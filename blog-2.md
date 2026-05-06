<!-- How do the four pillars of OOP—Inheritance, Polymorphism, Abstraction, and Encapsulation—help manage logic and reduce complexity in large-scale TypeScript projects? -->

# Title: The Four Pillars of OOP: Managing Logic and Reducing Complexity in TypeScript

# Introduction
Object-Oriented Programming in TypeScript gives me a structured way to 
organize code around real-world concepts. Instead of writing scattered 
functions and loose data, I can group related logic and data into classes, and use the four pillars — Inheritance, Polymorphism, Abstraction, and Encapsulation to manage how that logic is shared, hidden, extended, and reused. Each pillar solves a specific problem that comes up when a codebase starts to grow. Together they make large-scale TypeScript projects easier to read, maintain, and extend without breaking existing logic.

# Body Paragraphs
 
The four pillars of OOP are Inheritance, Polymorphism, Abstraction, and Encapsulation. Each one helps me write cleaner, more organized TypeScript code in a different way.
 
### 1. Inheritance
 
Inheritance allows a child class to reuse properties and methods from a parent class without rewriting them.
 
```
class Animal {
    name: string;
 
    constructor(name: string) {
        this.name = name;
    }
 
    makeSound(): void {
        console.log(`${this.name} makes a sound.`);
    }
}
 
class Dog extends Animal {
    makeSound(): void {
        console.log(`${this.name} barks.`);
    }
}
 
class Cat extends Animal {
    makeSound(): void {
        console.log(`${this.name} meows.`);
    }
}
 
const dog = new Dog("Rex");
const cat = new Cat("Whiskers");
 
dog.makeSound(); // Rex barks.
cat.makeSound(); // Whiskers meows.
```
 
Here `Dog` and `Cat` both extend `Animal`. They inherit the `name` property but each overrides `makeSound()` with their own behavior. The shared logic lives once in the parent class.
 
---
 
### 2. Polymorphism
 
Polymorphism means different classes can share the same method name but each runs its own version of it.
 
```typescript
const animals: Animal[] = [new Dog("Rex"), new Cat("Whiskers")];
 
animals.forEach(animal => animal.makeSound());
// Rex barks.
// Whiskers meows.
```
 
Even though the array holds different types, TypeScript treats them all as `Animal`. Each object runs its own `makeSound()` without any `if/else` checks needed.
 
---
 
### 3. Abstraction
 
Abstraction means hiding how something works internally and only exposing what is needed. I use abstract classes in TypeScript to define a structure that every subclass must follow.
 
```typescript
abstract class Shape {
    abstract getArea(): number;
 
    describe(): void {
        console.log(`This shape has an area of ${this.getArea()}`);
    }
}
 
class Circle extends Shape {
    constructor(private radius: number) {
        super();
    }
 
    getArea(): number {
        return Math.PI * this.radius * this.radius;
    }
}
 
class Rectangle extends Shape {
    constructor(private width: number, private height: number) {
        super();
    }
 
    getArea(): number {
        return this.width * this.height;
    }
}
 
const circle = new Circle(5);
circle.describe(); // This shape has an area of 78.53...
 
const rectangle = new Rectangle(4, 6);
rectangle.describe(); // This shape has an area of 24
```
 
`Shape` defines that every subclass must have a `getArea()` method. The `describe()` method works for any shape without knowing how the area is calculated inside. I interact with the concept, not the internal details.
 
---
 
### 4. Encapsulation
 
Encapsulation means keeping internal data private and only allowing access through specific methods.
 
```typescript
class BankAccount {
    private balance: number = 0;
 
    deposit(amount: number): void {
        if (amount > 0) {
            this.balance += amount;
        }
    }
 
    withdraw(amount: number): void {
        if (amount <= this.balance) {
            this.balance -= amount;
        } else {
            console.log("Insufficient funds.");
        }
    }
 
    getBalance(): number {
        return this.balance;
    }
}
 
const account = new BankAccount();
account.deposit(500);
account.withdraw(200);
console.log(account.getBalance()); // 300
```
 
`balance` is `private` so nothing outside the class can change it directly. All access goes through `deposit()`, `withdraw()`, and `getBalance()`. This keeps the data safe and the logic in one place.
 
---
 
## Conclusion
 
Through this learning, I understood that the four pillars of OOP are not just theoretical concepts ,they are practical tools for managing complexity. Inheritance removes duplication, Polymorphism removes unnecessary conditionals, Abstraction hides what does not need to be exposed, and Encapsulation protects data from uncontrolled changes. Together they give large-scale TypeScript projects a clear structure where logic is organized, responsibilities are separated, and changes in one place do not break everything else.