# 🎯 Module 5: Azure & DevOps — Interview Questions with Answers

---

# ☁️ SECTION A: Azure Fundamentals

## Q1. What is Cloud Computing?

📖 Definition:  
Cloud computing provides computing resources (servers, storage, DB) over the internet.

🎯 Answer:  
“In our HR project, we used Azure PaaS services like App Service and Azure SQL so we didn’t have to manage infrastructure.”

---

## Q2. Explain IaaS, PaaS, SaaS, FaaS

🎯 Answer:
- IaaS → Azure VM (you manage OS)
- PaaS → App Service (you manage app)
- SaaS → Microsoft 365
- FaaS → Azure Functions

---

## Q3. What is a Resource Group?

📖 Logical container for resources.

🎯 Answer:  
“We group resources by environment like dev, staging, and prod for easier management.”

---

## Q4. Can a resource belong to multiple resource groups?

❌ No — only one.

---

## Q5. What is an Azure Region?

📖 Geographic location where resources are hosted.

---

## Q6. What are Availability Zones?

📖 Multiple datacenters in a region for high availability.

---

## Q7. ARM vs Bicep?

🎯 Answer:  
“Bicep is preferred because it is simpler and more readable than ARM JSON.”

---

## Q8. Azure Policy vs RBAC?

- RBAC → Who can access  
- Policy → What can be created  

---

## Q9. What is Azure Advisor?

📖 Provides recommendations for performance, cost, and security.

---

## Q10. What is Azure Service Health?

📖 Shows outages affecting resources.

---

# 🌐 SECTION B: Azure App Services

## Q11. What is Azure App Service?

📖 PaaS platform to host APIs and web apps.

🎯 Answer:  
“We host our .NET APIs on App Service with auto-scaling and SSL.”

---

## Q12. What are Deployment Slots?

📖 Staging environments for deployment.

🎯 Answer:  
“We deploy to staging → test → swap → production with zero downtime.”

---

## Q13. How does slot swap work?

📖 Swaps staging with production.

🎯 Answer:  
“It ensures zero downtime and quick rollback.”

---

## Q14. What is Always On?

📖 Keeps app warm.

---

## Q15. Vertical vs Horizontal scaling?

- Vertical → Increase size  
- Horizontal → Increase instances  

---

## Q16. What is Kudu?

📖 Debugging console for App Service.

---

## Q17. What is VNet integration?

📖 Connect App Service to private network.

---

## Q18. What is Private Endpoint?

📖 Secure private access to resources.

---

## Q19. Authentication in App Service?

📖 Built-in auth using Azure AD, Google, etc.

---

## Q20. Backup in App Service?

📖 Automated backups stored in storage account.

---

# ⚡ SECTION C: Azure Functions

## Q21. What is Azure Functions?

📖 Serverless compute service.

🎯 Answer:  
“We use Functions for async processing like background jobs.”

---

## Q22. Consumption vs Premium?

🎯 Answer:
- Consumption → Pay per execution  
- Premium → No cold start  

---

## Q23. What is Cold Start?

📖 Delay when function starts.

---

## Q24. How to avoid cold start?

🎯 Answer:
“Use Premium plan or keep function warm.”

---

## Q25. Triggers vs Bindings?

- Trigger → Starts function  
- Binding → Input/output  

---

## Q26. Common triggers?

- HTTP  
- Timer  
- Queue  

---

## Q27. What is Timer Trigger?

📖 Scheduled execution.

---

## Q28. What are Durable Functions?

📖 Used for long-running workflows.

---

## Q29. Function security?

📖 Use keys, API Management, or Azure AD.

---

## Q30. Max execution time?

- Consumption → 10 min  
- Premium → Unlimited  

---

# 🗄️ SECTION D: Azure SQL

## Q31. Azure SQL vs SQL Server?

🎯 Answer:  
“Azure SQL is PaaS with built-in HA and auto backups.”

---

## Q32. DTU vs vCore?

- DTU → bundled  
- vCore → flexible  

---

## Q33. High availability options?

- Replication  
- Failover groups  

---

## Q34. What is Geo-replication?

📖 Secondary DB in another region.

---

## Q35. What is Elastic Pool?

📖 Shared resources for multiple DBs.

---

## Q36. What is Serverless DB?

📖 Auto scaling + auto pause.

---

## Q37. SQL Security features?

- TDE  
- Firewall  
- Azure AD  

---

## Q38. What is Indexing?

📖 Improves query performance.

---

## Q39. Clustered vs Non-clustered?

