---
title: 'Class: APIView'
---
Located in: <SwmPath>[src/sentry/api/base.py](/src/sentry/api/base.py)</SwmPath>

## Overview

The `APIView` class is the base class for all API views in Sentry. It provides common functionality for handling API requests, authentication, and response formatting.

## Properties

| Name                     | Type                        | Description                           |
| ------------------------ | --------------------------- | ------------------------------------- |
| `authentication_classes` | `List[AuthenticationClass]` | List of authentication classes to use |
| `permission_classes`     | `List[PermissionClass]`     | List of permission classes to check   |

## Methods

### `dispatch(request, *args, **kwargs) -> Response`

Main method for handling incoming requests.

### `handle_exception(exc) -> Response`

Handles exceptions raised during request processing.

### <SwmToken path="/src/sentry/api/base.py" pos="432:3:5" line-data="                self.initial(request, *args, **kwargs)">`initial(request`</SwmToken>`, *args, **kwargs) -> None`

Performs initial request setup, including authentication and permission checks.

## Usage Examples

```python
from sentry.api.base import APIView
from sentry.api.permissions import ProjectPermission

class ProjectDetailsView(APIView):
    permission_classes = (ProjectPermission,)

    def get(self, request, project_id):
        # Handle GET request
        pass

    def put(self, request, project_id):
        # Handle PUT request
        pass
```

## Related Classes

- `AuthenticationClass`: Base class for authentication methods

- `PermissionClass`: Base class for permission checks

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
