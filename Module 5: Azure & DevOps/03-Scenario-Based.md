# 🔥 Module 5: Azure & DevOps — Scenario-Based Questions

**Target Role:** .NET Full Stack Developer (3–5 yrs)  
**Focus:** Real-world scenarios + structured answers (Detection → Analysis → Fix → Prevention)

---

# 📑 Table of Contents

1. Production & Performance Issues  
2. CI/CD & Deployment  
3. Security & Secrets  
4. Scalability & Cost Optimization  
5. Microservices & Distributed Systems  
6. Kubernetes & Containers  
7. Database & Data Handling  
8. Monitoring & Observability  

---

# 🚨 1. Production & Performance Issues

## 🔹 Scenario 1: API latency increased (500ms → 5s)

**Detection:**
- Check Application Insights → Live Metrics  
- Identify slow endpoints (P95 latency)

**Analysis:**
- Inspect dependencies:
  - SQL queries  
  - External APIs  
- Check recent deployments  

**Fix:**
- Scale out App Service  
- Enable caching (Redis)

**Root Cause:**
- Fix N+1 queries  
- Optimize SQL  

**Prevention:**
- Add latency alerts  
- Add performance tests in CI/CD  

---

## 🔹 Scenario 2: High error rate after deployment

**Detection:**
- Alerts triggered (error spike)

**Fix (Immediate):**
- Rollback using deployment slots  

**Analysis:**
- Check exceptions in Application Insights  

**Prevention:**
- Add smoke tests  
- Improve test coverage  

---

## 🔹 Scenario 3: App Service CPU at 100%

**Detection:**
- Azure Metrics → CPU usage  

**Analysis:**
- Use Application Insights Profiler  
- Identify heavy endpoints  

**Fix:**
- Scale out instances  

**Root Cause:**
- Optimize loops / LINQ  

**Prevention:**
- Configure CPU alerts  

---

## 🔹 Scenario 4: Memory leak in production

**Approach:**
- Capture memory dump  
- Analyze heap usage  
- Identify object retention  
- Fix improper disposal  

---

# ⚙️ 2. CI/CD & Deployment

## 🔹 Scenario 5: Design CI/CD pipeline

**Flow:**
1. Code commit  
2. Build + Unit tests  
3. Artifact creation  
4. Deploy to staging  
5. Smoke tests  
6. Approval  
7. Production deployment (slot swap)  

---

## 🔹 Scenario 6: Deployment failed

**Approach:**
- Rollback using slot swap  
- Verify system stability  
- Check logs  
- Fix and redeploy  

---

## 🔹 Scenario 7: Pipeline is slow

**Optimization:**
- Parallel execution  
- Dependency caching  
- Incremental builds  
- Skip unnecessary steps  

---

## 🔹 Scenario 8: Zero downtime deployment

**Solution:**
- Use Deployment Slots  
- Blue-Green deployment  

---

# 🔐 3. Security & Secrets

## 🔹 Scenario 9: Secret exposed in repository

**Action Plan:**
1. Rotate credentials immediately  
2. Remove from Git history  
3. Move secrets to Key Vault  
4. Enable secret scanning  

---

## 🔹 Scenario 10: Secure application

**Solution:**
- Managed Identity  
- Key Vault  
- RBAC  
- Private Endpoints  

---

# 📈 4. Scalability & Cost Optimization

## 🔹 Scenario 11: Traffic spike

**Solution:**
- Enable auto-scaling  
- Use load balancer  
- Add caching (Redis)  

---

## 🔹 Scenario 12: Azure cost increased

**Approach:**
- Analyze Azure Cost Management  
- Identify expensive resources  
- Optimize:
  - Scale down unused services  
  - Use reserved instances  

---

## 🔹 Scenario 13: Improve scalability

**Solution:**
- Use microservices  
- Add caching  
- Use CDN  
- Horizontal scaling  

---

# 🔁 5. Microservices & Distributed Systems

## 🔹 Scenario 14: Service communication failure

**Solution:**
- Retry with exponential backoff  
- Circuit breaker (Polly)  
- Use message queues  

---

## 🔹 Scenario 15: Distributed transactions

**Solution:**
- Saga pattern  
- Event-driven architecture  

---

## 🔹 Scenario 16: External API failure

**Solution:**
- Retry  
- Timeout  
- Circuit breaker  
- Fallback  

---

# ☸️ 6. Kubernetes & Containers

## 🔹 Scenario 17: Pod CrashLoopBackOff

**Approach:**
- Check logs  
- Check pod description  
- Fix:
  - Config errors  
  - Memory issues  
  - Application bugs  

---

## 🔹 Scenario 18: Kubernetes deployment fails

**Approach:**
- Validate YAML  
- Check container image  
- Verify environment variables  

---

## 🔹 Scenario 19: Container not starting

**Solution:**
- Check logs  
- Verify entry point  
- Validate dependencies  

---

# 🗄️ 7. Database & Data Handling

## 🔹 Scenario 20: SQL connection pool exhausted

**Solution:**
- Correct DbContext lifetime  
- Optimize queries  
- Enable pooling  

---

## 🔹 Scenario 21: Data inconsistency

**Solution:**
- Cache invalidation strategy  
- Ensure consistency pattern  

---

## 🔹 Scenario 22: Database performance issue

**Solution:**
- Add indexes  
- Optimize queries  
- Reduce joins  

---

## 🔹 Scenario 23: Zero downtime DB migration

**Solution (Expand-Contract):**
1. Add new schema  
2. Update application  
3. Migrate data  
4. Remove old schema  

---

# 📊 8. Monitoring & Observability

## 🔹 Scenario 24: Monitoring strategy

**Solution:**
- Application Insights  
- Logging (Serilog)  
- Alerts  
- Dashboards  

---

## 🔹 Scenario 25: Debug slow API

**Approach:**
- Check Application Insights  
- Identify bottleneck  
- Optimize  

---

## 🔹 Scenario 26: High error rate

**Solution:**
- Alerts  
- Logs  
- Rollback  

---

## 🔹 Scenario 27: Distributed tracing issue

**Solution:**
- Use correlation ID  
- Track requests across services  

---

## 🔹 Scenario 28: Logging strategy

**Solution:**
- Structured logging  
- Centralized logs  
- Correlation IDs  

---
