# ADR 001: Database Choice - MongoDB

## Status
Accepted

## Context
We need a database that can handle:
- Dynamic content types (posts, stories, communities)
- Flexible schema requirements 
- Scalability for user growth

## Decision
Use MongoDB as the primary database for all services.

## Consequences
### Positive:
- Schema flexibility for evolving data models
- Horizontal scalability 
- Good performance for social media workloads

### Negative:
- Less transactional support than SQL databases