# Class 02 Reading

Question 1. Name 3 advantages to Test Driven Development

Answer: Receive instant feedback on code, cements an understanding of the code being written, simplifies the code being written.

References(https://dzone.com/articles/20-benefits-of-test-driven-development)

Question 2. In what case would you need to use beforeEach() or afterEach() in a test suite?

Answer: beforeEach is used when there is a global state that needs to be used by other tests, afterEach is for cleaning up that will be used by other tests.

Referenced (https://jestjs.io/docs/en/api#aftereachfn-timeout)

Question 3. What is one downside of Test Driven Development?

Answer: It requires time and effort to be frontloaded which can create the illusion of slow development. Tests, also, cannot cover everything.

Referenced (https://leantesting.com/test-driven-development/)

**Question 4. What is the primary difference between ES6 classes and Constructor/Prototype Classes?**

**Answer: ???**

Question 5. Name a use case for a static method

Answer: Creating utility functions (such as grabbing user data) in applications.


**Question 6. Write an example of a Higher Order function and describe the user case it solves.**

**Answer: ???** 
```js
const pokemonArray = [pokemonObject1, pokemonObject2, pokemonObject3];

render () {
    return { pokemonArray.map(pokemon => {
        pokemon.Name;
    })}
}

```

| Term   | Definition  |
|---|---|
| **functional programming**  | The process of building software using nothing but function (avoids shared state, mutable data, and side-effects).  |
| **pure function**  | Functions that return the same result if the same arguments are passed in. They do not make network requsts or mutate data. |
| **higher-order function**  | A function that either takes in a function as an argument or returns a function. |
| **immutable state** |  State that cannot be changed.  |
| **object**  | A data-type that is meant to represent a real-world item or concept. It has properties and methods unique to it.  |
| **object-oriented programming**  | Rather than making a program around functions and logic, object-oriented programming is a model that designs around the data or objects.  |
| **class**  | 'Special Function' that can be used to define function expressions and declarations |
| **prototype**  | How JavaSCript objects inherit features from one another.  |
| **super**  | Used to access and call function in an object's parent. |
| **inheritance**  | An object's ability to access methods and other properties from another object |
| **constructor**  | A function that initializes an object |
| **instance**  | Installation of a class |
| **context**  | The object within the function being executed |
| **this**  | A property of an execution context (global, function or eval) that, in non–strict mode, is always a reference to an object and in strict mode can be any value (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this) |