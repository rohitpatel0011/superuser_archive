---
title: Separating Data and Functions Separated but Working Together in JavaScript (Functional Style)
date: 2021-03-12
draft: false
description: "
In the world of programming, there are two main ways to organize things: object-oriented programming (OOP) and functional programming (FP). Today, we're focusing on a key difference between the two - how they handle data and functions.
"
image: "/images/javascript_strings.webp"
imageBig: "/images/javascript_strings.webp"
categories: ["javascript", ]
authors: ["superuser"]
avatar: "/images/avatar.webp"
---

**Data Everywhere!**
Data is the heart of any program and we can say  "**The Fuel of Programs"**. It can be anything from names and addresses to car models and video game character stats.

In the world of programming, we have two main choreography styles for organizing things: object-oriented programming **(OOP)** and functional programming **(FP)**
 Today, we'll delve into a key difference between these styles - how they handle data and functions, the essential building blocks of any program.

Data: The Fuel of Programs

Data is the lifeblood that pumps through any program's veins. It can be anything from customer information and financial records to product details and high scores. Here's how OOP and FP treat this data:

**OOP**: Imagine data as precious jewels stored in ornate treasure chests. These chests are objects, and you can only access the jewels inside using the chest's special tools (methods).

**FP:** Things are more transparent here. Data resides in simple containers like baskets or bowls (similar to OOP objects). This allows for easier access and manipulation.

## Taking Action: Functions

Functions are the actions we perform on our data. They're like the chefs in our programming kitchen, taking ingredients (data) and transforming them into something useful (results). Here's how OOP and FP approach these functions:

OOP: Functions live within the objects themselves, alongside the data they work with. They have a special key that allows them to directly access and modify the data within the object.

FP: Functions are completely separate entities from the data. We "pass" the data to the function as arguments, like giving a recipe and ingredients to a chef. Importantly, these functions shouldn't alter the original data, but rather create a new dish (modified copy). This ensures predictability and avoids errors in the kitchen (your program).

Why the Separation in FP?

This separation of data and functions in FP might seem like an unusual recipe at first, but it has some significant benefits:

Clearer Code: Separating concerns makes the code easier to understand and maintain, like a well-organized kitchen where everything has its designated place.
Fewer Errors: Functions can't accidentally mess up the original data, leading to fewer bugs and unexpected results in your program. Imagine a chef accidentally adding salt instead of sugar because the ingredients weren't labeled properly!
Reusable Functions: Functions can work with different data sets, making them more versatile. It's like having a chef who can whip up delicious meals with various ingredients, not just following a single recipe.
Putting it into Practice: A JavaScript Example

Let's look at a JavaScript example that demonstrates this separation:

Data (Array of Cars):

JavaScript
const cars = [
  { model: 'Yaris', year: 2020, color: 'red' },
  { model: 'Corolla', year: 2023, color: 'blue' },
  { model: 'Camry', year: 2022, color: 'silver' },
];
Use code with caution.
Function (Separate Entity):

JavaScript
function findCarsAfterYear(cars, year) {
  // Filter the original array to create a new one (immutability)
  const newerCars = cars.filter(car => car.year > year);
  return newerCars;
}
Use code with caution.
Explanation:

We have an array cars containing information about different cars.
The findCarsAfterYear function is completely independent of the cars data, acting as a separate tool in our programming kitchen.
It takes two arguments: cars (the array) and year (the filter criteria).
We use the filter method to create a new array (newerCars) containing only cars with a model year greater than the provided year. This follows the principle of immutability in functional programming, ensuring the original cars data remains unchanged.
The function returns the new newerCars array, containing the filtered results.
Using the Function:

JavaScript
const carsAfter2021 = findCarsAfterYear(cars, 2021);
console.log(carsAfter2021); // Output: Array containing only 2022 and 2023 cars
Use code with caution.
This example showcases how functions in FP operate on data passed as arguments. This separation promotes cleaner, more maintainable, and reusable code, ultimately leading to well-organized and reliable programs - like a delicious meal prepared by a skilled chef with a clean and efficient kitchen!

As you can see, OOP and FP offer different ways to manage data and functions. While OOP provides a more bundled approach, FP emphasizes separation and immutability. Both approaches have their merits, and the best choice for your project depends on the specific requirements and desired outcome.