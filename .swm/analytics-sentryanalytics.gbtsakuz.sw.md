---
title: Analytics (sentry/analytics)
---
### Overview:&nbsp;

The Analytics module tracks usage and generates insights about Sentry usage.

### Key Classes:

- AnalyticsEvent

  - Purpose: Represents a trackable event in Sentry

  - Key Fields: type, data, datetime, organization

- EventProcessor

  - Purpose: Processes and aggregates analytics events

  - Key Methods:

    - `process()`: Handles incoming events

    - `aggregate()`: Compiles event data into reportable metrics

### Key Flows:

- Event Tracking

  1. Trackable action occurs in Sentry

  2. AnalyticsEvent created

  3. Event queued for processing

  4. EventProcessor handles event

  5. Event data stored or aggregated

- Report Generation

  1. Reporting job triggered (e.g., daily/weekly)

  2. Relevant event data queried

  3. Data aggregated and analyzed

  4. Report generated and stored or sent

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