- Clustered → sorted data  
- Non-clustered → separate index  

---

## Q40. N+1 problem?

🎯 Answer:  
“Multiple DB calls due to lazy loading — solved using Include() in EF Core.”

---
# 🎯 Module 5: Azure & DevOps — Interview Questions with Answers (Part 2)

---

# 🔐 SECTION E: Azure Key Vault & Security

## Q41. What is Azure Key Vault?

📖 Definition:  
A cloud service to securely store secrets, keys, and certificates.

🎯 Answer:  
“We store connection strings, API keys, and secrets in Key Vault instead of appsettings to improve security.”

---

## Q42. What are Secrets, Keys, and Certificates?

- Secrets → Passwords, connection strings  
- Keys → Encryption keys  
- Certificates → SSL/TLS certs  

---

## Q43. What is Managed Identity?

📖 Identity provided by Azure to access resources securely.

🎯 Answer:  
“We use Managed Identity so our app can access Key Vault without storing credentials.”

---

## Q44. System-assigned vs User-assigned Managed Identity?

- System → Linked to resource lifecycle  
- User → Reusable across resources  

---

## Q45. RBAC vs Access Policies in Key Vault?

- RBAC → Role-based access (modern approach)  
- Access Policies → Older method  

---

## Q46. What is Soft Delete?

📖 Deleted secrets can be recovered.

---

## Q47. What is Purge Protection?

📖 Prevents permanent deletion.

---

## Q48. How to access Key Vault in .NET?

🎯 Answer:  
“Using DefaultAzureCredential and Azure SDK to fetch secrets securely.”

---

## Q49. How do you rotate secrets?

🎯 Answer:  
“Automate rotation using Azure Functions or scheduled jobs.”

---

## Q50. Key Vault network security?

- Firewall rules  
- Private endpoint  

---

# 📊 SECTION F: Monitoring & Application Insights

## Q51. What is Application Insights?

📖 Monitoring tool for applications.

---

## Q52. What does it track?

- Requests  
- Dependencies  
- Exceptions  
- Logs  

---

## Q53. What is Distributed Tracing?

📖 Tracks a request across services.

🎯 Answer:  
“We use correlation IDs to trace a request from frontend → API → DB.”

---

## Q54. What is a Correlation ID?

📖 Unique ID for tracking request across systems.

---

## Q55. What is KQL?

📖 Query language for logs.

---

## Q56. Example KQL query for slow APIs?

```kql
requests
| summarize avg(duration) by name
```

---
## Q57. What are Alerts?

📖 **Definition:**  
Alerts notify when specific conditions are met.

🎯 **Answer:**  
“We configure alerts for high CPU, slow response time, and error spikes.”

---

## Q58. Types of Alerts?

- Metric alerts  
- Log alerts  
- Activity alerts  

---

## Q59. What is Live Metrics?

📖 **Definition:**  
Real-time monitoring dashboard.

---

## Q60. What are Health Checks?

📖 **Definition:**  
Endpoints used to verify system health.

🎯 **Answer:**  
“We expose `/health` endpoints to monitor DB, cache, and external APIs.”

---

## Q61. Serilog integration?

🎯 **Answer:**  
“We use Serilog to generate structured logs and send them to Application Insights.”

---

## Q62. What is Sampling?

📖 **Definition:**  
Reduces telemetry volume to optimize performance.

---

## Q63. Why use Application Insights?

🎯 **Answer:**  
“It helps monitor performance, track failures, and debug production issues.”

---

## Q64. How to debug slow API?

🎯 **Answer:**

1. Check Application Insights  
2. Identify slow endpoints  
3. Analyze dependencies (SQL/HTTP)  
4. Optimize queries or scale  

---

## Q65. What is Dependency Tracking?

📖 **Definition:**  
Tracks external calls like SQL, HTTP APIs, Redis.

---

# ⚙️ SECTION G: Azure DevOps & CI/CD

## Q66. What is CI/CD?

- CI → Continuous Integration (Build + Test)  
- CD → Continuous Delivery (Deploy)  

---

## Q67. CI vs CD vs Continuous Deployment?

- CI → Code integration  
- CD → Deploy with approval  
- Continuous Deployment → Fully automated  

---

## Q68. Azure DevOps Services?

- Boards  
- Repos  
- Pipelines  
- Artifacts  

---

## Q69. What is a Pipeline?

📖 **Definition:**  
Automated workflow for building and deploying applications.

---

## Q70. YAML vs Classic Pipeline?

- YAML → Code-based (preferred)  
- Classic → UI-based  

---

