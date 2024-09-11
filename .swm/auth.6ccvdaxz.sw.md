---
title: Auth
---
### Overview:&nbsp;

The Auth module manages user authentication and authorization across Sentry.

### Key Classes:

- AuthenticationBackend

  - Purpose: Handles various authentication methods (e.g., password, SSO)

  - Key Methods:

    - `authenticate()`: Verifies user credentials

    - `get_user()`: Retrieves user object from session data

- PermissionManager

  - Purpose: Manages role-based access control

  - Key Methods:

    - `has_permission()`: Checks if a user has a specific permission

### Key Flows:

- User Authentication

  1. User submits login credentials

  2. AuthenticationBackend verifies credentials

  3. If valid, user session created

  4. User redirected to dashboard

- Single Sign-On (SSO)

  1. User initiates SSO login

  2. User redirected to identity provider

  3. Identity provider authenticates user

  4. User redirected back to Sentry with token

  5. Token verified and user session created

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
