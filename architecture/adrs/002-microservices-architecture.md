# ADR 002: Microservices Architecture

## Status
Accepted

## Context
The system requires:
- Independent scaling of features
- Optimal performance for different workloads
- Clear separation of concerns
- Fault isolation 

## Decision
Adopt microservices architecture with these services and technologies:

1. **Authentication Service**: Python with FastAPI
2. **Community Service**: Node.js with Express  
3. **Post Service**: Go with Gin  
4. **Story Service**: Node.js  
5. **Admin Service**: Java with Spring Boot  
6. **Notification Service**: Node.js  

## Justification

### Authentication Service (Python/FastAPI)
- **Performance**: FastAPI is one of the fastest Python frameworks (comparable to Node/Go)
- **Security**: Built-in OAuth2/JWT support matches our auth requirements
- **Developer Experience**: Rapid development with Python's simplicity 

### Community Service (Node.js/Express)
- **Flexibility**: Handles varied community operations (CRUD, joins, moderation)
- **Scalability**: Event-driven model suits high-concurrency social features  

### Post Service (Go/Gin) 
- **Concurrency**: Goroutines handle thousands of simultaneous likes/comments
- **Memory Efficiency**: Optimal for memory-intensive post operations
- **Stability**: Strong typing reduces runtime errors in core functionality

### Story Service (Node.js)
- **Temporal Nature**: Fits Node's event-driven model for 24-hour content 
- **Consistency**: Shared patterns with Community Service
- **Development Speed**: Quick iteration for time-sensitive features

### Admin Service (Java/Spring Boot)
- **Security**: Spring Security provides enterprise-grade protection  
- **Stability**: Battle-tested platform for critical admin operations
- **Tooling**: Excellent monitoring and management capabilities

### Notification Service (Node.js)
- **Real-time Performance**: Event loop ideal for push notifications  

## Consequences
### Positive:
- Optimal language/framework per service's needs 
- Fault isolation through technical boundaries

### Negative:
- Increased operational complexity