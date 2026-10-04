# FusionTech Storage

## Current Demonstration Model

The current FusionTech implementation uses browser-side persistence for selected application data.

This design is useful for:

- Portfolio demonstrations
- Local development
- Lightweight prototypes
- Environments where a database is unnecessary

It also allows the project to operate with a relatively small infrastructure footprint.

## Persistence Characteristics

Browser-side persistence means data is associated with the user's browser environment rather than a centralized production database.

Consequences include:

- Data is local to the browser
- Clearing browser data can remove persisted information
- Different devices do not automatically share the same data
- Different browsers can have different state
- It is not suitable as the authoritative source of business data

## Default Catalog

The application can initialize a demonstration service catalog when no existing catalog is available.

The catalog is designed to demonstrate the CMS and service-discovery experience.

## Production Recommendation

A production system should generally move authoritative business data to a backend service and database.

A possible model is:

```text
React Frontend
      │
      ▼
Authenticated API
      │
      ├── Services
      ├── Users / Roles
      ├── Analytics
      └── Audit Events
             │
             ▼
          Database
```

## Recommended Production Storage

Depending on requirements, production storage could include:

- PostgreSQL for relational application data
- Object storage for uploaded media
- Redis for caching or transient state
- Managed backups
- Database migrations
- Audit records

## Data Integrity

Server-side persistence enables:

- Validation
- Transactions
- Concurrency control
- Backups
- Access control
- Cross-device synchronization
- Reliable data recovery

## Privacy

Do not place sensitive information in browser storage.

Sensitive data should be stored and processed using an architecture appropriate to its sensitivity, with server-side access controls and secure transport.
