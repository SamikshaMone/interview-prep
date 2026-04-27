# Module 3: Entity Framework Core, Dapper & SQL
# Complete Interview Questions with Answers

Level: Mid–Senior (.NET Full Stack)

---

# Section 1: EF Core Fundamentals

## Q1. What is EF Core?
EF Core is an ORM that allows interaction with a database using C# objects instead of SQL.

---

## Q2. What is DbContext?
DbContext manages database connections, queries, and change tracking.

---

## Q3. What is DbSet?
Represents a table and is used to query and save entities.

---

## Q4. How does EF Core translate LINQ to SQL?
LINQ is converted into expression trees, then translated into SQL and executed in the database.

---

## Q5. What is change tracking?
EF tracks changes to entities and persists them using SaveChanges().

---

## Q6. What is AsNoTracking?
Disables tracking for read-only queries to improve performance.

---

## Q7. When should you use AsNoTracking?
When data is read-only and no updates are needed.

---

## Q8. What are entity states?
Added, Modified, Deleted, Unchanged, Detached.

---

## Q9. What happens when SaveChanges is called?
EF generates SQL statements and updates the database.

---

## Q10. What is DbContext lifetime?
Typically scoped per request to avoid memory issues.

---

# Section 2: Loading Strategies

## Q11. What is lazy loading?
Loads related data when accessed.

---

## Q12. Why is lazy loading dangerous?
It causes multiple queries and performance issues.

---

## Q13. What is eager loading?
Loads related data in a single query using Include.

---

## Q14. What is explicit loading?
Manually loads related data using Entry().

---

## Q15. Which loading strategy is best?
Eager loading is generally best for performance.

---

# Section 3: N+1 Problem

## Q16. What is N+1 problem?
One query for parent + multiple queries for children.

---

## Q17. Why is N+1 a problem?
It increases DB calls and slows performance.

---

## Q18. How to detect N+1?
Logs, SQL profiler, Application Insights.

---

## Q19. How to fix N+1?
Use Include or optimized queries.

---

## Q20. Real-world example?
Multiple DB calls replaced with a single optimized query using Include.

---

# Section 4: Dapper

## Q21. What is Dapper?
A micro ORM that executes raw SQL.

---

## Q22. Why is Dapper faster?
No tracking and minimal abstraction.

---

## Q23. When to use Dapper?
Read-heavy or performance-critical queries.

---

## Q24. Limitations of Dapper?
Manual SQL and no change tracking.

---

## Q25. How does Dapper map data?
Maps query results to objects automatically.

---

# Section 5: EF Core vs Dapper

## Q26. Difference between EF Core and Dapper?
EF Core is easier; Dapper is faster.

---

## Q27. When to use EF Core?
For CRUD and business logic.

---

## Q28. When to use Dapper?
For optimized queries.

---

## Q29. Can both be used together?
Yes, commonly used in real projects.

---

## Q30. Real-world decision?
EF Core for writes, Dapper for reads.

---

# Section 6: Migrations & Fluent API

## Q31. What are migrations?
Used to manage schema changes.

---

## Q32. Why use migrations?
To version control database structure.

---

## Q33. What is Fluent API?
Used to configure relationships and constraints.

---

## Q34. Fluent API vs Data Annotations?
Fluent API is more flexible.

---

## Q35. What is seeding?
Preloading initial data into database.

---

# Section 7: Concurrency

## Q36. What is concurrency?
Multiple users accessing same data.

---

## Q37. What is optimistic concurrency?
Uses versioning to detect conflicts.

---

## Q38. How to implement concurrency?
Using RowVersion column.

---

## Q39. What happens during conflict?
Exception is thrown and must be handled.

---

## Q40. Why is concurrency important?
Prevents data loss.

---

# Section 8: SQL Basics

## Q41. What are joins?
Combine data from multiple tables.

---

## Q42. Types of joins?
Inner, Left, Right.

---

## Q43. What is indexing?
Improves query performance.

---

## Q44. Clustered vs non-clustered?
Clustered sorts data; non-clustered uses separate structure.

---

## Q45. When to use indexes?
On frequently queried columns.

---

# Section 9: Query Optimization

## Q46. How to optimize queries?
Avoid SELECT *, use indexes, reduce joins.

---

## Q47. What causes slow queries?
Table scans, missing indexes.

---

## Q48. What is pagination?
Fetching limited data using skip/take.

---

## Q49. How to reduce DB load?
Caching and query optimization.

---

## Q50. What is caching?
Storing frequently used data in memory.

---

# Section 10: Execution Plans

## Q51. What is execution plan?
Shows how SQL executes a query.

---

## Q52. Why is it important?
Helps identify performance issues.

---

## Q53. What is table scan?
Full table read, very slow.

---

## Q54. What is index seek?
Efficient query using index.

---

## Q55. How to fix table scan?
Add index.

---

# Section 11: Advanced SQL

## Q56. What is CTE?
Temporary result set.

---

## Q57. What are window functions?
Operate on row sets.

---

## Q58. Example of window function?
ROW_NUMBER for ranking.

---

## Q59. What is partition by?
Divides data into groups.

---

## Q60. Use cases of window functions?
Ranking, pagination.

---

# Section 12: Scenarios

## Q61. API is slow. What will you do?
Check queries, optimize, add indexes.

---

## Q62. High DB load?
Reduce calls, caching.

---

## Q63. EF performance issue?
Use AsNoTracking, eager loading.

---

## Q64. When to switch to Dapper?
When performance is critical.

---

## Q65. Large data handling?
Use pagination and indexing.

---

# Final Strategy

- Focus on performance
- Explain real examples
- Highlight N+1 fix
- Explain EF vs Dapper clearly

---

# End
