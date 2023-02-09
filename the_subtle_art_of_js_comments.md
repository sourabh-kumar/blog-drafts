
# The Subtle Art of Adding Code Comments in Javascript

![Heart made of 0s and 1s](https://images.unsplash.com/photo-1569396116180-210c182bedb8?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=869&q=80)

Adding code comments is important for several reasons:

1. **Code readability**: Comments help to clarify the intent behind the code and make it easier for other developers to understand what the code does.

2. **Maintenance**: Comments provide context for the code and make it easier to maintain and update the code in the future.

3. **Collaboration**: Comments facilitate collaboration between developers by providing context for code changes and helping to avoid misunderstandings.

4. **Documentation**: Comments serve as documentation for the code and can help to ensure that the code meets industry standards and best practices.

By taking the time to add meaningful and accurate comments to code, developers can improve the overall quality and maintainability of their projects.


## Mental Model for Code Comments

Before writing comments around a piece of code, it is important to be clear about the intent of doing so. A code comment is a communication mechanism that should communicate the following aspects of the code:

1. **Purpose**: Explain the purpose of the code, what problem it solves and why it exists.

2. **Input**: Specify the inputs required by the code, including their types, expected values and whether they are optional or mandatory.

3. **Output**: Specify the output produced by the code, including its type and any relevant details.

4. **Usage**: Provide examples of how to use the code, including relevant code snippets.

5. **Linking**: Add links to related code and external resources.

6. **Best practices**: Highlight any best practices or gotchas related to the code.

By following the right mental model, developers can ensure that their code is well-documented, easy to understand, and maintainable over time.
## Consistency & Standardisation

It is crucial to maintain consistency in the formatting and style of comments throughout the codebase. Using a tool such as [**JS Doc**](https://jsdoc.app/) (JavaScript documentation), which is a set of documentation standards and tools for documenting JavaScript code is a good option.

The following are some of JS Doc's features:

- It uses tags to capture information about the code's structure, function, parameters, return values, and other details to create a human-readable reference for other developers. 

- A JS Doc tags start with an `@`symbol, followed by the tag name and any relevant information. For example, the `@param` tag is used to describe a function parameter, while the `@returns` tag is used to describe the return value of a function. 

- It can generate docuemntation in HTML or other formats from inline comments in the source code.

Let's look at some of the most commonly used JS Doc tags in detail. For reference, we will be adding code comments to the following JS Code:

```javascript
function factorial(n) {
  if (typeof n !== "number") {
    throw new TypeError("Input must be a number");
  }
  if (n === 0) {
    return 1;
  }
  return n * factorial(n - 1);
}

function factorialWithCallback(n, callback) {
  try {
    const result = {
      input: n,
      output: factorial(n),
    };
    callback(null, result);
  } catch (error) {
    callback(error);
  }
}
```

Do not worry if it is unclear what the code accomplishes. The next sections will provide an explanation.
## Commonly used JS Doc Tags
## Commonly used JS Doc Tags
**`@description`**

Provides a detailed description of a function, object, or property. Let's see how the code looks after adding this tag.

```javascript
/**
 * @description A function that calculates the factorial of a number using recursion.
 */
function factorial(n) {
  if (typeof n !== "number") {
    throw new TypeError("Input must be a number");
  }
  if (n === 0) {
    return 1;
  }
  return n * factorial(n - 1);
}

/**
 * @description A version of the factorial function that returns the result via a callback.
 */
function factorialWithCallback(n, callback) {
  try {
    const result = {
      input: n,
      output: factorial(n),
    };
    callback(null, result);
  } catch (error) {
    callback(error);
  }
}

```
**`@param`**

It is used to describe the parameters of a function. Adding `@param` to the example, makes the code look like this:

```js
/**
 * @description A function that calculates the factorial of a number using recursion.
 * 
 * @param {number} n - The number for which to calculate the factorial.
 */
function factorial(n) {
  if (typeof n !== "number") {
    throw new TypeError("Input must be a number");
  }
  if (n === 0) {
    return 1;
  }
  return n * factorial(n - 1);
}

/**
 * @description A version of the factorial function that returns the result via a callback.
 * 
 * @param {number} n - The number for which to calculate the factorial.
 * @param {function} callback - The function to call with the result of the calculation.
 */
function factorialWithCallback(n, callback) {
  try {
    const result = {
      input: n,
      output: factorial(n),
    };
    callback(null, result);
  } catch (error) {
    callback(error);
  }
}


```
**`@returns`**

It is used to describe the return value of a function. Adding `@return` to the example, makes the code look like this:

```javascript
/**
 * @description A function that calculates the factorial of a number using recursion.
 * 
 * @param {number} n - The number for which to calculate the factorial.
 * 
 * @returns {number} The factorial of `n`.
 */
function factorial(n) {
  if (typeof n !== "number") {
    throw new TypeError("Input must be a number");
  }
  if (n === 0) {
    return 1;
  }
  return n * factorial(n - 1);
}

/**
 * @description A version of the factorial function that returns the result via a callback.
 * 
 * @param {number} n - The number for which to calculate the factorial.
 * @param {function} callback - The function to call with the result of the calculation.
 * 
 * @returns {void}
 */
function factorialWithCallback(n, callback) {
  try {
    const result = {
      input: n,
      output: factorial(n),
    };
    callback(null, result);
  } catch (error) {
    callback(error);
  }
}

```

**`@throws`**

It is used to describe any errors that the function can throw. Adding `@throws` to the example, makes the code look like this:

```javascript
/**
 * @description A function that calculates the factorial of a number using recursion.
 * 
 * @param {number} n - The number for which to calculate the factorial.
 * 
 * @returns {number} The factorial of `n`.
 * 
 * @throws {TypeError} If the input is not a number.
 */
function factorial(n) {
  if (typeof n !== "number") {
    throw new TypeError("Input must be a number");
  }
  if (n === 0) {
    return 1;
  }
  return n * factorial(n - 1);
}

/**
 * @description A version of the factorial function that returns the result via a callback.
 * 
 * @param {number} n - The number for which to calculate the factorial.
 * @param {function} callback - The function to call with the result of the calculation.
 * 
 * @returns {void}
 */
function factorialWithCallback(n, callback) {
  try {
    const result = {
      input: n,
      output: factorial(n),
    };
    callback(null, result);
  } catch (error) {
    callback(error);
  }
}


```


**`@example`**

It is used to provide an example of how to use a function or object. Adding `@example` to the example, makes the code look like this:

```javascript
/**
 * @description A function that calculates the factorial of a number using recursion.
 * 
 * @param {number} n - The number for which to calculate the factorial.
 * 
 * @returns {number} The factorial of `n`.
 * 
 * @throws {TypeError} If the input is not a number.
 * 
 * @example
 * factorial(5);
 * // returns 120
 */
function factorial(n) {
  if (typeof n !== "number") {
    throw new TypeError("Input must be a number");
  }
  if (n === 0) {
    return 1;
  }
  return n * factorial(n - 1);
}

/**
 * @description A version of the factorial function that returns the result via a callback.
 * 
 * @param {number} n - The number for which to calculate the factorial.
 * @param {function} callback - The function to call with the result of the calculation.
 * 
 * @returns {void}
 * 
 * @example
 * factorialWithCallback(5, (error, result) => {
 *   if (error) {
 *     console.error(error);
 *   } else {
 *     console.log(result);
 *   }
 * });
 * // logs { input: 5, output: 120 }
 */
function factorialWithCallback(n, callback) {
  try {
    const result = {
      input: n,
      output: factorial(n),
    };
    callback(null, result);
  } catch (error) {
    callback(error);
  }
}

```
**`@type`**, **`@typedef`** and **`@property`**

The `@type` JSDoc tag is used to specify the type of a variable, function, or expression. It provides additional information about the type of the entity being documented and helps with code readability and maintainability.

The `@typedef` JSDoc tag, on the other hand, is used to define a custom type. This can be useful in complex projects where you have custom data structures or types that need to be documented. The custom type defined with @typedef can then be referenced with the @type tag in other parts of the code.

In essence, `@typedef` is used to define a custom type, while `@type` is used to specify the type of an entity.

The `@property` JSDoc tag is used to document properties of an object or class. It is typically used in conjunction with @typedef to document the structure of an object or class. The @property tag specifies the name and type of a property, as well as a description of its purpose.

Adding `@type`, `@typedef` and `@property` to the example, makes the code look like this:

```javascript
/**
 * @typedef {Object} FactorialResult
 * 
 * @property {number} input - The input to the factorial function.
 * @property {number} output - The output of the factorial function.
 */

/**
 * @description A function that calculates the factorial of a number using recursion.
 * 
 * @param {number} n - The number for which to calculate the factorial.
 * 
 * @returns {number} The factorial of `n`.
 * 
 * @throws {TypeError} If the input is not a number.
 * 
 * @example
 * factorial(5);
 * // returns 120
 */
function factorial(n) {
  if (typeof n !== "number") {
    throw new TypeError("Input must be a number");
  }
  if (n === 0) {
    return 1;
  }
  return n * factorial(n - 1);
}

/**
 * @description A version of the factorial function that returns the result via a callback.
 * 
 * @param {number} n - The number for which to calculate the factorial.
 * @param {function} callback - The function to call with the result of the calculation.
 * 
 * @returns {void}
 * 
 * @example
 * factorialWithCallback(5, (error, result) => {
 *   if (error) {
 *     console.error(error);
 *   } else {
 *     console.log(result);
 *   }
 * });
 * // logs { input: 5, output: 120 }
 */
function factorialWithCallback(n, callback) {
  /**
   * @type {FactorialResult}
   */
  const result = {
    input: n,
    output: factorial(n),
  };
  try {
    callback(null, result);
  } catch (error) {
    callback(error);
  }
}

```

It is important to note the difference between `@param` and `@property` tags. The `@property` tag is used to describe the properties or attributes of an object or class, whereas the `@param` tag is used to describe the parameters of a function or method. Unlike the `@property` tag, the `@param` tag is used within the JSDocs block of a function or method, not outside it.


**`@callback`**

It is used to describe a callback function. The `@callback` tag specifies the parameters of the callback function and their types. Adding `@callback` to the example, makes the code look like this:

```javascript
/**
 * @typedef {Object} FactorialResult
 * 
 * @property {number} input - The input to the factorial function.
 * @property {number} output - The output of the factorial function.
 */

/**
 * @callback FactorialCallback
 * 
 * @param {Error} error - The error that occurred during the calculation, if any.
 * @param {FactorialResult} result - The result of the calculation.
 */

/**
 * @description A function that calculates the factorial of a number using recursion.
 * 
 * @param {number} n - The number for which to calculate the factorial.
 * 
 * @returns {number} The factorial of `n`.
 * 
 * @throws {TypeError} If the input is not a number.
 * 
 * @example
 * factorial(5);
 * // returns 120
 */
function factorial(n) {
  if (typeof n !== "number") {
    throw new TypeError("Input must be a number");
  }
  if (n === 0) {
    return 1;
  }
  return n * factorial(n - 1);
}

/**
 * @description A version of the factorial function that returns the result via a callback.
 * 
 * @param {number} n - The number for which to calculate the factorial.
 * @param {FactorialCallback} callback - The function to call with the result of the calculation.
 * 
 * @returns {void}
 * 
 * @example
 * factorialWithCallback(5, (error, result) => {
 *   if (error) {
 *     console.error(error);
 *   } else {
 *     console.log(result);
 *   }
 * });
 * // logs { input: 5, output: 120 }
 */
function factorialWithCallback(n, callback) {
  /**
   * @type {FactorialResult}
   */
  const result = {
    input: n,
    output: factorial(n),
  };
  try {
    callback(null, result);
  } catch (error) {
    callback(error);
  }
}

```

In this code, the `@callback` tag is used to define a custom type `FactorialCallback`, which is a callback function that is passed as a parameter to the `factorialWithCallback` function.

The `FactorialCallback` type is then referenced in the `@param` tag for the callback parameter of the `factorialWithCallback` function.
## Demo

A preview of the above snippet and the documentation that it generates can be checked [**here**](https://github.com/sourabh-kumar/js-doc-example).
## Summary

In conclusion, code comments provide a lot of benefits. From improving code readability to generating automatically generated documentation, tool such as [**JS Doc**](https://jsdoc.app/) are an essential part of any development toolkit. Whether you are a seasoned developer or just starting out, taking the time to document your code in a standardised way will not only benefit the product in the short-term, but it will also help ensure the longevity and maintainability of the codebase for years to come. I'd encourage everyone to adopt this powerful tool and start using it in the projects.