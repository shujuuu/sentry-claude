---
title: Overview
---
Sentry is an open-source error tracking and performance monitoring platform. It helps developers identify, triage, and resolve code errors and performance issues in real-time.

## Architecture

```mermaid
graph TD
    A[Sentry Demo] --> B[Web]
    B --> B1[API]
    B --> B2[Frontend]
    B --> B3[Auth]

    A --> C[Models]
    A --> D[Task]
    A --> E[Search]
    A --> F[Integrations]
    A --> G[Analytics]
    A --> H[Notification]
    A --> I[Monitoring]
```

&nbsp;

## Main and sub-modules

### 1\. Web&nbsp;

The Web module handles HTTP requests, renders the user interface, and provides API endpoints. Read in-depth documentation at <SwmLink doc-title="Web module">[Web module](/.swm/web-module.ieqty71c.sw.md)</SwmLink> or find module at <SwmPath>[src/sentry/web/](/src/sentry/web/)</SwmPath>

Key Components:&nbsp;

- API
- Front-end
- Auth&nbsp;

### 2\. Models&nbsp;

The Models module defines the database schema and object-relational mapping (ORM) for Sentry's data. You can read more at  <SwmLink doc-title="Models Overview (sentry/models)">[Models Overview (sentry/models)](/.swm/models-overview-sentrymodels.eft70avm.sw.md)</SwmLink> and look up the files inside <SwmPath>[src/sentry/models/](/src/sentry/models/)</SwmPath>

Key Components:&nbsp;

- Core Models
- Event Models
- Identiry and Authentication Models
- Integration Models
- Configura Models
- Monitoring Models
- Release and Deployment Models

### 3\. Tasks&nbsp;

The Search module provides indexing and querying capabilities for Sentry data. Read more at <SwmLink doc-title="Tasks (sentry/tasks)">[Tasks (sentry/tasks)](/.swm/tasks-sentrytasks.6s4lf1ow.sw.md)</SwmLink> or work on the modules at <SwmPath>[src/sentry/dynamic_sampling/tasks/](/src/sentry/dynamic_sampling/tasks/)</SwmPath>

Key Components:&nbsp;

- Event Processing
- Notification Tasks
- Data Cleanup
- Integration Sync
- Monitoring Tasks&nbsp;
- Analytics Tasks
- Scheduled Maintenance
- Release Management

### 4\. Search&nbsp;

The Search module provides indexing and querying capabilities for Sentry data. You can read more at <SwmLink doc-title="Search (sentry/searches)">[Search (sentry/searches)](/.swm/search-sentrysearches.bfg917s9.sw.md)</SwmLink> or look for code sources at <SwmPath>[src/sentry/search/](/src/sentry/search/)</SwmPath>

- Indexing&nbsp;
- Query Engine

### 5\. Integrations&nbsp;

The Integrations module manages connections between Sentry and external services. Read more at <SwmLink doc-title="Integrations (sentry/integrations)">[Integrations (sentry/integrations)](/.swm/integrations-sentryintegrations.6o37ninn.sw.md)</SwmLink> and find its modules at  <SwmPath>[src/sentry/integrations/](/src/sentry/integrations/)</SwmPath>

- Third-party Services&nbsp;
- Plugins&nbsp;

### 6\. Analytics&nbsp;

The Analytics module tracks usage and generates insights about Sentry usage. Read more at <SwmLink doc-title="Analytics (sentry/analytics)">[Analytics (sentry/analytics)](/.swm/analytics-sentryanalytics.gbtsakuz.sw.md)</SwmLink> and look out for its code sources at <SwmPath>[src/sentry/analytics/](/src/sentry/analytics/)</SwmPath>

- Event Processing&nbsp;
- Reporting

### 7\. Notification

The Notifications module manages the sending of alerts and updates to users. Read about the module at <SwmLink doc-title="Notifications (sentry/notifications)">[Notifications (sentry/notifications)](/.swm/notifications-sentrynotifications.7grhpk3c.sw.md)</SwmLink> <SwmPath>[src/sentry/notifications/](/src/sentry/notifications/)</SwmPath>

- Email&nbsp;
- Webhooks

### 8\. Monitoring&nbsp;

The Monitoring module tracks the health and performance of Sentry itself. Read about the module at <SwmLink doc-title="Monitoring (sentry/monitoring)">[Monitoring (sentry/monitoring)](/.swm/monitoring-sentrymonitoring.9raewosh.sw.md)</SwmLink> and look for code sources at <SwmPath>[src/sentry/monitoring/](/src/sentry/monitoring/)</SwmPath>, <SwmPath>[src/sentry/monitors/](/src/sentry/monitors/)</SwmPath>

- Performance&nbsp;
- Alerts

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
