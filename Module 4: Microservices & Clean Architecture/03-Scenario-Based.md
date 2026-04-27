# Module 4: Microservices & Clean Architecture
# 03-Scenario-Based.md

Level: Mid–Senior (.NET Full Stack)
Focus: Real-world scenarios, decision-making, architecture thinking

---

# How to Answer Scenario Questions

Always follow:

1. Identify problem
2. Analyze root cause
3. Provide solution
4. Mention trade-offs
5. Add prevention

---

# Section 1: Service Communication Issues

## Scenario 1: Service A depends on Service B, B is down

Approach:

- Use retry with exponential backoff
- Implement circuit breaker
- Provide fallback response
- Log failure

Trade-off:
Too many retries can overload system

---

## Scenario 2: High latency between services

Approach:

- Identify bottleneck
- Use caching
- Switch to async messaging
- Reduce network hops

---

## Scenario 3: Too many synchronous calls

Approach:

- Replace with message queue
- Use event-driven communication

---

## Scenario 4: Need high-performance communication

Approach:

- Use gRPC instead of REST
- Optimize payload size

---

# Section 2: Data Consistency Issues

## Scenario 5: Data inconsistency across services

Approach:

- Use Saga pattern
- Use eventual consistency

---

## Scenario 6: Transaction across multiple services

Approach:

- Avoid distributed transactions
- Use Saga with compensation logic

---

## Scenario 7: Message lost after DB update

Approach:

- Implement Outbox pattern
- Ensure reliable publishing

---

## Scenario 8: Duplicate messages processed

Approach:

- Use idempotency keys
- Implement deduplication

---

# Section 3: Performance & Scaling

## Scenario 9: One service overloaded

Approach:

- Scale horizontally
- Use load balancing
- Implement rate limiting

---

## Scenario 10: High traffic spike

Approach:

- Auto-scaling
- Use caching
- Queue incoming requests

---

## Scenario 11: Slow API response

Approach:

- Analyze DB queries
- Reduce service calls
- Optimize communication

---

## Scenario 12: Database bottleneck

Approach:

- Optimize queries
- Use caching
- Use read replicas

---

# Section 4: Migration & Architecture

## Scenario 13: Migrating monolith to microservices

Approach:

- Use strangler pattern
- Identify bounded contexts
- Extract services gradually

---

## Scenario 14: Breaking a large service

Approach:

- Analyze domain
- Split into smaller services
- Ensure loose coupling

---

## Scenario 15: Shared database issue

Approach:

- Introduce service-specific databases
- Use APIs instead of direct access

---

# Section 5: API Gateway Issues

## Scenario 16: Too many frontend API calls

Approach:

- Use API Gateway aggregation
- Implement BFF pattern

---

## Scenario 17: Authentication across services

Approach:

- Centralize at API Gateway
- Use JWT tokens

---

## Scenario 18: Rate limiting required

Approach:

- Implement at gateway level
- Protect backend services

---

# Section 6: Service Discovery

## Scenario 19: Service location unknown

Approach:

- Use service discovery (DNS, registry)

---

## Scenario 20: Dynamic scaling of services

Approach:

- Use Kubernetes or registry-based discovery

---

# Section 7: Resiliency & Failure Handling

## Scenario 21: External service failure

Approach:

- Retry
- Circuit breaker
- Timeout
- Fallback

---

## Scenario 22: Cascading failure

Approach:

- Use circuit breaker
- Isolate services (bulkhead pattern)

---

## Scenario 23: Long-running request

Approach:

- Use async processing
- Offload to queue

---

# Section 8: Observability & Debugging

## Scenario 24: Hard to debug microservices

Approach:

- Centralized logging
- Distributed tracing
- Use correlation IDs

---

## Scenario 25: Identify slow service

Approach:

- Use tracing tools
- Analyze latency metrics

---

## Scenario 26: Production issue debugging

Approach:

- Check logs
- Trace request flow
- Identify failing service

---

# Section 9: Security

## Scenario 27: Secure inter-service communication

Approach:

- Use HTTPS
- Mutual TLS (mTLS)

---

## Scenario 28: Unauthorized access

Approach:

- Validate JWT tokens
- Implement RBAC

---

# Section 10: Advanced Scenarios

## Scenario 29: Versioning services

Approach:

- Use API versioning
- Maintain backward compatibility

---

## Scenario 30: Rolling deployment failure

Approach:

- Rollback deployment
- Use blue-green strategy

---

## Scenario 31: Event ordering issue

Approach:

- Use ordered queues
- Add timestamps

---

## Scenario 32: Data duplication

Approach:

- Use unique constraints
- Validate before insert

---

## Scenario 33: Need audit logging

Approach:

- Centralized logging
- Store audit trails

---

## Scenario 34: High memory usage

Approach:

- Optimize services
- Reduce payload size

---

## Scenario 35: Tight coupling between services

Approach:

- Introduce async communication
- Use events instead of direct calls

---

# Final Interview Strategy

Always structure answer:

1. Problem identification
2. Root cause analysis
3. Solution
4. Trade-off
5. Prevention

Example:

Service dependency failure handled using retry and circuit breaker, ensuring system stability and preventing cascading failures.

---

# End of File