## Q71. What are Pipeline Stages?

- Build  
- Test  
- Deploy  

---

## Q72. What are Variable Groups?

📖 **Definition:**  
Reusable variables across pipelines.

---

## Q73. What is Service Connection?

📖 **Definition:**  
Secure connection to Azure or external services.

---

## Q74. Self-hosted vs Microsoft-hosted agents?

- Microsoft-hosted → Managed by Azure  
- Self-hosted → Custom infrastructure  

---

## Q75. What are Approvals & Gates?

📖 **Definition:**  
Checks before deployment.

🎯 **Answer:**  
“We use manual approval before production deployment.”

---

## Q76. Deployment Strategies?

- Blue-Green  
- Canary  
- Rolling  

---

## Q77. Blue-Green vs Canary?

- Blue-Green → Switch environments instantly  
- Canary → Gradual rollout  

---

## Q78. Git Branching Strategy?

🎯 **Answer:**  
“We use feature branches and merge via pull requests to the main branch.”

---

## Q79. What are PR Policies?

- Code review  
- Build validation  
- Code coverage  

---

## Q80. Database migration in CI/CD?

🎯 **Answer:**  
“We use EF Core migrations and ensure backward compatibility during deployment.”

---

# 🎯 Module 5: Azure & DevOps — Interview Questions with Answers (Part 3)

---

# 🔄 SECTION H: GitHub Actions

## Q81. What is GitHub Actions?

📖 **Definition:**  
CI/CD tool integrated with GitHub to automate workflows.

🎯 **Answer:**  
“We use GitHub Actions to automate build, test, and deployment pipelines directly from our repository.”

---

## Q82. Workflow structure in GitHub Actions?

📖 **Definition:**  
A workflow is defined in a YAML file and consists of:
- Events (`on`)
- Jobs
- Steps

---

## Q83. GitHub Actions vs Azure DevOps?

- GitHub Actions → Native GitHub CI/CD  
- Azure DevOps → Full DevOps suite  

🎯 **Answer:**  
“We use GitHub Actions for lightweight CI/CD and Azure DevOps for enterprise pipelines.”

---

## Q84. Secrets vs Variables?

- Secrets → Encrypted  
- Variables → Plain text  

---

## Q85. What is Matrix Strategy?

📖 **Definition:**  
Runs jobs in parallel across multiple configurations.

---

## Q86. What are Reusable Workflows?

📖 **Definition:**  
Workflows that can be reused across multiple repositories.

---

# 🐳 SECTION I: Docker

## Q87. What is Docker?

📖 **Definition:**  
Containerization platform to package applications with dependencies.

---

## Q88. Containers vs Virtual Machines?

| Feature | Container | VM |
|--------|----------|----|
| Size | MB | GB |
| Speed | Fast | Slow |

---

## Q89. What is a Dockerfile?

📖 **Definition:**  
File containing instructions to build Docker image.

---

## Q90. What is Multi-stage build?

📖 **Definition:**  
Uses multiple stages to reduce image size.

🎯 **Answer:**  
“Multi-stage builds reduce final image size and improve security.”

---

## Q91. Common Docker commands?

- `docker build`  
- `docker run`  
- `docker ps`  
- `docker logs`  

---

## Q92. What is Docker Compose?

📖 **Definition:**  
Tool to run multi-container applications.

---

## Q93. Volumes vs Bind Mounts?

- Volume → Managed by Docker  
- Bind Mount → Host file system  

---

## Q94. Docker Networking?

📖 **Definition:**  
Allows communication between containers.

---

## Q95. How to reduce Docker image size?

🎯 **Answer:**
- Use Alpine base image  
- Multi-stage builds  
- Remove unnecessary files  

---

## Q96. Docker security best practices?

🎯 **Answer:**
- Scan images  
- Avoid root user  
- Use minimal base images  

---

# ☸️ SECTION J: Kubernetes (AKS)

## Q97. What is Kubernetes?

📖 **Definition:**  
Container orchestration platform.

---

## Q98. What is AKS?

📖 **Definition:**  
Azure-managed Kubernetes service.

---

## Q99. Pod vs Node?

- Pod → Smallest unit  
- Node → VM running pods  

---

## Q100. Deployment vs ReplicaSet?

- Deployment → Manages pods  
- ReplicaSet → Maintains replicas  

---

## Q101. Service types in Kubernetes?

- ClusterIP  
- NodePort  
- LoadBalancer  

---

## Q102. What is Ingress?

📖 **Definition:**  
Handles HTTP routing.

---

## Q103. What is HPA?

