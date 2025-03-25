# ADR 003: Authentication Method - Google OAuth2

## Status
Accepted

## Context
Need secure, scalable authentication that:
- Minimizes password management 
- Supports stateless authentication

## Decision
Implement Google OAuth2 with JWT tokens.

## Consequences
### Positive:
- No password storage required
- Familiar user experience
- Built-in security from Google
- Stateless JWT enables horizontal scaling

### Negative: 
- Limited user data control 