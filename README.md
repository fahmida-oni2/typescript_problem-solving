# TypeScript Problem Solving

This repository contains 7 coding problems and a blog post that explains the concept in my own words.

---

##  Code file Structure

```
├── solutions.ts       # All 7 TypeScript problem solutions
├── blog.md            # Blog post on TypeScript Generics and pillar of object oriented programming
└── README.md         
```

---

## Problems

| # | Function | Description |
|---|----------|-------------|
| 1 | `filterEvenNumbers` | Filters even numbers from an array |
| 2 | `reverseString` | Reverses a given string |
| 3 | `checkType` | Uses union types and type guards to identify input type |
| 4 | `getProperty` | Generic function with `keyof` constraint to access object properties |
| 5 | `toggleReadStatus` | Extends a `Book` interface and adds an `isRead` property |
| 6 | `Person` / `Student` | Class inheritance with a `getDetails` method |
| 7 | `getIntersection` | Returns common elements between two arrays |

---

## 📝 Blog Posts

### Blog 1 — TypeScript Generics

> **How do Generics allow you to build reusable components and functions that stay strictly typed regardless of the data structures passed in?**

Covers the concept of Generics through the problems above — explaining what I learned, how `<T>` and `keyof T` work, and why Generics matter in real TypeScript code.

### Blog 2 — OOP in TypeScript

> **How do the four pillars of OOP — Inheritance, Polymorphism, Abstraction, and Encapsulation — help manage logic and reduce complexity in large-scale TypeScript projects?**

Covers each pillar with code examples — how Inheritance removes duplication, Polymorphism removes conditionals, Abstraction hides internal details, and Encapsulation protects data.

---

## 🚀 How to Run

```bash
# Install TypeScript globally
npm install -g typescript

# Compile
tsc solutions.ts

# Run
node solutions.js
```

---

## 🛠️ Tech

- TypeScript 5.x
- Node.js
