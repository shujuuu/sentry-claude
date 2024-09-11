---
title: Tasks (sentry/tasks)
---
### Overview: The Tasks module manages asynchronous and scheduled jobs in Sentry.

### Key Classes:

- AsyncWorker

  - Purpose: Base class for defining asynchronous tasks

  - Key Methods:

    - `delay()`: Enqueues task for asynchronous execution

    - `apply()`: Executes task synchronously

- ScheduledTask

  - Purpose: Defines tasks that run on a schedule

  - Key Methods:

    - `run()`: Executes the scheduled task

    - `schedule()`: Defines when the task should run

### Key Flows:

- Task Queuing

  1. Task instance created

  2. Task serialized

  3. Task added to message queue (e.g., Redis)

  4. Worker picks up task from queue

  5. Task executed asynchronously

- Scheduled Job Execution

  1. Scheduler (e.g., Celery Beat) checks for due tasks

  2. Due task triggered

  3. Worker executes task

  4. Results logged or stored as needed

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
