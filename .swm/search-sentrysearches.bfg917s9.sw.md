---
title: Search (sentry/searches)
---
### Overview:&nbsp;

The Search module provides indexing and querying capabilities for Sentry data.

### Key Classes:

- SearchBackend

  - Purpose: Abstract base class for search implementations

  - Key Methods:

    - `index()`: Indexes a document

    - `search()`: Performs a search query

- SearchQuery

  - Purpose: Represents a search query

  - Key Methods:

    - `build()`: Constructs the search query

    - `execute()`: Runs the search query

### Key Flows:

- Indexing

  1. New or updated data received

  2. Data normalized and formatted for indexing

  3. Index updated in search backend (e.g., Elasticsearch)

- Query Execution

  1. User inputs search criteria

  2. SearchQuery object created and built

  3. Query executed against search backend

  4. Results parsed and returned to user

##

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
