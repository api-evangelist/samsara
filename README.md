# Samsara

Samsara is a leading connected operations platform for physical operations industries including transportation, logistics, construction, field services, and energy. The Samsara REST API provides programmatic access to fleet telematics, driver safety, compliance (ELD/HOS), vehicle diagnostics, route management, industrial IoT sensors, and workforce management. With over two million connected devices, the platform offers real-time GPS tracking, AI-powered safety cameras, digital inspection forms (DVIRs), IFTA reporting, and data streaming via webhooks and Kafka.

**URL:** [Samsara Developer Portal](https://developers.samsara.com/)

## Tags

Asset Tracking, Connected Operations, ELD, Fleet Management, GPS Tracking, IoT, Logistics, Safety, Telematics, Transportation

## Timestamps

- **Created:** 2024-11-07
- **Modified:** 2026-05-02

## APIs

### Samsara API

The Samsara REST API provides comprehensive access to fleet and industrial IoT data. Base URL: `https://api.samsara.com`. Authentication via Bearer token.

#### Tags

Addresses, Assets, Compliance, Documents, Drivers, DVIR, ELD, Fleet, Forms, Hours Of Service, IoT, Routes, Safety, Sensors, Tags, Telematics, Users, Vehicles, Webhooks

#### Properties

- [Documentation](https://developers.samsara.com/docs/rest-api-overview)
- [OpenAPI](openapi/samsara-openapi.yml) — 217 Operations
- [GitHub Repository](https://github.com/samsarahq/api-docs)
- [Python SDK](https://github.com/samsarahq/samsara-python)
- [JavaScript SDK](https://github.com/samsarahq/samsara-js)

## Common Properties

- [Documentation](https://developers.samsara.com/) — Samsara Developer Portal
- [Documentation](https://developers.samsara.com/docs/getting-started) — Getting Started Guide
- [GitHub Organization](https://github.com/samsarahq) — Samsara GitHub
- [Authentication](https://developers.samsara.com/docs/authentication) — API Authentication

## OpenAPI Specifications

- [openapi/samsara-openapi.yml](openapi/samsara-openapi.yml) — Samsara API (217 operations across 26 resource areas)

## Rules

- [rules/samsara-rules.yml](rules/samsara-rules.yml) — Samsara API Spectral Rules

## Capabilities

### Shared Definitions

- [capabilities/shared/samsara.yaml](capabilities/shared/samsara.yaml) — Samsara API (vehicles, drivers, routes, safety, compliance)

### Workflow Capabilities

- [capabilities/fleet-operations.yaml](capabilities/fleet-operations.yaml) — Fleet Operations (vehicles, drivers, routes, assets, addresses, tags)
- [capabilities/safety-compliance.yaml](capabilities/safety-compliance.yaml) — Safety and Compliance (safety events, DVIR, HOS/ELD logs)

## JSON Schema

- [json-schema/samsara-vehicle-schema.json](json-schema/samsara-vehicle-schema.json) — Samsara Vehicle
- [json-schema/samsara-driver-schema.json](json-schema/samsara-driver-schema.json) — Samsara Driver
- [json-schema/samsara-safety-event-schema.json](json-schema/samsara-safety-event-schema.json) — Samsara Safety Event

## JSON Structure

- [json-structure/samsara-vehicle-structure.json](json-structure/samsara-vehicle-structure.json) — Vehicle Field Hierarchy
- [json-structure/samsara-driver-structure.json](json-structure/samsara-driver-structure.json) — Driver Field Hierarchy

## JSON-LD

- [json-ld/samsara-context.jsonld](json-ld/samsara-context.jsonld) — Samsara JSON-LD Context

## Examples

- [examples/samsara-list-vehicles-example.json](examples/samsara-list-vehicles-example.json) — List Vehicles Request/Response
- [examples/samsara-list-safety-events-example.json](examples/samsara-list-safety-events-example.json) — List Safety Events Request/Response

## Vocabulary

- [vocabulary/samsara-vocabulary.yml](vocabulary/samsara-vocabulary.yml) — Samsara Vocabulary

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
