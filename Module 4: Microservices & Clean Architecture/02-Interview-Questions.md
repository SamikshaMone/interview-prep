# Module 4: Microservices & Clean Architecture
# 02-Interview-Questions.md (Extended)

Level: Mid–Senior (.NET Full Stack)
Focus: Concepts + Trade-offs + Real-world reasoning

---

# Section A: Microservices Fundamentals

## Q1. What is Microservices Architecture?
Small, independent services communicating over a network, each owning its data.

## Q2. Monolith vs Microservices?
Monolith: single deployable, shared DB.
Microservices: independent deployables, per-service DB.
Trade-off: simplicity vs scalability/complexity.

## Q3. When should you use microservices?
Large domains, multiple teams, need for independent scaling and deployments.

## Q4. When should you avoid microservices?
Small apps, tight timelines, limited team maturity.

## Q5. What are key characteristics of microservices?
Independence, decentralization, automation, resilience.

## Q6. What are common challenges?
Latency, partial failures, data consistency, observability, ops complexity.

## Q7. What is bounded context?
A clear boundary where a specific domain model applies.

## Q8. Why database per service?
Prevents tight coupling; enables independent scaling and evolution.

## Q9. What is loose coupling?
Services interact via contracts, not shared internals.

## Q10. What is high cohesion?
Each service focuses on a single business capability.

---

# Section B: Migration (Monolith → Microservices)

## Q11. How to migrate a monolith?
Use strangler pattern; extract services incrementally.

## Q12. What is strangler pattern?
Gradually replace parts of monolith with microservices behind a facade.

## Q13. How to choose first service?
Pick a low-risk, high-value bounded context.

## Q14. How to handle shared database during migration?
Introduce APIs; avoid direct cross-service DB access.

## Q15. What are migration risks?
Data inconsistency, duplicate logic, routing complexity.

## Q16. How to manage routing during migration?
Use API Gateway to route to monolith or new services.

## Q17. How to ensure backward compatibility?
Version APIs; maintain contracts.

## Q18. How to split data?
Create service-owned schemas; replicate/transform as needed.

## Q19. How to test during migration?
Contract tests, integration tests, canary releases.

## Q20. How to roll back?
Use feature flags, routing switches, deployment slots.

---

# Section C: Clean Architecture

## Q21. What is Clean Architecture?
Separation of concerns with inward dependency rule.

## Q22. Layers?
Domain, Application, Infrastructure, Presentation.

## Q23. Dependency rule?
Outer layers depend on inner; inner has no knowledge of outer.

## Q24. Why use it?
Testability, maintainability, framework independence.

## Q25. Where do interfaces live?
In inner layers; implementations in outer layers.

## Q26. What goes in Domain layer?
Entities, value objects, domain services, invariants.

## Q27. What goes in Application layer?
Use cases, DTOs, interfaces, orchestrations.

## Q28. What goes in Infrastructure?
DB access, external services, messaging.

## Q29. What goes in Presentation?
Controllers, endpoints, UI concerns.

## Q30. Common mistake?
Leaking infrastructure into domain.

---

# Section D: Domain-Driven Design (DDD)

## Q31. What is DDD?
Design around domain models and ubiquitous language.

## Q32. Entity vs Value Object?
Entity has identity; Value Object is immutable without identity.

## Q33. What is Aggregate?
Cluster of entities with a root enforcing invariants.

## Q34. What is Aggregate Root?
Entry point for modifying an aggregate.

## Q35. What is Repository?
Abstraction to persist/retrieve aggregates.

## Q36. What is Domain Service?
Stateless logic not fitting an entity.

## Q37. What is Ubiquitous Language?
Shared language between devs and domain experts.

## Q38. What is Context Map?
Relationships between bounded contexts.

## Q39. What is Anti-Corruption Layer?
Translates between different domain models.

## Q40. When not to use full DDD?
Simple CRUD apps.

---

# Section E: CQRS & MediatR

## Q41. What is CQRS?
Separate models for reads and writes.

## Q42. Benefits?
Independent scaling, optimized reads.

## Q43. Drawbacks?
Complexity, data sync.

## Q44. When to use CQRS?
Read-heavy systems, complex domains.

## Q45. What is a Command?
Intent to change state.

## Q46. What is a Query?
Request to read data.

## Q47. What is MediatR?
Mediator library to decouple request handling.

## Q48. Why MediatR?
Cleaner controllers, testable handlers.

## Q49. Typical flow?
Controller → MediatR → Handler → Repo.

## Q50. Pitfall with MediatR?
Over-abstraction for simple cases.

---

# Section F: Inter-service Communication

## Q51. Synchronous vs Asynchronous?
Sync: blocking, simple. Async: decoupled, scalable.

## Q52. REST vs gRPC?
REST: text/HTTP, flexible. gRPC: binary, high performance.

## Q53. When to use REST?
Public APIs, simplicity.

