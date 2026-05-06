<!-- How do Generics allow you to build reusable components and functions that stay strictly typed regardless of the data structures passed in? -->

# Title : TypeScript Generics: Building Reusable, Strictly-Typed Components That Scale

# Introduction
Generics in TypeScript allow me to write reusable code that works with any data type while still keeping full type safety. Instead of writing separate functions or interfaces for string, number, or custom objects, I can use a type parameter like <T> as a flexible placeholder and TypeScript resolves the actual type automatically based on what I pass in.The core idea is to write the logic or structure once, and let TypeScript handle the type based on the actual data.This makes code cleaner, avoids unnecessary duplication, and keeps TypeScript's type checking fully active at all times.

#  Body Paragraphs
A generic function in TypeScript is a function that can work with any type while still maintaining full type safety. Instead of writing separate functions for each data type, I define a type parameter <T> that TypeScript resolves automatically based on what is passed in at the time of calling.

For example:
```
type User = {
    id: number;
    name: string;
    age: number;
}
 
const getProperty = <T>(obj: T, key: keyof T) => {
    return obj[key];
}
 
const user: User = { id: 1, name: "John Doe", age: 21 };
 
getProperty(user, "name");  // "John Doe"
getProperty(user, "age");   // 21
```
Here <T> gets inferred as User when I pass the user object. The keyof T constraint limits the key to only "id", "name", or "age" nothing else is allowed. The return type is also inferred automatically, so TypeScript knows exactly what type of value is coming back.
This is what makes Generics with keyof useful. I write one function that works on any object, and TypeScript still keeps full type safety on both the key and the return value.

# Conclusion
Through this learning, I understood that Generics are not just a TypeScript feature, they are a way of thinking about code. Instead of solving the same problem multiple times for different types, I define the solution once and let TypeScript handle the type resolution. The <T> type parameter, combined with constraints like keyof T, gives me both flexibility and safety at the same time. This is what separates well-structured TypeScript code from code that simply works.
