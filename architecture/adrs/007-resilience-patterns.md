# ADR 007: Resilience Patterns

## Status
Accepted

## Context
Need to handle:
- Service failures
- Network issues
- High latency

## Decision
Implement:
1. Circuit breakers (opossum for Node.js)
2. Retry mechanisms (axios-retry)
3. Fallback responses

## Consequences
### Positive:
- Improved fault tolerance
- Better user experience during failures
- Prevents cascading failures

### Negative:
- Additional code complexity
- Potential masking of real issues 