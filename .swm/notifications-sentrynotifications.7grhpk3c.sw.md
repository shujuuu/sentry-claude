---
title: Notifications (sentry/notifications)
---
### Overview:&nbsp;

The Notifications module manages the sending of alerts and updates to users.

### Key Classes:

- NotificationHandler

  - Purpose: Determines when and to whom notifications should be sent

  - Key Methods:

    - `should_notify()`: Checks if a notification should be sent

    - `get_recipients()`: Determines who should receive the notification

- DeliveryBackend

  - Purpose: Handles the actual sending of notifications

  - Key Methods:

    - `send()`: Sends the notification via the appropriate channel (e.g., email, Slack)

### Key Flows:

- Notification Triggering

  1. Event occurs that may require notification

  2. NotificationHandler.should_notify() checks notification rules

  3. If notification needed, recipients determined

  4. Notification content generated

- Delivery Process

  1. Notification queued for delivery

  2. Appropriate DeliveryBackend selected

  3. Notification sent via chosen method

  4. Delivery status tracked and logged

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