📖 **Definition:**  
Auto-scales pods based on CPU/memory.

---

## Q104. Rolling update vs Canary?

- Rolling → Gradual update  
- Canary → Partial rollout  

---

## Q105. ConfigMap vs Secret?

- ConfigMap → Non-sensitive data  
- Secret → Sensitive data  

---

## Q106. Common kubectl commands?

- `kubectl get pods`  
- `kubectl logs`  
- `kubectl describe`  

---

# 🔁 SECTION K: Resilience & Reliability

## Q107. What is Polly?

📖 **Definition:**  
Resilience library for handling failures.

---

## Q108. Retry vs Circuit Breaker?

- Retry → Retry failed calls  
- Circuit Breaker → Stop failing service  

---

## Q109. What is Timeout Policy?

📖 **Definition:**  
Stops request if it exceeds time limit.

---

## Q110. What is Bulkhead Pattern?

📖 **Definition:**  
Limits concurrent requests to avoid overload.

---

## Q111. What is Fallback?

📖 **Definition:**  
Return alternate response if failure occurs.

---

## Q112. What is OpenTelemetry?

📖 **Definition:**  
Observability framework for logs, traces, and metrics.

---

## Q113. Rate limiting in .NET 8?

🎯 **Answer:**  
“Used middleware to limit requests per user to prevent abuse.”

---

## Q114. What is Idempotency?

📖 **Definition:**  
Same request produces same result.

---

## Q115. Why is Idempotency important?

🎯 **Answer:**  
“Prevents duplicate operations during retries.”

---

## Q116. What is Chaos Engineering?

📖 **Definition:**  
Testing system resilience by introducing failures.

---

## Q117. What is Graceful Shutdown?

📖 **Definition:**  
Allows app to finish processing before shutting down.

---

## Q118. Retry vs Circuit Breaker order?

🎯 **Answer:**  
“Retry inside circuit breaker so failures are counted properly.”

---

## Q119. What is Exponential Backoff?

📖 **Definition:**  
Increasing delay between retries.

---

## Q120. Why use Resilience patterns?

🎯 **Answer:**  
“To ensure system stability under failures and high load.”

---
# 🎯 Module 5: Azure & DevOps — Interview Questions with Answers (Part 4)

---

# 🔥 SECTION L: Scenario-Based Questions (MOST IMPORTANT)

---

## Q121. API latency increased suddenly in production. How do you debug?

🎯 **Answer:**

1. Check Application Insights (Live Metrics)  
2. Identify slow endpoints (P95 latency)  
3. Analyze dependencies (SQL, HTTP calls)  
4. Check recent deployments  
5. Scale out if needed  
6. Optimize queries or fix code  

---

## Q122. Design CI/CD pipeline for microservices.

🎯 **Answer:**

- Separate pipelines per service  
- Build → Test → Docker build → Push to registry  
- Deploy to staging → Smoke tests  
- Manual approval → Production  
- Use versioning and rollback strategy  

---

## Q123. Production errors increased after deployment. What do you do?

🎯 **Answer:**

1. Rollback using deployment slots  
2. Monitor error rate  
3. Identify root cause  
4. Fix and redeploy  
5. Add test coverage to prevent recurrence  

---

## Q124. Secret leaked in repository. What is your action plan?

🎯 **Answer:**

1. Rotate credentials immediately  
2. Remove from repo history  
3. Move secrets to Key Vault  
4. Enable secret scanning  

---

## Q125. How to achieve zero-downtime DB migration?

🎯 **Answer:**

Use **Expand-Contract pattern**:

1. Add new schema  
2. Update application  
3. Migrate data  
4. Remove old schema  

---

## Q126. Redis cache goes down. What happens?

🎯 **Answer:**

- Use fallback to DB  
- Avoid app crash  
- Log failure  
- Use retry with Polly  

---

## Q127. Azure cost suddenly increased. How do you investigate?

🎯 **Answer:**

1. Use Azure Cost Management  
2. Identify high-cost resources  
3. Check scaling issues  
4. Optimize unused resources  

---

## Q128. Pipeline takes too long. How to optimize?

🎯 **Answer:**

- Parallel jobs  
- Cache dependencies  
- Skip unnecessary steps  
- Use incremental builds  

---

## Q129. App Service CPU is 100%. What to do?

🎯 **Answer:**

1. Check App Insights  
2. Identify heavy endpoints  
3. Optimize code  
4. Scale out instances  

---

## Q130. Design Disaster Recovery (DR) strategy.

🎯 **Answer:**

