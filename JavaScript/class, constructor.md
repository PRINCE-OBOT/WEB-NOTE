### **Class** 

A **class** in JavaScript is a blueprint for creating objects with shared properties and methods. It allows you to define a structure for your objects, including how they are created and how they behave.

You can think of a class as a template, and when you create an instance of that class, you’re creating a real object that follows that template.

## constructor

A **constructor** is a function inside a class. When the `new` keyword is used, it **initializes object properties** uniquely for each object.

Each object **does not inherit properties from another object**—instead, it **occupies its own space in memory** with its own **unique properties**.

However, **methods inside the class are not copied into each object**—instead, they are stored **once in the prototype**, and all objects **inherit** (share) them.

---
### *Example 

Imagine you're designing a hospital system, and you need a class to represent a **Patient**.


```javascript
class Patient {
   constructor(name, age) {
      this.name = name;  // Unique to each object
      this.age = age;    // Unique to each object
   }

   describe() {
      return `I am ${this.name}, and I am ${this.age} years old.`;
   }
}

let patient1 = new Patient("Obot", 56);
let patient2 = new Patient("Ahmed", 45);

console.log(patient1.describe()); // "I am Obot, and I am 56 years old."
console.log(patient2.describe()); // "I am Ahmed, and I am 45 years old."

console.log(patient1.describe === patient2.describe); // true (both share the same method)
```

---

### **Key Fixes to Your Explanation**

1. **Properties are not inherited; they are unique for each object.**
2. **Methods inside the class are stored once in the prototype and inherited by all objects.**
