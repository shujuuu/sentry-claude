---
title: 'Class: AuthenticationBackend'
---
Located in: `sentry/auth/backends.py`

## Overview

The `AuthenticationBackend` class is responsible for handling various authentication methods in Sentry, including SSO, password-based auth, and 2FA.

## Properties

| Name   | Type  | Description                                      |
| ------ | ----- | ------------------------------------------------ |
| `name` | `str` | Name of the authentication backend               |
| `type` | `str` | Type of authentication (e.g., 'sso', 'password') |

## Methods

### `authenticate(request, **credentials) -> User | None`

Authenticates a user based on the provided credentials.

Parameters:

- `request`: The current request object

- `**credentials`: Dict containing authentication credentials

Returns: A `User` object if authentication is successful, otherwise `None`

### `get_user(user_id) -> User | None`

Retrieves a user by their ID.

Parameters:

- `user_id`: The ID of the user to retrieve

Returns: A `User` object if found, otherwise `None`

### `configure_sso() -> Dict`

Configures SSO settings for the authentication backend.

Returns: A dictionary containing SSO configuration settings

### `validate_sso_token(token: str) -> bool`

Validates an SSO token received from an identity provider.

Parameters:

- `token`: The SSO token to validate

Returns: `True` if the token is valid, otherwise `False`

### `create_or_update_user(user_data: Dict) -> User`

Creates a new user or updates an existing user based on SSO data.

Parameters:

- `user_data`: Dictionary containing user information from the identity provider

Returns: The created or updated `User` object

## Usage Examples

```python
class SentrySSOBackend(AuthenticationBackend):
    name = 'sentry-sso'
    type = 'sso'

    def authenticate(self, request, **credentials):
        token = credentials.get('sso_token')
        if not token or not self.validate_sso_token(token):
            return None user_data = self.get_user_data_from_token(token)
        user = self.create_or_update_user(user_data)
        return user
    def configure_sso(self): return {
        'provider_name': 'Sentry SSO',
        'callback_url':  'https://sentry.io/auth/sso/callback/',
        # Other configuration options...
    }

# Usage
backend = SentrySSOBackend() user = backend.authenticate(request, sso_token='received_token')
if
    user: login(request, user)
else:
# Handle authentication failure
```

## Related Classes

- `User`: Represents a Sentry user

- `PermissionManager`: Handles user permissions and access control

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
