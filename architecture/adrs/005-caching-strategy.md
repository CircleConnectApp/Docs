# ADR 005: Caching Strategy - Redis

## Status
Accepted

## Context
Need to optimize:
- Frequently accessed data (user profiles, posts)
- Rate limiting 

## Decision
Implement Redis for:
- Application caching
- Rate limiting storage 

## Consequences
### Positive:
- Sub-millisecond response times
- Reduced database load 
- Pub/sub capabilities

### Negative:
- Additional infrastructure 