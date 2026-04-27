# 🚀 Module 5: Azure & DevOps — Complete Notes (FULL VERSION)

**Prepared for:** Full Stack .NET Developer (3–5 Years)  
**Goal:** Crack 15+ LPA interviews with strong Azure + DevOps + Real-world explanation  

---

# 📑 TABLE OF CONTENTS

1. Azure Fundamentals  
2. Azure App Services  
3. Azure Functions  
4. Azure SQL Database  
5. Azure Key Vault & Security  
6. Application Insights & Monitoring  
7. Azure DevOps & CI/CD  
8. GitHub Actions  
9. Docker & Containers  
10. Kubernetes (AKS)  
11. Resilience (Polly, OpenTelemetry, Rate Limiting)

---

# ☁️ 1. AZURE FUNDAMENTALS

## 🔹 Cloud Computing
Cloud computing = On-demand access to computing resources over internet.

### Service Models

| Model | You Manage | Azure Example |
|------|-----------|--------------|
| IaaS | OS + App | Azure VM |
| PaaS | App only | App Service |
| FaaS | Code only | Azure Functions |
| SaaS | Nothing | Microsoft 365 |

👉 **Interview Answer Tip:**
“We used PaaS (App Service + Azure SQL) to avoid infra management and focus on business logic.”

---

## 🔹 Resource Group
Logical container for Azure resources.

- Same lifecycle  
- Same permissions  
- Same billing  

👉 Example:
`rg-hr-prod` → App Service + SQL + Redis + Key Vault

---

## 🔹 Region & Availability Zone

- Region = geographical location  
- Availability Zone = multiple datacenters  

👉 Used for:
- High availability  
- Disaster recovery  

---

## 🔹 ARM vs Bicep vs Terraform

| Tool | Description |
|------|------------|
| ARM | JSON templates |
| Bicep | Simplified Azure-native |
| Terraform | Multi-cloud |

👉 **Best Practice: Use Bicep**

---

## 🔹 Subscription vs Tenant

- Tenant → Identity boundary  
- Subscription → Billing  
- Resource Group → Resources  

---

# 🌐 2. AZURE APP SERVICES

## 🔹 What is App Service?
PaaS for hosting:
- Web apps  
- APIs  
- Backend services  

---

## 🔹 Features
- Auto scaling  
- SSL support  
- Deployment slots  
- Built-in authentication  
- CI/CD integration  

---

## 🔹 App Service Plan

| Tier | Use Case |
|------|--------|
| Basic | Dev/Test |
| Standard | Production |
| Premium | High performance |
| Isolated | Enterprise |

👉 Multiple apps can share one plan → cost saving

---

## 🔹 Deployment Slots (VERY IMPORTANT)

- staging slot  
- production slot  

### Flow:
Deploy → Test → Swap → Production  

👉 Benefits:
- Zero downtime  
- Instant rollback  

👉 **Interview Line:**
“Used deployment slots for zero downtime deployment and quick rollback.”

---

## 🔹 Scaling

### Vertical Scaling
Increase VM size

### Horizontal Scaling
Increase number of instances

👉 Auto-scale triggers:
- CPU  
- Memory  
- HTTP queue  

---

## 🔹 Networking
- VNet integration  
- Private endpoint  
- IP restrictions  

---

# ⚡ 3. AZURE FUNCTIONS

## 🔹 What is Azure Functions?
Serverless compute service (event-driven)

---

## 🔹 Hosting Plans

| Plan | Description |
|------|------------|
| Consumption | Pay per execution |
| Premium | No cold start |
| Dedicated | Fixed |

---

## 🔹 Triggers
- HTTP  
- Timer  
- Queue  
- Blob  
- Service Bus  

---

## 🔹 Bindings
Input/output connections

---

## 🔹 Real Use Case
Employee request → Queue → Function → DB → Notification  

👉 Used for:
- Background jobs  
- Async workflows  

---

## 🔹 Durable Functions
Used for long-running workflows

Example:
- HR onboarding process  
- Multi-step approvals  

---

# 🗄️ 4. AZURE SQL DATABASE

## 🔹 Deployment Options

