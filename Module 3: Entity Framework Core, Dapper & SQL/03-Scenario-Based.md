# Module 3: Entity Framework Core, Dapper & SQL
# 03-Scenario-Based.md

Level: Mid–Senior (.NET Full Stack)
Focus: Real-world debugging, optimization, and decision-making

---

# Section 1: Performance Issues

## Scenario 1: API response time increased significantly

Approach:

Detection:
- Check logs or monitoring tools
- Identify slow endpoints

Analysis:
- Check database queries
- Look for N+1 issues
- Analyze execution plan

Fix:
- Use eager loading
- Add indexes
- Optimize queries

Prevention:
- Add performance monitoring
- Use caching

---

## Scenario 2: High database load

Approach:

- Identify frequent queries
- Reduce repeated DB calls
- Use caching (Redis or in-memory)
- Optimize queries

---

## Scenario 3: Query taking too long

Approach:

- Analyze execution plan
- Identify table scans
- Add indexes
- Reduce joins
- Optimize filters

---

## Scenario 4: EF Core query is slow

Approach:

- Use AsNoTracking for read-only queries
- Avoid lazy loading
- Use projections (Select)
- Optimize LINQ

---

## Scenario 5: Application memory usage is high

Approach:

- Avoid tracking large datasets
- Use pagination
- Use streaming instead of loading all data

---

# Section 2: N+1 Problem

## Scenario 6: Multiple database calls observed

Approach:

- Identify lazy loading usage
- Replace with eager loading using Include
- Reduce number of queries

---

## Scenario 7: Nested loops causing DB calls

Approach:

- Refactor queries
- Use joins or Include
- Fetch data in one query

---

# Section 3: EF vs Dapper Decision

## Scenario 8: API is slow with EF Core

Approach:

- Analyze query performance
- Replace EF with Dapper for that query
- Use raw SQL for optimization

---

## Scenario 9: Complex reporting query

Approach:

- Use Dapper
- Write optimized SQL
- Avoid ORM overhead

---

## Scenario 10: Maintainability vs performance

Approach:

- Use EF Core for business logic
- Use Dapper for heavy queries

---

# Section 4: Data Consistency & Concurrency

## Scenario 11: Data overwritten by multiple users

Approach:

- Implement optimistic concurrency
- Use RowVersion column
- Handle concurrency exceptions

---

## Scenario 12: Lost updates issue

Approach:

- Use versioning
- Retry logic if conflict occurs

---

# Section 5: SQL Optimization

## Scenario 13: Table scan detected

Approach:

- Add appropriate indexes
- Rewrite query

---

## Scenario 14: Slow join query

Approach:

- Ensure indexed columns
- Reduce unnecessary joins
- Optimize join conditions

---

## Scenario 15: Large dataset query

Approach:

- Use pagination
- Fetch only required columns
- Use filtering

---

## Scenario 16: Query returning too much data

Approach:

- Use Select instead of full entity
- Limit columns

---

# Section 6: Database Design Issues

## Scenario 17: Poor schema design

Approach:

- Normalize tables
- Add relationships
- Use constraints

---

## Scenario 18: Duplicate data issue

Approach:

- Add unique constraints
- Clean existing data

---

# Section 7: Migrations Issues

## Scenario 19: Migration failed

Approach:

- Check migration script
- Validate schema changes
- Rollback if needed

---

## Scenario 20: Data loss during migration

Approach:

- Backup database
- Use safe migration strategy
- Test in staging

---

# Section 8: Dapper Issues

## Scenario 21: Mapping issues in Dapper

Approach:

- Ensure column names match model
- Use aliases

---

## Scenario 22: SQL injection risk

Approach:

- Use parameterized queries
- Avoid string concatenation

---

# Section 9: Advanced SQL Scenarios

## Scenario 23: Ranking data required

Approach:

- Use window functions like ROW_NUMBER

---

## Scenario 24: Complex query readability issue

Approach:

- Use CTE
- Break query into parts

---

# Section 10: Real Interview Scenarios

## Scenario 25: API scaling issue

Approach:

- Reduce DB dependency
- Use caching
- Optimize queries

---

## Scenario 26: High latency due to DB

Approach:

- Optimize SQL
- Add indexes
- Reduce DB calls

---

## Scenario 27: Switching from EF to Dapper

Approach:

- Identify bottleneck
- Replace specific queries with Dapper
- Keep EF for other logic

---

## Scenario 28: Large data processing

Approach:

- Use batching
- Process in chunks

---

## Scenario 29: Frequent DB calls in loop

Approach:

- Refactor logic
- Fetch data once

---

## Scenario 30: Debugging production issue

Approach:

- Check logs
- Analyze query performance
- Fix root cause

---

# Final Strategy

Answer structure:

1. Detection
2. Analysis
3. Fix
4. Prevention

Always include:

- Performance improvement
- Real example
- Optimization techniques

---

# End of File
