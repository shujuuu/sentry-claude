---
title: Integrations (sentry/integrations)
---
### Overview:&nbsp;

The Integrations module manages connections between Sentry and external services.

### Key Classes:

- IntegrationProvider

  - Purpose: Defines the interface for a specific integration

  - Key Methods:

    - `setup()`: Configures the integration

    - `create_integration()`: Instantiates a new integration

- IntegrationInstallation

  - Purpose: Represents an installed integration for an organization

  - Key Methods:

    - `get_config()`: Retrieves integration configuration

    - `update_organization_config()`: Updates organization-specific settings

### Key Flows:

- Integration Setup

  1. User selects integration to install

  2. IntegrationProvider.setup() called

  3. User redirected to external service for authorization

  4. External service redirects back with token

  5. IntegrationInstallation created and configured

- Data Synchronization

  1. Webhook received from external service

  2. Relevant IntegrationInstallation identified

  3. Data parsed and normalized

  4. Sentry data updated based on webhook content

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
