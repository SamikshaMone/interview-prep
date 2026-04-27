# Module 1: C# & .NET Core / .NET 8 (Backend Core)
# Complete Deep Notes

Level: Mid–Senior (.NET Full Stack)
Goal: Strong foundation in C# internals + runtime + performance

---

# Table of Contents

1. OOP Concepts (Deep)
2. SOLID Principles (With Real Use Cases)
3. Value vs Reference Types (Memory Deep Dive)
4. Boxing & Unboxing (Performance Impact)
5. async/await (Internals + Best Practices)
6. Task vs Thread vs Parallelism
7. Delegates & Events (Deep Understanding)
8. LINQ (Execution + Performance)
9. Generics (CLR + Performance)
10. Extension Methods
11. .NET 8 Features (Practical Use)
12. Middleware Pipeline
13. Filters (Execution Flow)
14. Dependency Injection (Internals)
15. Garbage Collection (Deep Dive)
16. IDisposable & Resource Management

---

# 1. OOP Concepts (Deep)

## Encapsulation
- Restricts direct access to data
- Achieved via properties and access modifiers

Why important:
- Data protection
- Maintainability

---

## Abstraction
- Hides implementation details
- Exposes only required functionality

Implementation:
- Interfaces
- Abstract classes

---

## Inheritance
- Enables code reuse
- Supports base and derived classes

Problem:
- Tight coupling if overused

---

## Polymorphism

Compile-time:
- Method overloading

Runtime:
- Method overriding using virtual/override

---

# 2. SOLID Principles (With Real Use Cases)

## SRP
One class → one responsibility

Example:
Separate EmailService and UserService

---

## OCP
Extend behavior without modifying existing code

Example:
Use interfaces for new payment types

---

## LSP
Derived class should not break base class behavior

---

## ISP
Avoid large interfaces

Example:
Split IUserService into smaller interfaces

---

## DIP
Depend on abstractions

Example:
Use interface instead of concrete class

---

# 3. Value vs Reference Types (Memory Deep Dive)

## Value Types
- Stored in stack
- Passed by value
- Faster

Examples:
int, struct

---

## Reference Types
- Stored in heap
- Passed by reference

Examples:
class, string, array

---

## Key Concept

Value:
Creates copy

Reference:
Points to same object

---

# 4. Boxing & Unboxing

Boxing:
Value type → object (heap allocation)

Unboxing:
Object → value type

Problem:
- Performance overhead
- Memory allocation

Avoid:
- Using generics instead of object

---

# 5. async/await (Deep)

## What happens internally

- async method creates state machine
- Execution pauses at await
- Thread released to thread pool
- Continues after completion

---

## Benefits

- Non-blocking I/O
- Better scalability

---

## Best Practices

- Avoid blocking calls (.Result, .Wait())
- Use ConfigureAwait(false) in libraries
- Prefer async all the way

---

## Common Mistakes

- Deadlocks
- Mixing sync and async code

---

# 6. Task vs Thread vs Parallelism

## Thread
- OS-level
- Heavyweight

---

## Task
- Lightweight abstraction
- Uses thread pool

---

## Parallelism
- Multiple operations simultaneously
- CPU-bound tasks

---

## Comparison

Thread:
Manual, costly

Task:
Recommended

Parallel:
For CPU-heavy operations

---

# 7. Delegates & Events

## Delegate
Type-safe function pointer

---

## Types

Action:
No return

Func:
Returns value

Predicate:
Returns bool

---

## Events

Publisher-subscriber model

Use case:
UI events, notifications

---

# 8. LINQ (Execution + Performance)

## Types

Deferred:
Executed when iterated

Immediate:
Executed instantly

---

## Performance Tips

- Avoid multiple enumerations
- Use projection (Select)
- Filter early

---

## Common Methods

Where, Select, OrderBy, GroupBy

---

# 9. Generics (Deep)

## Purpose

- Type safety
- Performance

---

## Benefits

- No boxing
- Reusable code

---

## CLR Behavior

Generics create type-safe compiled code

---

# 10. Extension Methods

Adds functionality without modifying original class

---

## Use Case

Reusable helper methods

---

# 11. .NET 8 Features

## Keyed Dependency Injection

Multiple implementations with keys

---

## Native AOT

Ahead-of-time compilation

Benefits:
- Faster startup
- Reduced memory

---

## Minimal APIs

Less boilerplate

---

# 12. Middleware Pipeline

## Concept

Pipeline of request processing

---

## Flow

Request → Middleware → Response

---

## Example Use

- Authentication
- Logging
- Error handling

---

# 13. Filters

## Types

- Authorization
- Action
- Exception

---

## Execution Order

Authorization → Action → Result → Exception

---

# 14. Dependency Injection (Internals)

## Types

Transient:
New instance every time

Scoped:
One per request

Singleton:
Single instance

---

## Benefits

- Loose coupling
- Testability

---

## Internal Working

- Service container stores mappings
- Resolves dependencies at runtime

---

# 15. Garbage Collection (Deep)

## Generations

Gen 0:
Short-lived objects

Gen 1:
Medium

Gen 2:
Long-lived

---

## Process

- Marks unused objects
- Frees memory

---

## Important Concepts

- Heap allocation
- Memory pressure

---

# 16. IDisposable & Resource Management

## Purpose

Release unmanaged resources

---

## Example

File, DB connection

---

## using statement

Ensures Dispose is called automatically

---

## Pattern

Implement IDisposable correctly

---

# Final Interview Strategy

Always answer:

1. Concept
2. Internals
3. Real-world usage

Example:

Used async/await for non-blocking operations, improving scalability of APIs under high load.

---

# End of File
