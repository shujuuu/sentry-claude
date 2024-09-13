---
title: 'Flow: Frontend rendering'
---
## Overview

This flow describes the process of rendering a page in Sentry's frontend.

## Trigger

User navigates to a new page in Sentry.

## Steps

1. Route Matching

   - React Router matches the URL to a route

2. Component Loading

   - The corresponding React component is loaded

3. Initial State Setup

   - Component's constructor and initial state are set up

4. API Data Fetching

   - componentDidMount() triggers API requests for necessary data

5. State Update

   - Component state is updated with fetched data

6. Rendering

   - Component's render method is called

   - Child components are rendered recursively

7. DOM Update

   - React updates the DOM with the rendered output

## Outcome

The page is fully rendered and interactive.

## Error Handling

- If an error occurs during rendering, the nearest error boundary catches it

- The error state is rendered instead of the normal component output

## Related Flows

- API Data Fetching Flow

- User Interaction Flow

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