## Q54. When to use gRPC?
Internal, low-latency, high-throughput.

## Q55. What are message queues?
Brokers for async messaging (RabbitMQ, Kafka).

## Q56. Benefits of async?
Resilience, decoupling, buffering.

## Q57. Drawbacks of async?
Eventual consistency, complexity.

## Q58. What is idempotency?
Same request → same effect.

## Q59. Why idempotency?
Safe retries without duplicates.

## Q60. How to implement idempotency?
Keys, dedup tables, upserts.

---

# Section G: Distributed Patterns

## Q61. What is Saga?
Manage distributed transactions via local steps.

## Q62. Choreography vs Orchestration?
Events vs central coordinator.

## Q63. When to use orchestration?
Complex flows, central visibility.

## Q64. What is compensation?
Undo step for failed transaction.

## Q65. What is Outbox pattern?
Store events in DB, publish reliably later.

## Q66. Why Outbox?
Avoid DB-write/message-publish inconsistency.

## Q67. How to implement Outbox?
Table + background publisher.

## Q68. What is Inbox pattern?
Deduplicate consumed messages.

## Q69. What is eventual consistency?
State converges over time.

## Q70. Trade-off vs strong consistency?
Availability and scalability vs immediacy.

---

# Section H: Resiliency

## Q71. What is resiliency?
Ability to handle failures gracefully.

## Q72. Retry pattern?
Retry transient failures with backoff.

## Q73. Circuit breaker?
Stop calls to failing dependency.

## Q74. Timeout?
Fail fast on slow dependencies.

## Q75. Bulkhead?
Isolate resources to limit blast radius.

## Q76. Fallback?
Alternate response when failure occurs.

## Q77. Why Polly?
Implement these patterns in .NET.

## Q78. Exponential backoff?
Increasing delay between retries.

## Q79. Where to apply?
Client calls to external services.

## Q80. Pitfall?
Retry storms without limits.

---

# Section I: API Gateway

## Q81. What is API Gateway?
Single entry point routing to services.

## Q82. Responsibilities?
Routing, auth, rate limiting, aggregation.

## Q83. Benefits?
Simplified clients, centralized concerns.

## Q84. Drawbacks?
Single point of failure if not scaled.

## Q85. What is aggregation?
Combining multiple service responses.

## Q86. Gateway patterns?
BFF (Backend for Frontend).

## Q87. Rate limiting?
Control request volume per client.

## Q88. Auth at gateway?
JWT validation, OAuth.

## Q89. Caching at gateway?
Cache common responses.

## Q90. Example tools?
YARP, Ocelot, Kong.

---

# Section J: Service Discovery

## Q91. What is service discovery?
Dynamic resolution of service instances.

## Q92. Client-side discovery?
Client queries registry.

## Q93. Server-side discovery?
Load balancer queries registry.

## Q94. Examples?
Kubernetes DNS, Consul.

## Q95. Health checks?
Ensure only healthy instances receive traffic.

## Q96. Load balancing types?
Round-robin, least connections.

## Q97. Why needed?
Dynamic scaling and IP changes.

## Q98. What is registration?
Service registers itself to registry.

## Q99. What is deregistration?
Remove unhealthy instances.

## Q100. Pitfall?
Stale registry entries.

---

# Section K: Observability

## Q101. What is observability?
Understand system via logs, metrics, traces.

## Q102. Logging?
Centralized structured logs.

## Q103. Metrics?
CPU, latency, error rate.

## Q104. Tracing?
Follow request across services.

## Q105. Correlation ID?
Unique ID across calls.

## Q106. Tools?
OpenTelemetry, Application Insights.

## Q107. Alerting?
Notify on thresholds.

## Q108. Sampling?
Reduce telemetry volume.

## Q109. Dashboards?
Visualize health.

## Q110. Pitfall?
Too much noise, no signal.

---

# Section L: Scenarios

## Q111. Service dependency failing?
Retry + circuit breaker + fallback.

## Q112. Need distributed transaction?
Use Saga with compensation.

## Q113. Inconsistent data across services?
Use Outbox + eventual consistency.

## Q114. High latency between services?
Cache, async messaging, reduce hops.

## Q115. Too many frontend calls?
Gateway aggregation or BFF.

## Q116. Need high performance?
Use gRPC for internal calls.

## Q117. Spike traffic?
Auto-scale, queue buffering.

## Q118. Debugging issue?
Central logs + tracing.

## Q119. Duplicate events processed?
Implement idempotency + inbox.

## Q120. Versioning APIs?
Use versioned routes/headers.

---

# Final Strategy

Always answer with:
1. Problem
2. Approach
3. Trade-off
4. Outcome

Example:
We used CQRS with MediatR to separate read/write paths, introduced message queues for async processing, and applied Polly for resilience, improving scalability and reducing failures.

---

# End of File
