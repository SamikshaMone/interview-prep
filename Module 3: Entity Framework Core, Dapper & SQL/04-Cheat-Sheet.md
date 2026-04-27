# Module 3: Entity Framework Core, Dapper & SQL
# 04-Cheat-Sheet.md

Purpose: Fast but deep revision before interviews
Level: Mid–Senior (.NET Full Stack)

---

# 1. EF Core Essentials

EF Core is an ORM that:
- Converts LINQ to SQL
- Maps database data to C# objects
- Handles change tracking

Key Components:
- DbContext: manages connection and queries
- DbSet: represents a table

---

# 2. EF Core Query Flow

1. LINQ query
2. Expression tree
3. SQL translation
4. Execution in DB
5. Result mapping

Important:
- Not all LINQ translates to SQL
- Some parts execute in memory (bad for performance)

---

# 3. Change Tracking

Tracks entity changes automatically.

Entity States:
- Added
- Modified
- Deleted
- Unchanged
- Detached

Optimization:
- Use AsNoTracking() for read-only queries
- Reduces memory usage and improves performance

---

# 4. Loading Strategies

Lazy Loading:
- Loads data on demand
- Causes multiple queries
- Avoid in production

Eager Loading:
- Loads related data in one query
- Use Include()

Explicit Loading:
- Manual loading when needed

Best Practice:
- Prefer eager loading

---

# 5. N+1 Query Problem

Problem:
1 query for parent + N queries for child

Impact:
- High DB calls
- Poor performance

Fix:
- Use Include()
- Use joins or projections

Interview Line:
Optimized multiple DB calls by replacing lazy loading with eager loading.

---

# 6. EF Core Performance Tips

- Use AsNoTracking for read queries
- Avoid lazy loading
- Use Select (projection) instead of full entity
- Use pagination (Skip/Take)
- Avoid loading large datasets
- Use compiled queries for frequent operations

---

# 7. Dapper Essentials

Dapper is a micro ORM:
- Executes raw SQL
- Maps results to objects
- No change tracking

Advantages:
- Very fast
- Full control over SQL

Limitations:
- Manual queries
- No built-in relationships

---

# 8. EF Core vs Dapper

EF Core:
- Easier to use
- Slower
- Good for CRUD and business logic

Dapper:
- Faster
- More control
- Good for complex queries

Best Practice:
- Use EF Core + Dapper together

Interview Line:
Used EF Core for writes and Dapper for optimized read queries.

---

# 9. Migrations

Used to manage schema changes.

Commands:
- Add-Migration
- Update-Database

Best Practice:
- Always test migrations in staging
- Avoid breaking changes

---

# 10. Fluent API

Used to configure:
- Relationships
- Constraints
- Table mappings

Better than Data Annotations for complex configurations

---

# 11. Concurrency Handling

Optimistic Concurrency:
- Uses version column (RowVersion)
- Detects conflicts

Purpose:
- Prevents overwriting data

---

# 12. SQL Fundamentals

Joins:
- Inner Join
- Left Join
- Right Join

Indexes:
- Clustered: sorts data
- Non-clustered: separate structure

Use indexes on frequently queried columns

---

# 13. Query Optimization

Techniques:
- Avoid SELECT *
- Use indexes
- Filter early
- Reduce joins
- Use pagination
- Use proper data types

---

# 14. Execution Plan

Shows how SQL executes queries.

Look for:
- Table scan (bad)
- Index seek (good)

Fix:
- Add indexes
- Rewrite query

---

# 15. Advanced SQL

CTE:
Used for readable complex queries

Window Functions:
- ROW_NUMBER
- RANK
- Used for pagination and ranking

---

# 16. Common Performance Issues

- N+1 queries
- Missing indexes
- Large data fetch
- Unoptimized joins
- Lazy loading

---

# 17. Real-world Scenarios Quick Guide

Slow API:
- Check queries
- Add indexes
- Optimize SQL

High DB load:
- Reduce calls
- Use caching

EF performance issue:
- Use AsNoTracking
- Avoid lazy loading

Large data:
- Use pagination

---

# 18. Key Interview Points

Always mention:
- N+1 problem fix
- EF vs Dapper decision
- Query optimization
- Index usage
- Real performance improvements

---

# 19. Golden Answer Pattern

1. Identify problem
2. Analyze root cause
3. Optimize solution
4. Prevent recurrence

---

# 20. Must Remember Lines

- Used AsNoTracking to improve read performance
- Fixed N+1 problem using eager loading
- Used Dapper for performance-critical queries
- Added indexes to optimize query performance
- Reduced DB calls using caching

---

# End of File
