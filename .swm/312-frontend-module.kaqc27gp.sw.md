---
title: 3.1.2 Frontend module
---
### Overview:&nbsp;

The Frontend module handles the user interface of Sentry, built as a single-page application.

### Key Classes:

- App

  - Purpose: Root React component that sets up routing and global state

  - Key Methods:

    - `render()`: Renders the main application structure

- ProjectsStore

  - Purpose: Redux store for managing project data

  - Key Methods:

    - `fetchProjects()`: Retrieves project data from the API

    - `updateProject()`: Updates local project data

### Key Flows:

- User Interaction Handling

  1. User interacts with UI element

  2. React event handler triggered

  3. Action creator called

  4. Action dispatched to Redux store

  5. Reducers update state

  6. Components re-render with new state

- Data Fetching

  1. Component mounts or user navigates to new view

  2. useEffect hook triggers data fetch

  3. API call made to backend

  4. Response received and normalized

  5. Data stored in Redux store

  6. Components update with new data

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
