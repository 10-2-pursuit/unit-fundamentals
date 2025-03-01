# Objects

## Introduction

Let's say you are tasked with creating a car inventory app. A car has a lot of properties like brand, model, color, year, price, and more.

Is there a suitable datatype we've learned to fit this kind of data?

If we put it in an array, it would look something like this:

```js
const carArray = ["Mazda", "CX-5", "Meteor Gray", 2015, 19_999, true, "fair"];
```

If you had to use this data, you would have to remember the property at each index. You would have to be careful to update the correct index. What would happen if you had 100 properties? What would happen if someone made a mistake and swapped two values or accidentally made the array too short?

An array is the wrong datatype for this kind of data.

We need a new datatype called an object. An object has keys and values. Let's rebuild our car data as an object:

```js
const carObject = {
  brand: "Mazda",
  model: "CX-5",
  color: "Meteor Gray",
  year: 2015,
  price: 19_999,
  passedInspection: true,
  condition: "fair",
};
```

Every value has a descriptive key, and it is easy to understand what each property is refering to. In this lesson, you'll learn how to access, add, and update properties in an object.

## Learning Objectives

- Define what an object is and describe its properties
- Create an object with the object literal syntax.
- Access values in an object through bracket and dot notation.
- Update values in an object with bracket and dot notation.
- Add key-value pairs to an object with bracket and dot notation.
- Loop over an object.
- Differentiate between arrays and objects.

<hr>

## Introduction to objects

To create an object, you start with curly braces.

```js
const myObj = {};
console.log(myObj);
```

Objects contain key-value pairs that are separated by a colon `:`, and a comma separates each key-value pair.

```js
const giftBox = {
  fruit: "Pears",
  candle: "Peach scented",
  soap: "Milky rose",
  price: 100,
  colorTheme: "Winter Delights",
};

console.log(giftBox);
```

## Accessing elements in an object

To access an object's property (or value), you can use dot notation. Dot notation requires the exact key:

```js
console.log(giftBox.candle);
```

You can also use square brackets, which will evaluate the value first. You can either enter the key as a string or save the key to a variable:

```js
const kindOfGift = "soap";

console.log(giftBox["soap"]);
console.log(giftBox[kindOfGift]);
```

## Changing key-value pairs

You can change a value by accessing its key and assigning it a new value.

```js
giftBox.price = 99;
console.log(giftBox.price);
```

## Adding a key-value pair

You can add a new key-value pair if the key does not exist.

```js
giftBox.chocolate = "Hazelnut overload";
console.log(giftBox);
```

## Iterating over an object

There are two common ways to iterate over an object.

The first is to use a method that takes all the keys and makes them into an array.

```js
const giftBoxKeys = Object.keys(giftBox);
console.log(giftBoxKeys);
```

Now that you have an array, you can use a `for` loop.

```js
for (let i = 0; i < giftBoxKeys.length; i++) {
  console.log(giftBoxKeys[i], giftBox[giftBoxKeys[i]]);
}
```

You can also use a `for in` loop, which will give you keys to iterate. In the control panel of this `for` loop, the value `key` can be anything. You can name it `asdf` or anything you like. `in` is a reserved keyword that defines what kind of for loop this is, and finally, the object you are iterating over is the final piece of the control panel.

```js
for (let key in giftBox) {
  console.log(key);
}
```

You can then use those keys to access the property:

```js
for (let key in giftBox) {
  console.log(giftBox[key]);
}
```

## Compare and contrast objects and arrays

What are the similarities you notice? What are the differences?

We can imagine an array as an object, where the keys are the index position. The array has extra properties, for example, the numbered keys always go in order and it has special methods like `.pop()` and `.push()` that are not available for an object.

```js
const mockArray = {
  0: "first item",
  1: "second",
  2: "third",
};
```

## JSDoc object notation

An object can have properties that are numbers, strings, booleans and more. You can also have an array of objects. When commenting with JS Docs, you would do so like this"

```js
/**
 * Examples of how to note arrays with different data types
 * @param {Object} employee - The entire employee object
 * @param {string} employees.name - The employee's name, which is part of an object, which is a string
 * @param {Object[]} employees - An array of employee objects
 */
```

[JSDoc params](https://jsdoc.app/tags-param.html)