- Multi-region deployment  
- Geo-replication for DB  
- Backup strategy  
- Failover mechanism  

---

## Q131. SQL connection pool exhausted. How to fix?

🎯 **Answer:**

- Use proper DbContext scope  
- Enable connection pooling  
- Optimize queries  

---

## Q132. External API is unreliable. How to handle?

🎯 **Answer:**

- Retry with exponential backoff  
- Circuit breaker (Polly)  
- Timeout policy  
- Fallback response  

---

## Q133. Pipeline passes but production fails. Why?

🎯 **Answer:**

- Environment mismatch  
- Missing configs  
- Data-related issues  

---

## Q134. Redis vs DB inconsistency issue.

🎯 **Answer:**

- Use cache-aside pattern  
- Invalidate cache properly  
- Ensure consistency  

---

## Q135. Improve system scalability.

🎯 **Answer:**

- Use auto-scaling  
- Load balancing  
- Caching (Redis)  

---

## Q136. High error rate in production.

🎯 **Answer:**

1. Check logs  
2. Identify failing endpoints  
3. Rollback if needed  
4. Fix root cause  

---

## Q137. API response time degraded.

🎯 **Answer:**

- Check DB queries  
- Optimize indexes  
- Use caching  

---

## Q138. Microservices communication failure.

🎯 **Answer:**

- Retry  
- Circuit breaker  
- Message queue  

---

## Q139. Handle high traffic spike.

🎯 **Answer:**

- Auto-scale  
- Load balancer  
- CDN  

---

## Q140. Design monitoring strategy.

🎯 **Answer:**

- Application Insights  
- Alerts  
- Logging  
- Dashboards  

---

## Q141. Kubernetes pod crash (CrashLoopBackOff).

🎯 **Answer:**

- Check logs  
- Fix config issues  
- Check memory limits  

---

## Q142. Deployment rollback strategy.

🎯 **Answer:**

- Use deployment slots  
- Use versioning  
- Quick rollback  

---

## Q143. Secure application in Azure.

🎯 **Answer:**

- Key Vault  
- Managed Identity  
- RBAC  

---

## Q144. Improve API performance.

🎯 **Answer:**

- Optimize queries  
- Use caching  
- Reduce payload size  

---

## Q145. Reduce infrastructure cost.

🎯 **Answer:**

- Use serverless  
- Scale down unused resources  
- Reserved instances  

---

## Q146. Debug memory leak.

🎯 **Answer:**

- Use profiling tools  
- Analyze heap  
- Fix object references  

---

## Q147. Design logging strategy.

🎯 **Answer:**

- Structured logging (Serilog)  
- Centralized logging  
- Correlation IDs  

---

## Q148. Handle distributed transactions.

🎯 **Answer:**

- Saga pattern  
- Event-driven architecture  

---

## Q149. Ensure system resilience.

🎯 **Answer:**

- Retry  
- Circuit breaker  
- Fallback  

---

## Q150. Improve deployment reliability.

🎯 **Answer:**

- CI/CD pipelines  
- Automated testing  
- Monitoring  

---

## Q151. API security best practices.

🎯 **Answer:**

- JWT authentication  
- HTTPS  
- Rate limiting  

---

## Q152. Handling throttling errors.

🎯 **Answer:**

- Retry with backoff  
- Rate limiting  

---

## Q153. Improve database performance.

🎯 **Answer:**

- Indexing  
- Query optimization  
- Caching  

---

## Q154. Multi-region deployment challenges.

🎯 **Answer:**

- Data consistency  
- Latency  
- Failover  

---

## Q155. Debug failing Kubernetes deployment.

🎯 **Answer:**

- Check logs  
- Verify config  
- Check image  

---

## Q156. Handling API versioning.

🎯 **Answer:**

- Use versioning in routes  
- Maintain backward compatibility  

---

## Q157. Improve frontend performance.

🎯 **Answer:**

- Lazy loading  
- Code splitting  

---

## Q158. Event-driven architecture benefits.

🎯 **Answer:**

- Loose coupling  
- Scalability  

---

## Q159. Handling concurrency issues.

🎯 **Answer:**

- Optimistic concurrency  
- Locks  

---

## Q160. How to prepare for production readiness?

🎯 **Answer:**

- Monitoring  
- Logging  
- Security  
- Scalability  

---

# 🎯 FINAL INTERVIEW STRATEGY

- Always give **real project examples**
- Use strong keywords:
  - Zero downtime  
  - Managed Identity  
  - Auto-scaling  
  - App Insights debugging  

---