| Option | Use |
|--------|----|
| Azure SQL DB | Cloud apps |
| Managed Instance | Lift & shift |
| SQL VM | Full control |

---

## 🔹 Pricing Models

- DTU → Simple  
- vCore → Flexible  

👉 Prefer vCore

---

## 🔹 Performance Optimization

- Indexing  
- Query optimization  
- Avoid N+1  
- Use caching  

---

## 🔹 High Availability

- Built-in replication  
- Geo-replication  
- Failover groups  

---

## 🔹 Security

- TDE encryption  
- Azure AD authentication  
- Firewall rules  
- Private endpoint  

---

# 🔐 5. AZURE KEY VAULT

## 🔹 What is Key Vault?
Secure storage for:
- Secrets  
- Keys  
- Certificates  

---

## 🔹 Best Practice

✅ Use Managed Identity  
❌ Do NOT store secrets in code  

---

## 🔹 Example
Fetch connection string from Key Vault

---

## 🔹 Features

- Soft delete  
- Purge protection  
- RBAC access  

---

# 📊 6. APPLICATION INSIGHTS

## 🔹 What is it?
Monitoring tool for:
- Requests  
- Dependencies  
- Exceptions  
- Logs  

---

## 🔹 Metrics

- Response time  
- Failure rate  
- Throughput  

---

## 🔹 KQL Example

```kql
requests
| summarize avg(duration) by name
```

## 🔗 Distributed Tracing

Tracks request flow across services:

Frontend → API → Database  

👉 Helps in:
- Debugging latency issues  
- Identifying bottlenecks  
- End-to-end request visibility  

---

## 🔔 Alerts

Used for proactive monitoring.

### Common Alerts:
- Slow API response  
- High CPU usage  
- High error rate  

---

# ⚙️ 7. Azure DevOps & CI/CD

## 🔹 What is CI/CD?

- **CI (Continuous Integration)** → Build + Test  
- **CD (Continuous Delivery/Deployment)** → Deploy  

---

## 🔹 Pipeline Flow

1. Code commit  
2. Build  
3. Unit testing  
4. Deploy to staging  
5. Approval  
6. Production deployment  

---

## 🔹 YAML Example

```yaml
trigger:
  - main

steps:
  - script: dotnet build
  - script: dotnet test
```

## 🔹 Best Practices

- Maintain **code coverage > 80%**  
- Enforce **PR approvals**  
- Use **automated testing**  
- Always have a **rollback strategy**  

---

# 🔄 8. GitHub Actions

## 🔹 What is GitHub Actions?

CI/CD tool integrated with GitHub repositories.

---

## 🔹 Workflow Example

```yaml
on: push

jobs:
  build:
    runs-on: ubuntu-latest
Features
- Secrets management
- Matrix builds
- Reusable workflows
```
---

# 🔄 8. Docker

## 🔹 Why Docker?

- Lightweight
- Fast deployment
- Consistent environments

 ## 🔹 Docker vs Virtual Machine

| Feature | Container | VM |
|--------|----------|----|
| Size | MB | GB |
| Speed | Fast | Slow |

---

## 🔹 Dockerfile Example

```dockerfile
FROM mcr.microsoft.com/dotnet/aspnet:8.0
COPY . /app
ENTRYPOINT ["dotnet", "app.dll"]

Key Concepts
- Images
- Containers
- Volumes
Networking
```
---
# ☸️ 10. Kubernetes (AKS)

## 🔹 What is Kubernetes?

Container orchestration platform used to manage containers at scale.

---

## 🔹 Core Components

- Pod → Smallest deployable unit  
- Deployment → Manages pods  
- Service → Exposes application  
- Ingress → Handles routing  

---

## 🔹 Scaling

- Horizontal Pod Autoscaler (HPA)  

---

# 🔁 11. Resilience

## 🔹 Polly

Handles:

- Retry  
- Circuit Breaker  
- Timeout  

---

## 🔹 OpenTelemetry

Used for:

- Logging  
- Tracing  
- Metrics  

---

## 🔹 Rate Limiting (.NET 8)

```csharp
app.UseRateLimiter();
```
