---
title: 'Flow: Single Sign-On (SSO) Authentication'
---
## Overview

This flow describes the process of authenticating a user through Single Sign-On (SSO) in Sentry.

## Trigger

User initiates login through SSO option on Sentry login page.

## Steps

 1. User Selection

    - User clicks on "Login with SSO" option

    - Sentry frontend sends request to Auth module

 2. Identity Provider Selection

    - Auth module presents list of configured identity providers

    - User selects their organization's identity provider

 3. Redirect to Identity Provider

    - Auth module generates SSO request

    - User is redirected to identity provider's login page

 4. External Authentication

    - User authenticates with identity provider

    - Identity provider validates user credentials

 5. Token Generation

    - Identity provider generates authentication token

    - User is redirected back to Sentry with token

 6. Token Validation

    - Auth module receives token

    - Token is validated for authenticity and expiration

 7. User Provisioning/Updating

    - If user doesn't exist in Sentry, a new account is created

    - If user exists, their information is updated if necessary

 8. Session Creation

    - Auth module creates a new session for the user

    - Session token is generated

 9. Authorization

    - User's roles and permissions are loaded

    - Access control settings are applied to the session

10. Redirect to Dashboard

    - User is redirected to Sentry dashboard

    - Frontend loads user-specific data based on permissions

## Outcome

User is authenticated and gains access to Sentry with appropriate permissions.

## Error Handling

- If identity provider authentication fails, user is returned to Sentry login page with error message

- If token validation fails, user is prompted to retry SSO or contact support

- If user provisioning fails, an error is logged and user is prompted to contact support

## Related Flows

- Password-based Authentication

- Two-Factor Authentication (2FA)

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
