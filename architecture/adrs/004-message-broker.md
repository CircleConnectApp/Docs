# ADR 004: Message Broker - Kafka/RabbitMQ

## Status
Proposed

## Context
Need real-time communication for:
- Notifications
- Event-driven workflows
- Decoupled services

## Decision
Use either Kafka or RabbitMQ for:
- Notification events
- Post/story updates
- Cross-service communication

## Consequences
### Positive:
- Asynchronous processing
- Better fault tolerance
- Scalable event handling 

### Negative:
- Additional infrastructure
- Learning curve
- Potential message ordering issues