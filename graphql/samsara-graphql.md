# Samsara GraphQL Schema

## Overview

This document describes a conceptual GraphQL schema for the Samsara connected operations platform. Samsara provides a REST API at https://api.samsara.com with documentation at https://developers.samsara.com/. This GraphQL schema represents the same domain objects and relationships expressed as a typed GraphQL service.

Samsara serves physical operations industries including transportation, logistics, construction, field services, and energy. The platform covers fleet telematics, driver safety, ELD/HOS compliance, vehicle diagnostics, route management, industrial IoT sensors, and workforce management.

## Schema Source

- **Type**: Conceptual / Derived
- **Based on**: Samsara REST API (https://developers.samsara.com/reference)
- **REST base URL**: https://api.samsara.com
- **Authentication**: Bearer token / OAuth 2.0

## Core Domain Areas

### Vehicles and Telematics

The `Vehicle` type is the central entity for fleet management. Each vehicle carries real-time and historical telematics data through related types:

- `VehicleStats` — aggregate statistics for a vehicle over a time window
- `VehicleLocation` — GPS coordinates, heading, speed, and timestamp
- `VehicleSpeed` — instantaneous and rolling speed readings
- `EngineState` — on/off/idle state with transition timestamps
- `EngineHours` — cumulative engine hours for maintenance tracking
- `FuelLevel` — fuel tank percentage and estimated range
- `BatteryLevel` — state of charge for electric and hybrid vehicles
- `DefLevel` — diesel exhaust fluid level for emissions compliance
- `OBDData` — OBD-II parameter readings (RPM, coolant temp, etc.)
- `OBDFault` — active and historical diagnostic trouble codes
- `FaultCode` — decoded fault code with severity and description

### Assets and IoT

- `Asset` — non-vehicle tracked equipment (trailers, containers, heavy machinery)
- `AssetLocation` — GPS position and motion state for assets
- `AssetStats` — utilization, idle time, and sensor readings for assets

### Drivers and Workforce

- `Driver` — driver profile with license, HOS ruleset, and carrier assignment
- `DriverStats` — aggregate safety scores, miles driven, and event counts
- `DriverApp` — ELD app session state, log certification status
- `DriverMessage` — in-cab messaging between dispatch and driver

### Hours of Service (HOS) and Compliance

- `HOS` — current HOS status (driving, on-duty, off-duty, sleeper)
- `HOSLog` — individual HOS duty status log entry
- `HOSCycle` — 60/70-hour cycle state and available time
- `HOSViolation` — detected HOS rule violations with severity

### Inspections (DVIR)

- `DVIRReport` — Driver Vehicle Inspection Report with pre/post trip status
- `DVIRMechanic` — mechanic sign-off record for defect resolution
- `DVIRDefect` — individual defect item with category and resolution status

### Trips and Routes

- `Trip` — a single vehicle trip from ignition on to ignition off
- `TripLog` — high-resolution breadcrumb log for a trip
- `TripSegment` — subdivided segment of a trip (e.g., highway vs. city)
- `Route` — planned route with ordered waypoints
- `RoutePlan` — optimization metadata and constraints for a route
- `RoutePoint` — individual stop or waypoint within a route

### Dispatch

- `Dispatch` — a dispatch workflow instance
- `DispatchJob` — a job assigned to a driver/vehicle with status lifecycle
- `DispatchStop` — an individual stop within a dispatch job

### Organization and Administration

- `Tag` — label applied to vehicles, drivers, or assets for grouping
- `Address` — geofenced address with formatted location and lat/lng
- `Contact` — person record associated with an address or organization
- `Group` — logical grouping of drivers, vehicles, or assets
- `Organization` — top-level Samsara customer account

### Integrations and Webhooks

- `Integration` — third-party system integration configuration
- `Webhook` — webhook endpoint registration
- `WebhookConfig` — event type subscriptions and secret for a webhook

### Alerts and Notifications

- `Alert` — triggered alert instance (speeding, geofence, HOS, etc.)
- `AlertNotification` — delivery record for an alert (email, SMS, webhook)
- `AlertConfig` — alert rule definition with thresholds and recipients

### Safety and Coaching

- `Camera` — dashcam device associated with a vehicle
- `DashcamVideo` — dashcam recording with event trigger and timestamps
- `DashcamFootage` — raw footage segment from a camera
- `Clip` — user-requested clip or event-triggered short video
- `AI` — AI inference result attached to a dashcam event
- `RiskScore` — computed driver risk score from AI and telematics signals
- `CoachingEvent` — individual coaching-worthy event (harsh brake, distraction, etc.)
- `CoachingSession` — structured coaching review session for a driver

### Media

- `MediaRequest` — request to retrieve dashcam media with status tracking

### Configuration

- `TruckConfig` — vehicle-specific hardware and sensor configuration
- `TrailerConfig` — trailer-specific sensor and tracking configuration
- `LightValue` — lighting sensor reading from trailer or asset sensor

## Query Patterns

```graphql
# Fetch a vehicle with current location and stats
query GetVehicle($id: ID!) {
  vehicle(id: $id) {
    id
    name
    vin
    location {
      latitude
      longitude
      speed
      heading
      timestamp
    }
    engineState {
      value
      updatedAt
    }
    fuelLevel {
      percent
      updatedAt
    }
  }
}

# List all active drivers with HOS status
query ActiveDrivers {
  drivers(isActive: true) {
    id
    name
    licenseNumber
    hos {
      currentStatus
      driveRemainingMs
      shiftRemainingMs
      cycleRemainingMs
    }
  }
}

# Fetch open DVIR defects for a vehicle
query OpenDefects($vehicleId: ID!) {
  vehicle(id: $vehicleId) {
    dvirReports(resolved: false) {
      id
      inspectionType
      defects {
        id
        category
        description
        isResolved
      }
    }
  }
}
```

## Mutation Patterns

```graphql
# Create a dispatch job
mutation CreateDispatchJob($input: DispatchJobInput!) {
  createDispatchJob(input: $input) {
    id
    status
    driver {
      id
      name
    }
    stops {
      id
      address {
        formattedAddress
      }
      scheduledArrival
    }
  }
}

# Update driver HOS log
mutation UpdateHOSLog($id: ID!, $status: HOSStatus!) {
  updateHOSLog(id: $id, status: $status) {
    id
    status
    startTime
  }
}
```

## Subscription Patterns

```graphql
# Subscribe to real-time vehicle location updates
subscription VehicleLocationUpdates($vehicleId: ID!) {
  vehicleLocation(vehicleId: $vehicleId) {
    latitude
    longitude
    speed
    heading
    timestamp
  }
}

# Subscribe to safety alert events
subscription SafetyAlerts($orgId: ID!) {
  alertTriggered(organizationId: $orgId) {
    id
    type
    severity
    vehicle {
      id
      name
    }
    driver {
      id
      name
    }
    triggeredAt
  }
}
```

## Notes

- This is a conceptual schema derived from the Samsara REST API surface. Samsara does not currently publish a public GraphQL endpoint.
- Types and fields are based on the REST API reference at https://developers.samsara.com/reference and the OpenAPI specification in this repository.
- All IDs are strings in the Samsara REST API and are represented as `ID` scalars in this schema.
- Timestamps use ISO 8601 format represented as the `DateTime` custom scalar.
- GPS coordinates use the `Float` scalar with standard WGS84 decimal degrees.
