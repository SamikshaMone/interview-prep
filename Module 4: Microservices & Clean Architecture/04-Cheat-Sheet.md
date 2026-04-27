# Module 4: Microservices & Clean Architecture
# 04-Cheat-Sheet.md

Purpose: Fast and deep revision before interview
Level: Mid–Senior (.NET Full Stack)

---

# 1. Microservices Fundamentals

Microservices:
- Small, independent services
- Each service owns its database
- Communicate over network

Key Benefits:
- Independent deployment
- Scalability
- Fault isolation

Key Challenges:
- Network latency
- Data consistency
- Debugging complexity

---

# 2. Monolith vs Microservices

Monolith:
- Simple
- Shared database
- Hard to scale

Microservices:
- Scalable
- Independent
- Complex

Interview Line:
Used microservices for scalability and independent deployment.

---

# 3. Migration Strategy

Strangler Pattern:
- Gradual migration
- Replace modules step by step

Steps:
- Identify bounded contexts
- Extract services
- Route via API Gateway

---

# 4. Clean Architecture

Layers:
- Domain (business logic)
- Application (use cases)
- Infrastructure (DB, external)
- Presentation (API)

Rule:
Inner layers should not depend on outer layers

---

# 5. Domain-Driven Design (DDD)

Entity:
- Has identity

Value Object:
- Immutable, no identity

Aggregate:
- Group of related entities

Bounded Context:
- Defines service boundary

---

# 6. CQRS

Separate:
- Commands (write)
- Queries (read)

Benefits:
- Better performance
- Scalability

Drawback:
- Increased complexity

---

# 7. MediatR

Purpose:
- Decouples logic

Flow:
Controller → MediatR → Handler

Benefits:
- Clean code
- Testable

---

# 8. Inter-service Communication

REST:
- Simple
- Synchronous

gRPC:
- High performance
- Binary protocol

Message Queue:
- Asynchronous
- Event-driven

---

# 9. Communication Decision

Use REST:
- Simple APIs

Use gRPC:
- High performance

Use Message Queue:
- Async processing

---

# 10. Saga Pattern

Used for:
- Distributed transactions

Types:
- Choreography
- Orchestration

---

# 11. Outbox Pattern

Problem:
- DB updated but event lost

Solution:
- Store event in DB
- Publish later

---

# 12. Resiliency

Patterns:
- Retry
- Circuit Breaker
- Timeout
- Fallback

Tool:
- Polly

---

# 13. API Gateway

Responsibilities:
- Routing
- Authentication
- Aggregation

Benefits:
- Single entry point
- Simplifies client

---

# 14. Service Discovery

Purpose:
- Find services dynamically

Types:
- Client-side
- Server-side

Examples:
- Kubernetes DNS

---

# 15. Observability

Logging:
- Centralized logs

Monitoring:
- Metrics

Tracing:
- Track request flow

---

# 16. Key Performance Strategies

- Use async communication
- Reduce service calls
- Use caching
- Scale independently

---

# 17. Common Problems & Solutions

Service failure:
- Retry + circuit breaker

Data inconsistency:
- Saga + eventual consistency

High latency:
- Cache + async messaging

---

# 18. Trade-offs to Remember

- Consistency vs availability
- Simplicity vs scalability
- Sync vs async communication

---

# 19. Golden Answer Structure

1. Problem
2. Approach
3. Solution
4. Trade-off
5. Result

---

# 20. Must Use Interview Lines

- Used Saga pattern for distributed transactions
- Implemented Outbox pattern for reliable messaging
- Used Polly for resiliency
- Applied CQRS for scalability
- Used API Gateway for centralized routing

---

# 21. Example Strong Answer

We designed microservices using bounded contexts, implemented CQRS with MediatR, used REST and message queues for communication, applied Polly for resilience, and used API Gateway for routing, which improved scalability and fault tolerance.

---

# End of File
