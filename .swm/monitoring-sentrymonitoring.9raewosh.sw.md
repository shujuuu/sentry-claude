---
title: Monitoring (sentry/monitoring)
---
### Overview:&nbsp;

The Monitoring module tracks the health and performance of Sentry itself.

### Key Classes:

- Monitor

  - Purpose: Defines a specific aspect of Sentry to be monitored

  - Key Fields: type, config, status, last_check_in

- CheckInManager

  - Purpose: Manages the process of recording and evaluating check-ins

  - Key Methods:

    - `process_check_in()`: Handles incoming check-in data

    - `trigger_failure_alert()`: Initiates alerts for failed check-ins

### Key Flows:

- Health Check Execution

  1. Scheduled task triggers health check

  2. Monitor runs its defined check

  3. Results recorded via CheckInManager

  4. Monitor status updated

- Alert Triggering

  1. CheckInManager detects missed or failed check-in

  2. Alert conditions evaluated

  3. If conditions met, alert generated

  4. Alert sent via Notifications module

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
