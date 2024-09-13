---
title: 'Class: SentryComponent'
---
Located in: `sentry/static/app/components/sentryComponent.tsx`

## Overview

The `SentryComponent` class is a base class for React components in Sentry's frontend. It provides common functionality and hooks into Sentry-specific features.

## Properties

| Name  | Type  | Description                     |
| ----- | ----- | ------------------------------- |
| `api` | `API` | Instance of Sentry's API client |

## Methods

### `componentDidCatch(error: Error, errorInfo: React.ErrorInfo) -> void`

Handles errors that occur within the component tree.

### `renderError() -> React.ReactNode`

Renders an error state for the component.

## Usage Examples

```python
import SentryComponent from 'app/components/sentryComponent';

class ProjectOverview extends SentryComponent {
  state = {
    project: null,
  };

  componentDidMount() {
    this.api.request(`/projects/${this.props.projectId}/`)
      .then(project => this.setState({project}));
  }

  render() {
    if (this.state.error) {
      return this.renderError();
    }
    // Render component
  }
}
```

## Related Classes

- `API`: Sentry's API client class

- `ErrorBoundary`: React error boundary component

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
