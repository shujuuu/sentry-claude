---
title: Web module
---
## Overview

The Web module is a core component of Sentry, responsible for handling all web-based interactions with the system. It encompasses the API, Frontend, and Auth components, providing a comprehensive interface for users and external systems to interact with Sentry's error tracking and performance monitoring capabilities.

## Module Structure

The Web module is organized into three main sub-modules:

1. API

2. Frontend

3. Auth

---

### API (sentry/web/api)

The API sub-module handles all programmatic interactions with Sentry, providing RESTful endpoints for various operations.

#### Key Components:

- **APIView**: Base class for all API views

- **Endpoints**: Specific API endpoints (e.g., ProjectDetailsEndpoint, EventDetailsEndpoint)

- **Serializers**: Data serialization/deserialization for API requests and responses

- **Decorators**: Custom decorators for authentication, permissions, and rate limiting

#### Key Flows:

1. **API Request Handling**:

   - Request received

   - Authentication and authorization

   - Rate limiting check

   - Endpoint logic execution

   - Response serialization and return

2. **Pagination**:

   - Cursor-based pagination for large datasets

   - Efficient querying of database

### Frontend (sentry/web/frontend)

The Frontend sub-module manages the user interface of Sentry, implemented as a single-page application (SPA).

#### Key Components:

- **SentryApp**: Main React application component

- **Redux Store**: Central state management

- **React Components**: Reusable UI components (e.g., ErrorBoundary, LoadingIndicator)

- **Routes**: Definition of frontend routes and corresponding components

#### Key Flows:

1. **Frontend Rendering**:

   - Initial page load

   - React component tree rendering

   - API data fetching

   - State updates and re-renders

2. **User Interaction Handling**:

   - User action captured

   - Action dispatched to Redux store

   - State update

   - Component re-render

### Auth (sentry/web/auth)

The Auth sub-module manages user authentication and authorization across the Sentry web interface.

#### Key Components:

- **AuthenticationBackend**: Handles various authentication methods

- **LoginView**: Manages the login process

- **PermissionBackend**: Handles permission checks

- **AuthMiddleware**: Django middleware for authentication in web requests

#### Key Flows:

1. **User Authentication**:

   - Credentials submitted

   - Authentication backend validates credentials

   - Session created

   - User redirected to dashboard

2. **Single Sign-On (SSO)**:

   - SSO request initiated

   - User redirected to identity provider

   - Identity provider authenticates user

   - User redirected back to Sentry with token

   - Token validated and session created

---

## &nbsp;Interactions Between Sub-modules

The Web module's sub-modules interact closely to provide a seamless user experience:

1. **Frontend ↔ API**:

   - Frontend components make API calls to fetch and update data

   - API responses are used to update the Frontend's state

2. **Auth ↔ API**:

   - API endpoints use Auth module for authentication and authorization

   - Auth module may use API endpoints for user data retrieval

3. **Auth ↔ Frontend**:

   - Frontend uses Auth module for login/logout functionality

   - Auth status affects Frontend rendering (e.g., displaying user-specific content)

## Key Classes

### 4.1 APIView (API)

```python
class APIView(View): authentication_classes = [SessionAuthentication, ApiKeyAuthentication] permission_classes = [ApiPermission] def dispatch(self, request, *args, **kwargs): # Handle request dispatch, including authentication and permissions def handle_exception(self, exc): # Consistent exception handling for API responses
```

### 4.2 SentryApp (Frontend)

```python
class SentryApp extends React.Component { componentDidMount() { // Initialize app, fetch initial data } render() { return ( <ErrorBoundary> <Router> <Routes /> </Router> </ErrorBoundary> ); } }
```

### 4.3 AuthenticationBackend (Auth)

```python
class AuthenticationBackend: def authenticate(self, request, username=None, password=None): # Authenticate user credentials def get_user(self, user_id): # Retrieve user object from ID `
```

## Common Patterns and Best Practices

1. **API Versioning**: All API endpoints are versioned to ensure backwards compatibility.

2. **Error Handling**: Consistent error responses across all API endpoints.

3. **Performance Optimization**: Use of caching and efficient database queries to ensure fast response times.

4. **Security**: Implementation of CSRF protection, secure session handling, and proper input validation.

5. **Modularity**: Use of React components and Django apps to maintain a modular and extensible codebase.

## Testing

- **Unit Tests**: For individual components and functions

- **Integration Tests**: For API endpoints and authentication flows

- **End-to-End Tests**: For critical user journeys in the frontend

## Related Modules

- **Models**: Provides data models used by the Web module

- **Tasks**: Handles background processing triggered by web requests

- **Integrations**: Manages third-party service integrations accessible through the web interface

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
