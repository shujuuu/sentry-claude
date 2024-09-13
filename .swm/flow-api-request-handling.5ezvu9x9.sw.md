---
title: 'Flow: API Request Handling'
---
## Overview

This flow describes the process of handling an API request in Sentry.

## Trigger

An HTTP request is received by the Sentry API.

## Steps

1. Request Routing

   - Django routes the request to the appropriate APIView

2. Dispatch

   - APIView.dispatch() method is called

3. Initial Setup

   - APIView.initial() performs setup tasks

   - Authentication is performed

   - Permissions are checked

4. Request Method Handling

   - Appropriate HTTP method handler (get(), post(), etc.) is called

5. Response Preparation

   - Data is serialized into the response format

6. Response Sending

   - Response is sent back to the client

## Outcome

Client receives the API response.

## Error Handling

- If authentication fails, a 401 Unauthorized response is sent

- If permission check fails, a 403 Forbidden response is sent

- Other exceptions are handled by APIView.handle_exception()

## Related Flows

- Authentication Flow

- Rate Limiting Flow

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
