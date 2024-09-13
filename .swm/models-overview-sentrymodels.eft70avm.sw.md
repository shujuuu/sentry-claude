---
title: Models Overview (sentry/models)
---
### Overview:&nbsp;

The Models module is a fundamental component of Sentry, defining the data structures that underpin the entire system. It uses Django's ORM (Object-Relational Mapping) to define database schemas, relationships, and behaviors. This module is crucial for data persistence, retrieval, and manipulation throughout Sentry.

The Models module is organized into several sub-modules:

1. Core Models

2. Event Models

3. Identity and Authentication Models

4. Integration Models

5. Configuration Models

6. Monitoring Models

7. Release and Deployment Models

8. Alert and Notification Models

---

&nbsp;

### 1\. Core Models (sentry/models/core.py)

Core Models define the fundamental entities in Sentry.

#### Key Components:

- **Organization**: Represents a Sentry organization

- **Project**: Represents a project within an organization

- **Team**: Represents a team within an organization

- **User**: Represents a Sentry user

#### Key Relationships:

- Organizations have many Projects and Teams

- Projects belong to Organizations and can be associated with Teams

- Users can belong to multiple Organizations and Teams

&nbsp;

### 2\. Event Models (sentry/models/event.py)

Event Models handle error and transaction data.

#### Key Components:

- **Event**: Represents a single error or transaction event

- **Group**: Represents a collection of similar events

- **EventAttachment**: Represents files attached to events

#### Key Relationships:

- Events belong to a Group and a Project

- Groups belong to a Project

&nbsp;

### 3\. Identity and Authentication Models (sentry/models/auth.py)

These models manage user identities and authentication methods.

#### Key Components:

- **Identity**: Represents a user's identity in an external system

- **AuthIdentity**: Links a User to an Identity

- **AuthProvider**: Represents an authentication provider (e.g., Google, GitHub)

#### Key Relationships:

- Users can have multiple Identities

- AuthIdentities link Users to specific AuthProviders

###

### 4\. Integration Models (sentry/models/integration.py)

Integration Models manage connections with external services.

#### Key Components:

- **Integration**: Represents an external service integration

- **ExternalIssue**: Links Sentry issues to issues in external systems

#### Key Relationships:

- Integrations are associated with Organizations

- ExternalIssues link Groups to external issue trackers

&nbsp;

### 5\. Configuration Models (sentry/models/options.py)

Configuration Models store various settings and options.

#### Key Components:

- **Option**: Stores global Sentry configuration options

- **ProjectOption**: Stores project-specific configuration options

#### Key Relationships:

- ProjectOptions are associated with specific Projects

&nbsp;

### 6\. Monitoring Models (sentry/models/monitor.py)

Monitoring Models handle Sentry's self-monitoring capabilities.

#### Key Components:

- **Monitor**: Represents a monitoring check

- **CheckIn**: Represents a status update for a Monitor

#### Key Relationships:

- CheckIns are associated with a specific Monitor

&nbsp;

### 7\. Release and Deployment Models (sentry/models/release.py)

These models manage software releases and deployments.

#### Key Components:

- **Release**: Represents a software release

- **ReleaseFile**: Represents a file associated with a Release

- **Deployment**: Represents a deployment of a Release

#### Key Relationships:

- Releases are associated with Projects

- Deployments are associated with Releases

&nbsp;

### 8\. Alert and Notification Models (sentry/models/alert.py)

These models handle alerting and notification logic.

#### Key Components:

- **Rule**: Defines conditions for triggering alerts

- **Alert**: Represents a triggered alert

- **AlertRule**: Defines advanced alert rules

#### Key Relationships:

- Rules and AlertRules are associated with Projects

- Alerts are associated with Projects and can reference specific Events or Issues

&nbsp;

---

&nbsp;

## Interactions Between Sub-modules

The Models sub-modules interact to create a cohesive data structure:

1. **Core Models ↔ Event Models**:

   - Events and Groups are associated with Projects and Organizations

2. **Core Models ↔ Identity and Authentication Models**:

   - Users are authenticated and associated with Organizations

3. **Core Models ↔ Integration Models**:

   - Integrations are set up at the Organization level

4. **Event Models ↔ Alert and Notification Models**:

   - Alerts are triggered based on Events and Groups

5. **Release and Deployment Models ↔ Event Models**:

   - Events are associated with specific Releases

&nbsp;

---

&nbsp;

## Key Classes

### Organization (Core Models)

```
class Organization(Model):
    name = models.CharField(max_length=64)
    slug = models.SlugField(unique=True)
    status = BoundedPositiveIntegerField(choices=ORGANIZATION_STATUS_CHOICES)

    class Meta:
        app_label = 'sentry'

    def get_audit_log_data(self):
        # Return data for audit logging
```

### Event (Event Models)

```
class Event(Model):
    group = FlexibleForeignKey('sentry.Group', null=True, blank=True, related_name="events")
    event_id = models.CharField(max_length=32, null=True, db_index=True)
    project_id = BoundedBigIntegerField(blank=True, null=True)
    message = models.TextField()
    platform = models.CharField(max_length=64, null=True)
    datetime = models.DateTimeField(default=timezone.now, db_index=True)

    class Meta:
        app_label = 'sentry'
        unique_together = (('project_id', 'event_id'),)

    def save(self, *args, **kwargs):
        # Custom save logic
```

&nbsp;

### Integration (Integration Models)

```
class Integration(Model):
    organizations = models.ManyToManyField('sentry.Organization')
    provider = models.CharField(max_length=64)
    external_id = models.CharField(max_length=64)
    name = models.CharField(max_length=200)

    class Meta:
        app_label = 'sentry'
        unique_together = (('provider', 'external_id'),)

    def get_provider(self):
        # Return the provider instance
```

&nbsp;

---

&nbsp;

## Common Patterns and Best Practices

1. **Soft Deletion**: Use of `BoundedBigIntegerField` for status fields to allow soft deletion.

2. **Slugs**: Use of slug fields for human-readable unique identifiers.

3. **Flexible Foreign Keys**: Use of `FlexibleForeignKey` for better performance with large datasets.

4. **Denormalization**: Strategic denormalization for performance optimization.

5. **Audit Logging**: Implementation of `get_audit_log_data` methods for comprehensive audit trails.

&nbsp;

---

&nbsp;

## Database Interactions

- **Queries**: Efficient querying using Django's ORM

- **Indexing**: Strategic use of database indexes for performance

- **Transactions**: Use of database transactions for data integrity

&nbsp;

---

&nbsp;

## Testing

- **Unit Tests**: For individual model methods and properties

- **Integration Tests**: For complex queries and model interactions

- **Factories**: Use of factory_boy for generating test data

&nbsp;

---

&nbsp;

## Related Modules

- **Web**: Uses models for data persistence and retrieval in API endpoints

- **Tasks**: Interacts with models for background processing and data manipulation

- **Search**: Indexes and queries data defined in the Models module

&nbsp;

###

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
