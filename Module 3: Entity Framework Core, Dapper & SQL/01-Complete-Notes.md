# Module 3: Entity Framework Core, Dapper & SQL — Complete Notes

Level: Mid–Senior (.NET Full Stack)
Goal: Understand data access, performance optimization, and real-world decision making

---

# Table of Contents

1. EF Core Overview
2. EF Core Internals
3. Change Tracking
4. Loading Strategies
5. N+1 Query Problem
6. Dapper
7. EF Core vs Dapper
8. Migrations & Fluent API
9. Concurrency Handling
10. SQL Fundamentals
11. Query Optimization
12. Execution Plans
13. Advanced SQL
14. Real-world Scenarios

---

# 1. Entity Framework Core

## What is EF Core?

EF Core is an ORM that allows interaction with the database using C# objects instead of writing raw SQL.

It converts:
- LINQ queries into SQL
- SQL results into C# objects

---

## DbContext

Central class responsible for database interaction.

Example:

public class AppDbContext : DbContext
{
    public DbSet<User> Users { get; set; }
}

---

# 2. EF Core Internals

## Query Pipeline

1. LINQ query is written
2. Converted into expression tree
3. Translated to SQL
4. SQL executed in database
5. Results mapped back to objects

Important:
Not all LINQ queries are translated to SQL. Some may execute in memory, which can cause performance issues.

---

# 3. Change Tracking

## What is Change Tracking?

EF Core tracks changes made to entities and persists them using SaveChanges().

## Entity States

- Added
- Modified
- Deleted
- Unchanged
- Detached

## Optimization

Use AsNoTracking for read-only queries:

context.Users.AsNoTracking().ToList();

This improves performance by disabling tracking.

---

# 4. Loading Strategies

## Lazy Loading

- Loads related data only when accessed
- Can cause multiple queries

Example:

var orders = user.Orders;

## Eager Loading

- Loads related data in one query

Example:

context.Users.Include(u => u.Orders).ToList();

## Explicit Loading

- Manually loads related data

Example:

context.Entry(user).Collection(u => u.Orders).Load();

## Comparison

Lazy Loading:
- Easy but poor performance

Eager Loading:
- Best performance for most cases

Explicit Loading:
- Good control over data loading

---

# 5. N+1 Query Problem

## Problem

1 query to fetch parent records
+ N queries to fetch related records

Example:

var users = context.Users.ToList();

foreach (var user in users)
{
    var orders = user.Orders;
}

This results in multiple database calls.

## Solution

Use eager loading:

context.Users.Include(u => u.Orders).ToList();

## Interview Explanation

Identified multiple database calls using logging and fixed it using eager loading, reducing response time significantly.

---

# 6. Dapper

## What is Dapper?

Dapper is a micro ORM that executes raw SQL queries and maps results to objects.

## Example

var users = connection.Query<User>("SELECT * FROM Users");

## Advantages

- High performance
- Full SQL control
- Lightweight

## When to Use

- Read-heavy queries
- Complex joins
- Performance-critical operations

---

# 7. EF Core vs Dapper

EF Core:
- Slower than Dapper
- Easier to use
- Good for business logic

Dapper:
- Faster
- More control
- Best for optimized queries

## Interview Answer

Use EF Core for standard CRUD operations and Dapper for performance-critical queries.

---

# 8. Migrations & Fluent API

## Migrations

Used to manage database schema changes.

Commands:

Add-Migration Initial
Update-Database

## Fluent API

Used to configure entity relationships and constraints.

Example:

modelBuilder.Entity<User>()
    .HasKey(u => u.Id);

---

# 9. Concurrency Handling

## Optimistic Concurrency

Uses a version column to detect conflicts.

Example:

[Timestamp]
public byte[] RowVersion { get; set; }

## Purpose

Prevents overwriting changes when multiple users update the same data.

---

# 10. SQL Fundamentals

## Joins

- INNER JOIN: matching rows
- LEFT JOIN: all left rows + matching right
- RIGHT JOIN: all right rows + matching left

## Indexes

- Clustered Index: sorts data
- Non-clustered Index: separate structure

Indexes improve query performance.

---

# 11. Query Optimization

## Techniques

- Avoid SELECT *
- Use indexes
- Reduce joins
- Use pagination
- Filter early

## Example

SELECT Name FROM Users WHERE Id = 1;

---

# 12. Execution Plans

## What is Execution Plan?

Shows how SQL Server executes a query.

## Used to identify

- Table scans
- Missing indexes
- Costly operations

---

# 13. Advanced SQL

## CTE (Common Table Expression)

WITH cte AS (
    SELECT * FROM Users
)
SELECT * FROM cte;

## Window Functions

ROW_NUMBER() OVER (PARTITION BY Department ORDER BY Salary);

Used for ranking and pagination.

---

# 14. Real-world Scenarios

## Scenario: Slow API

- Identify slow queries
- Optimize SQL
- Add indexes
- Use caching

## Scenario: High DB Load

- Reduce database calls
- Use caching
- Optimize queries

## Scenario: EF vs Dapper Decision

- EF Core for business logic
- Dapper for performance-critical queries

---

# Final Interview Strategy

- Always explain with real examples
- Focus on performance improvements
- Mention optimization techniques
- Highlight N+1 problem solution

---

# End of Module 3 Notes
