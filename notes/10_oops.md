```md
# **Object-Oriented Programming (OOP) in JavaScript**

## **What is OOP?**
- OOP is a **programming paradigm** based on the concept of objects.
- Objects **encapsulate data and behaviors (methods)** in a single unit.
- OOP **organizes code** to make it **more flexible and easier to maintain**.
- A **class** is a blueprint, while an **object** is an instance of that class.

---

## **Four Pillars of OOP**
### **1. Abstraction**
- **Hides complex implementation details**, showing only essential features.
- Example: Using the `.filter()` method without knowing how it works internally.
- **High-level details** are visible, while **low-level details** remain hidden.

### **2. Encapsulation**
- **Restricts direct access** to object properties and methods.
- **Prevents unintended modifications** of internal data.
- **Enables changes** in internal implementation without affecting external code.

### **3. Inheritance**
- Allows **one class (child) to inherit properties and methods** from another (parent).
- **Promotes code reuse** and models real-world relationships.
- A **child class extends** a parent class, inheriting its properties and methods.

### **4. Polymorphism**
- A **child class can override methods** inherited from a parent class.
- This allows **different behaviors** for the same method in different contexts.

---

## **OOP in JavaScript**
- JavaScript **implements OOP using prototypes** instead of traditional classes.
- **Objects are linked to prototype objects**, which store methods.

### **Three Ways to Implement Prototypal Inheritance in JS**
1. **Constructor Functions**
2. **ES6 Classes**
3. **`Object.create()`** (Simplest way to link an object to a prototype)

---

## **1. Constructor Function**
```javascript
const Person = function (firstName, birthYear) {
    this.firstName = firstName;
    this.birthYear = birthYear;
};

const Jonas = new Person('Jonas', 1998);
console.log(Jonas); // Person { firstName: 'Jonas', birthYear: 1998 }
```
### **What Happens Behind the Scenes?**
1. A **new empty object `{}`** is created.
2. The **function is called**, and `this = {}`.
3. The **new object is linked to the prototype**.
4. The function **automatically returns `{}`**.

---

This guide covers **OOP principles, JavaScript prototypal inheritance, and constructor functions!** 🚀
```