---
title: Models-old
---
### Key Classes:

- Project

  - Purpose: Represents a project in Sentry

  - Key Fields: name, organization, platform, status

- Organization

  - Purpose: Represents an organization that owns projects

  - Key Fields: name, status, default_role

- Event

  - Purpose: Represents an error or transaction event

  - Key Fields: project, group, message, datetime

&nbsp;

### Key Flows:

- Data Persistence

  1. Model instance created or updated

  2. Pre-save hooks executed

  3. Data saved to database

  4. Post-save hooks executed

- Relationship Management

  1. Related objects queried through foreign keys

  2. Prefetch_related and select_related used for optimization

  3. Cached_property used for frequently accessed computed fields

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
