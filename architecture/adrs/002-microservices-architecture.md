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
2. **User Service**: Go with Gin  
3. **Community Service**: Node.js with Express  
4. **Post Service**: Go with Gin  
5. **Story Service**: Node.js  
6. **Feed Service**: Go with Gin  
7. **Search Service**: Go with Gin  
8. **Admin Service**: Node.js  
9. **Notification Service**: Node.js  

## Justification

### Authentication Service (Python/FastAPI)
- **Security**: Excellent security libraries and built-in OAuth2/JWT support
- **Development Speed**: Rapid development with Python's simplicity
- **Performance**: FastAPI provides near-Go performance for auth workflows

### User Service (Go/Gin)
- **Performance**: Golang excels at concurrent user preference management
- **Reliability**: Strong typing reduces errors in core user data operations
- **Efficiency**: Optimal for handling user-community relationships at scale

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

### Feed Service (Go/Gin)
- **Performance**: Golang's speed crucial for personalized feed generation
- **Concurrency**: Efficiently handles real-time feed updates and recommendations

### Search Service (Go/Gin)
- **Indexing Performance**: Go's speed benefits content indexing operations
- **Scalability**: Handles large-scale search queries efficiently

### Admin Service (Node.js)
- **Real-time Monitoring**: Event-driven model suits admin dashboards
- **Development Speed**: Rapid iteration for moderation tools

### Notification Service (Node.js)
- **Real-time Performance**: Event loop ideal for push notifications  
- **Scalability**: Handles high volumes of ephemeral notifications

## Consequences
### Positive:
- Optimal language/framework per service's needs 
- Fault isolation through technical boundaries
- Performance-optimized services (Go for CPU-intensive, Node for I/O-bound)
- Clear separation of concerns

### Negative:
- Increased operational complexity
- Cross-service communication overhead
- Distributed system monitoring challenges