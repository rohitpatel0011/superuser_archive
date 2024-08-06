---
title: Iterating The for...of Loop in JavaScript
date: 2021-03-12
draft: false
description: "
JavaScript equips you with a powerful arsenal of tools for manipulating data. A crucial aspect of this manipulation involves traversing or iterating over collections of elements. The for...of loop, introduced in ES6, simplifies this process by offering a concise and versatile syntax for iterating through various iterable objects like arrays, strings, maps, and sets.
"
image: "/images/javascript_strings.webp"
imageBig: "/images/javascript_strings.webp"
categories: ["javascript", ]
authors: ["superuser"]
avatar: "/images/avatar.webp"
---


### Understanding Iterables: A Foundation for for...of

An iterable object is essentially a collection that can be looped over, allowing you to access its elements one by one. Arrays, strings, maps, and sets all qualify as iterables in JavaScript. The for...of loop takes advantage of this inherent iterability to provide a clean and efficient way to process each element within an iterable.

Iterating over Strings: Extracting Characters

**Let's embark on a practical exploration using a string:**

```javascript
for (let letter of "JavaScript") {
  console.log(letter); // Output: J, a, v, a, S, c, r, i, p, t
}
```
In this example, we iterate through the characters of the string "JavaScript". The for...of loop automatically extracts each character and assigns it to the variable letter within each iteration. The console.log(letter) statement then prints each character to the console on a new line.

## Iterating over Arrays: Processing Elements

Arrays, being another common iterable, also benefit from for...of:

```javascript
const topics = ["JavaScript", "Node", "CSS"];

for (let topic of topics) {
  console.log(topic); // Output: JavaScript, Node, CSS
}
```
Here, we loop through the topics array, containing a list of programming languages. The for...of loop iterates over each element (topic name) and logs it to the console.

Iterating over Maps: Exploring Key-Value Pairs

Maps, a versatile data structure introduced in ES6, can also be effectively navigated using for...of:

JavaScript
const learningResources = new Map();
learningResources.set("HTML", "/topic/html");
learningResources.set("CSS", "/topic/css");
learningResources.set("JavaScript", "/topic/javascript");

for (let topic of learningResources) {
  console.log(topic); // Output: [HTML, "/topic/html"], [CSS, "/topic/css"], [JavaScript, "/topic/javascript"]
}
Use code with caution.
In this scenario, we create a learningResources map to store associations between programming languages and their corresponding learning URLs. The for...of loop iterates over the map, but it's important to understand that it directly iterates over the key-value pairs themselves, returning an array containing the key and value in each iteration.

Extracting Specific Values: Using .keys() and .values() methods

If you're solely interested in the keys or values within a map, you can leverage the built-in keys() and values() methods alongside for...of:

JavaScript
for (let key of learningResources.keys()) {
  console.log(key); // Output: HTML, CSS, JavaScript
}

for (let value of learningResources.values()) {
  console.log(value); // Output: "/topic/html", "/topic/css", "/topic/javascript"
}
Use code with caution.
Here, we demonstrate iterating over both keys and values. The keys() method returns an iterable of the map's keys, while values() provides an iterable of the values. By incorporating these methods within the for...of loop, we can specifically target the desired data.

Key-Value Pairs with .entries()

Maps also offer the .entries() method, which returns an iterable of key-value pairs as separate elements within the loop:

JavaScript
for (let [key, value] of learningResources.entries()) {
  console.log(`The course description for ${key} can be found at ${value}`);
  // Output: The course description for HTML can be found at /topic/html
  // Output: The course description for CSS can be found at /topic/css
  // Output: The course description for JavaScript can be found at /topic/javascript
}
Use code with caution.
In this example, we leverage destructuring within the for...of loop to unpack the key-value pairs returned by .entries(). This allows us to directly access both the key (course name) and value (learning URL