# ⚡ Module 5: Azure & DevOps — Deep Cheat Sheet

**Purpose:** Fast + deep revision before interviews  
**Level:** Mid–Senior (.NET Full Stack, 3–5 yrs)  
**Usage:** Revise this 1 day before interview  

---

# ☁️ 1. Azure Fundamentals

## 🔹 Cloud Models

| Model | You Manage | Azure Example |
|------|-----------|--------------|
| IaaS | OS + Runtime + App | Azure VM |
| PaaS | App only | App Service, Azure SQL |
| FaaS | Code only | Azure Functions |
| SaaS | Nothing | Microsoft 365 |

👉 **Interview Line:**
“We used PaaS services to reduce infrastructure overhead and focus on business logic.”

---

## 🔹 Core Concepts

- **Resource Group:** Logical container  
- **Region:** Physical location  
- **Availability Zone:** High availability  

👉 **Important:**
- Same RG → same lifecycle  
- Use multiple regions for DR  

---

## 🔹 ARM vs Bicep

- ARM → JSON (complex)  
- Bicep → Clean + readable  

👉 Prefer **Bicep (modern approach)**

---

# 🌐 2. Azure App Service (VERY IMPORTANT)

## 🔹 What & Why

- PaaS for hosting APIs  
- Fully managed runtime  

---

## 🔹 App Service Plan

- Defines **compute resources**
- Multiple apps can share same plan  

---

## 🔹 Scaling

- Vertical → Increase size  
- Horizontal → Increase instances  

👉 **Auto-scale triggers:**
- CPU > threshold  
- Memory  
- HTTP queue  

---

## 🔹 Deployment Slots (CRITICAL)

- Staging + Production  

### Flow:
Deploy → Test → Swap  

### Benefits:
- Zero downtime  
- Instant rollback  

👉 **Interview Line:**
“We used deployment slots to achieve zero downtime deployments.”

---

## 🔹 Networking

- VNet Integration  
- Private Endpoint  
- IP restrictions  

---

# ⚡ 3. Azure Functions

## 🔹 Concept

- Serverless (event-driven)  
- Executes on trigger  

---

## 🔹 Plans

| Plan | Key Point |
|------|----------|
| Consumption | Pay per execution |
| Premium | No cold start |
| Dedicated | Fixed resources |

---

## 🔹 Cold Start

- Delay in execution  
👉 Avoid using:
- Premium plan  
- Keep warm  

---

## 🔹 Triggers

- HTTP  
- Timer  
- Queue  
- Service Bus  

---

## 🔹 Real Use

👉 Background processing, async workflows  

👉 **Interview Line:**
“We used Azure Functions to process asynchronous workflows and reduce latency.”

---

# 🗄️ 4. Azure SQL

## 🔹 Types

- Azure SQL DB  
- Managed Instance  
- SQL VM  

---

## 🔹 Performance Optimization

- Indexing  
- Query tuning  
- Avoid N+1  
- Use caching  

---

## 🔹 Index Types

- Clustered → sorted data  
- Non-clustered → separate structure  

---

## 🔹 HA & DR

- Geo-replication  
- Failover groups  

---

👉 **Interview Line:**
“We optimized queries and resolved N+1 problem using EF Core Include.”

---

# 🔐 5. Azure Key Vault

## 🔹 Purpose

Secure storage for:
- Secrets  
- Keys  
- Certificates  

---

## 🔹 Best Practices

- Use Managed Identity  
- Avoid storing secrets in code  

---

## 🔹 Access Methods

- RBAC (preferred)  
- Access Policies  

---

👉 **Interview Line:**
“We used Managed Identity to securely access Key Vault without storing credentials.”

---

# 📊 6. Application Insights

## 🔹 Purpose

Monitoring + observability  

---

## 🔹 Tracks

- Requests  
- Dependencies  
- Exceptions  
- Logs  

---

## 🔹 Key Concepts

- Distributed tracing  
- Correlation ID  
- KQL queries  

---

## 🔹 Sample KQL

requests  
| summarize avg(duration) by name  

---

👉 **Interview Line:**
“We used Application Insights to identify slow APIs and debug production issues.”

---

# ⚙️ 7. CI/CD (Azure DevOps)

## 🔹 CI/CD Flow

1. Code commit  
2. Build  
3. Test  
4. Deploy staging  
5. Approval  
6. Production  

---

## 🔹 Key Concepts

- YAML pipelines  
- PR policies  
- Approval gates  
- Artifacts  

---

## 🔹 Deployment Strategies

- Blue-Green  
- Canary  
- Rolling  

---

👉 **Interview Line:**
“We implemented CI/CD pipelines with automated testing and zero downtime deployments.”

---

# 🔄 8. GitHub Actions

## 🔹 Purpose

CI/CD inside GitHub  

---

## 🔹 Concepts

- Workflow (.yml)  
- Jobs  
- Steps  
- Secrets  

---

## 🔹 Advantage

- Lightweight  
- Easy integration  

---

# 🐳 9. Docker

## 🔹 Why Docker?

- Lightweight  
- Fast  
- Portable  

---

## 🔹 Key Concepts

- Image → Blueprint  
- Container → Running instance  
- Volume → Storage  
- Network → Communication  

---

## 🔹 Best Practices

- Multi-stage builds  
- Minimal base images  
- Avoid root user  

---

👉 **Interview Line:**
“Docker ensures consistent environments across development and production.”

---

# ☸️ 10. Kubernetes (AKS)

## 🔹 Purpose

Container orchestration  

---

## 🔹 Core Components

- Pod → Smallest unit  
- Deployment → Manage pods  
- Service → Expose app  
- Ingress → Routing  

---

## 🔹 Scaling

- HPA (Horizontal Pod Autoscaler)  

---

# 🔁 11. Resilience & Reliability

## 🔹 Polly

- Retry  
- Circuit breaker  
- Timeout  

---

## 🔹 Patterns

- Retry  
- Fallback  
- Bulkhead  
- Idempotency  

---

## 🔹 Rate Limiting (.NET 8)

Used to prevent abuse  

---

👉 **Interview Line:**
“We implemented Polly for retries and circuit breaker to handle failures gracefully.”

---

# 🔥 Scenario Keywords (IMPORTANT)

Use these words in interviews:

- Zero downtime  
- Auto-scaling  
- Managed Identity  
- Application Insights debugging  
- Retry + Circuit Breaker  
- Redis caching  

---

# 🎯 Golden Answer Structure

1. Detection  
2. Analysis  
3. Fix  
4. Prevention  

---

# 🚀 Example Answer

“We identified latency using Application Insights, found slow SQL queries, optimized them, and scaled the App Service. We also added alerts to prevent recurrence.”

---

# 📌 Final Reminder

❌ Weak:
“Azure Functions is serverless”

✅ Strong:
“We used Azure Functions for async workflows, reducing processing time and improving system performance.”

---

# 💯 End of Cheat Sheet
