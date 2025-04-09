# ADR 001: Database Choice - SQL and MongoDB

## Status
Accepted

## Context
We need databases that can handle:
- Structured, transactional data (user accounts, authentication)
- Dynamic content types (posts, stories, communities)
- Flexible schema requirements
- Strict data integrity where needed
- Scalability for user growth

## Decision
Adopt a hybrid database approach:

1. **SQL Databases (PostgreSQL)** for:
   - User Management
   - Authentication
   - Community metadata

2. **MongoDB (NoSQL)** for:
   - Posts
   - Stories
   - Feed content
   - Search indexing

## Justification

### SQL Databases (Structured Data)
- **Data Integrity**: Ensures ACID compliance for critical user data
- **Complex Transactions**: Supports role management and authentication flows
- **Strict Schemas**: Enforces data consistency for core platform entities
- **Mature Ecosystem**: Proven solutions for user management

### MongoDB (Unstructured Data)
- **Schema Flexibility**: Accommodates evolving content formats
- **Read Performance**: Optimized for feed retrieval and content queries  
- **Horizontal Scaling**: Handles growing content volumes
- **Document Model**: Natural fit for posts/stories with nested data

## Consequences
### Positive:
- Right tool for each data type (SQL for critical data, NoSQL for content)
- Maintains data integrity where needed while allowing flexibility
- Optimized performance characteristics for each workload
- SQL ensures reliable auth/user management
- MongoDB enables content scalability

### Negative:
- Increased complexity from polyglot persistence
- Cross-database transactions become challenging
- Requires expertise in both database types
- Potential data synchronization challenges