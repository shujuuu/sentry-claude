---
title: Overview
---
Sentry is an open-source error tracking and performance monitoring platform. It helps developers identify, triage, and resolve code errors and performance issues in real-time.

## 2\. Architecture

Sentry's architecture consists of several key components:

1. SDK: Client-side libraries that capture errors and performance data

2. Relay: Edge service that handles data ingestion and processing

3. Web: User interface and API endpoints

4. Workers: Background task processors

5. Database: Stores project configurations and error data

6. Search: Indexes and queries error events

## 3\. Main and sub-modules

### 3.1 Web&nbsp;

Description: The Web module handles HTTP requests, renders the user interface, and provides API endpoints. You can read more at

or look up the file inside it <SwmPath>[src/sentry/web/](/src/sentry/web/)</SwmPath>

Key Components:&nbsp;

- <SwmLink doc-title="3.1.1 API module">[3.1.1 API module](/.swm/311-api-module.n262jy6w.sw.md)</SwmLink>
- <SwmLink doc-title="3.1.2 Frontend module">[3.1.2 Frontend module](/.swm/312-frontend-module.kaqc27gp.sw.md)</SwmLink>
- <SwmLink doc-title="3.1.3 Auth Component">[3.1.3 Auth Component](/.swm/313-auth-component.njjxmdfx.sw.md)</SwmLink>

### 3.2 Models&nbsp;

The Models module defines the database schema and object-relational mapping (ORM) for Sentry's data. You can read more at <SwmLink doc-title="Models (sentry/models)">[Models (sentry/models)](/.swm/models-sentrymodels.eft70avm.sw.md)</SwmLink> and look up the file inside it <SwmPath>[src/sentry/models/](/src/sentry/models/)</SwmPath>

### 3.3 Tasks&nbsp;

sources: <SwmPath>[src/sentry/dynamic_sampling/tasks/](/src/sentry/dynamic_sampling/tasks/)</SwmPath>

### 3.4 Search&nbsp;

You can read more at <SwmLink doc-title="3.4 Search (sentry/search)">[3.4 Search (sentry/search)](/.swm/34-search-sentrysearch.bfg917s9.sw.md)</SwmLink>

sources: <SwmPath>[src/sentry/search/](/src/sentry/search/)</SwmPath>

- Indexing&nbsp;
- Query Engine

### 3.5 Integrations&nbsp;

sources: <SwmPath>[src/sentry/integrations/](/src/sentry/integrations/)</SwmPath>

- Third-party Services&nbsp;
- Plugins <SwmPath>[src/sentry/plugins/](/src/sentry/plugins/)</SwmPath>

### 3.6 Analytics&nbsp;

sources: <SwmPath>[src/sentry/analytics/](/src/sentry/analytics/)</SwmPath>

- Event Processing&nbsp;
- Reporting

### 3.7 Notification

- Email&nbsp;
- Webhooks

### 3.8 Monitoring&nbsp;

Source: <SwmPath>[src/sentry/monitoring/](/src/sentry/monitoring/)</SwmPath>, <SwmPath>[src/sentry/monitors/](/src/sentry/monitors/)</SwmPath>

- Performance&nbsp;
- Alerts

---

&nbsp;

## 5\. Interesting Flows

5.1 Error Ingestion Process&nbsp;

5.2 Issue Grouping&nbsp;

5.3 Alert Notifications&nbsp;

5.4 Search Functionality&nbsp;

5.5 User Authentication Flow

---

&nbsp;

## 6\. Development Guide

6.1 Setting Up Development Environment&nbsp;

6.2 Running Tests&nbsp;

6.3 Contributing Guidelines

---

&nbsp;

## 7\. API Reference

7.1 REST API&nbsp;

7.2 SDK APIs

---

&nbsp;

## 8\. Deployment

8.1 Self-Hosted Deployment&nbsp;

8.2 Cloud Deployment Options

---

##

### Detailed References

## 11\. Detailed References

11.1 Classes&nbsp;

- \[GroupedByModule\]&nbsp;

11.2 Flows

- \[GroupedByFunctionality\]

---

&nbsp;

## Appendix

A. Glossary&nbsp;

B. Additional Resources

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
