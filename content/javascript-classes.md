---
title: Unveiling Classes in JavaScript Building Reusable(inheritance) Objects
date: 2021-03-12
draft: false
description: "
JavaScript's ability to manipulate data is fundamental to its web development prowess. However, as applications grow in complexity, the need for organized and reusable code becomes paramount. Classes, introduced in ES6, address this need by providing a structure for creating objects that share similar characteristics and behaviors. This blog article delves into the world of JavaScript classes, equipping you with the knowledge to craft reusable and well-structured code.
"
image: "/images/javascript_strings.webp"
imageBig: "/images/javascript_strings.webp"
categories: ["javascript", ]
authors: ["superuser"]
avatar: "/images/avatar.webp"
---




## Introducing the Class: A Blueprint for Objects

Imagine you're developing a game simulation. You require a mechanism to represent various vehicles, each with common properties (like description) and functionalities (like describing itself). Classes serve as blueprints for creating objects that share these traits. Let's build a Vehicle class:

JavaScript
class Vehicle {
  constructor(description, wheels) {
    // Set properties using 'this' keyword
    this.description = description;
    this.wheels = wheels;
  }

  describeYourself() {
    console.log(`I am a ${this.description} with ${this.wheels} wheels.`);
  }
}
Use code with caution.
Here, we define a class named Vehicle. The constructor function serves as the foundation, responsible for initializing properties that belong to each Vehicle instance. Inside the constructor, we leverage the this keyword to assign the received arguments (description and wheels) to the corresponding object properties.

The describeYourself method is a custom function associated with the Vehicle class. This method utilizes template literals to construct a message incorporating the object's description and number of wheels.

Creating Objects (Instances) from the Class

Now that we have the Vehicle class blueprint, we can create instances (objects) that inherit its properties and methods. Think of an instance as a specific realization of the general concept defined by the class:

JavaScript
class Vehicle {
  // ... (constructor and describeYourself method remain the same)
}

// Create a new instance (object) of Vehicle
const coolSkiVan = new Vehicle("Cool Ski Van", 4);

console.log(coolSkiVan); // Output: Vehicle { description: "Cool Ski Van", wheels: 4 }

coolSkiVan.describeYourself(); // Output: I am a Cool Ski Van with 4 wheels.
Use code with caution.
In this example, we create a new coolSkiVan object using the new keyword and the Vehicle class. The constructor is invoked, setting the description and wheels properties for this specific coolSkiVan instance. By calling coolSkiVan.describeYourself(), we execute the method inherited from the Vehicle class, resulting in the informative message about the cool ski van.

Inheritance: Specialization Through Class Extension

Classes can be further enhanced using inheritance. Inheritance allows you to create new classes (subclasses) that inherit properties and behaviors from an existing class (superclass). This promotes code reusability and enables the creation of specialized object types:

JavaScript
class Vehicle {
  // ... (constructor and describeYourself method remain the same)
}

class SemiTruck extends Vehicle {
  constructor(description, wheels) {
    // Call superclass constructor with super()
    super(description, wheels);
  }
}

// Create a new instance (object) of SemiTruck
const bigRig = new SemiTruck("Big Rig", 18);

bigRig.describeYourself(); // Output: I am a Big Rig with 18 wheels.
Use code with caution.
Here, we establish a new class, SemiTruck, that extends the Vehicle class. The extends keyword signifies inheritance. Within the SemiTruck constructor, we leverage the super() function to call the constructor of the superclass (Vehicle), ensuring that the description and wheels properties are initialized appropriately for the SemiTruck instance.

In Conclusion: Classes for a Structured and Reusable JavaScript Journey

Classes empower you to craft reusable and well-organized code in JavaScript. By leveraging classes and inheritance, you can establish a foundation for building complex applications that maintain a clean and maintainable codebase. As you embark on your JavaScript development adventures, embrace classes to streamline your object creation and promote code reusability.