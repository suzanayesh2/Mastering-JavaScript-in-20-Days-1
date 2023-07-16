# DAY 1: Introduction,Types And Coercion
# Introduction:
## Lesson Summary:
* [Kyle Simpson](https://github.com/getify) introduces the course and makes a case for why it matters to think deeply about JavaScript. He said that [JS specification](https://262.ecma-international.org/9.0/#Title) is the source of authority not the JS engine!
* Kyle describes how incorrect assumptions about how code is working causes bugs. He start to analyse the spec of ++ operator (the postfix operator) in this case .
* Kyke claims that Whenever there's a divergence between what your brain thinks is happening, and what the computer does, that's where **bugs** enter the code.
* JavaScript devides into three main pillars :
  1. Types:( Primitive Types, Abstract Operations, Coercion, Equality, TypeScript, Flow, etc)
  2. Scope:( Nested Scope, Hoisting, Closure, Modules)
  3. Objects (Oriented):( this, class { }, Prototypes, OO vs. OLOO)

# Types:
## Lesson Summary:
* _null_ primitive type is _not_ considered as an object!
* In JavaScript, variables don't have types, values do.
* We can use utilites like ```typeof``` operator to know what the type of a value which is always return a string e.g ```"undefined"``` :
    * ```typeof(null)``` will return the string ```"object"``` !!! . This is because a bug in JS spec! simple as that.
* Concepts of emptiness:  undefined vs. undeclared vs. uninitialized (aka TDZ):
  * undefined mean there is definitly a variable ,and at the moment it has no value 
  * undeclared mean it is never been created in any scope that we have access to
  * [temporal dead zone](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let#temporal_dead_zone_tdz)
* NaN(invalid number) so it is a number and it's an invalid one according to IEEE 754 spec and it is the only value that doesn't have the identity proprety (NaN === NaN //false! ) .
* [Type check exercise and solution](https://github.com/M-Alsuleibi/Mastering-JavaScript-in-20-Days/tree/main/Week%203/Object-is-exersice)
     - _Note_: A polyfill is a piece of code that provides a service that you, the developer, expect it to provide natively

# Coercion:
## Lesson Summary:
* Coercion is a type conversion in JS
* Abstract Operations :ToPrimitive(hint),ToString ,ToNumber and ToBoolean .
* the term _boxing_ refers to _implicit coercion_ which we see an example of it like using methods on primitive value. e.g :
  ```javascript
  if(studentName.length()>20){
  console.log("Name is too long!);
  }
  ```
   ---
# Code Exercises:
#### Question 1: Write a function called convertStringToNumber that converts a string to a number using the unary plus operator. If the input is not a string, return an object of the input's value and type.
#### My Solution:
```javascript
function convertStringToNumber(input) {
    //write your own code here
    if (typeof (input) === "string") {
        return +input;
    } else {
        const obj = {
            value: input,
            type: typeof (input)
        }
        return obj;
    }
}


console.log(convertStringToNumber("45"));
console.log(convertStringToNumber(22));
```
#### Question 2: Write a function called checkNaN that takes a single argument and returns true if the argument is NaN and false otherwise.
#### My Solution:
```javascript
const checkNaN = (value) => {
    //write your own code here
    if(value !== value && isNaN(value)==true){
    return true
    }else{
        return false
    }
  }

  console.log(checkNaN(NaN));
  console.log(checkNaN(34));
  console.log(checkNaN("Hi"));
  console.log(checkNaN([]));
  console.log(checkNaN({}));
```
#### Question 3: Write a function called isEmptyValue that checks if a given input is an empty value (undefined, null, or empty string).
#### My Solution:
```javascript
function isEmptyValue(value) {
    //write your own code here
    if (Boolean(value) === false) {
        return true;
    }else return false 
}

// console.log(Number(undefined)); // Nan
// console.log(Number(null)); // 0
// console.log("".length); // 0
// console.log(Number("")); // 0

console.log(isEmptyValue(465));
console.log(isEmptyValue(""));
console.log(isEmptyValue(null));
console.log(isEmptyValue(undefined)); 

```
#### Question 4: Write a function called compareObjects that takes 2 arguments of type "object" and compares them. If both arguments are equal, return true. If not, return false. If either argument is not of type "object", the function should return an array of the arguments.
#### My Solution:
```javascript
function compareObjects(input1, input2) {
    //write your own code here
    if ((typeof input1 === "object") || (typeof input === "object")) {
        return true
    } else if (typeof input1 !== "object" && typeof input2 !== "object") {
        return false;
    } else {
        return [input1, input2]
    }
}

console.log(compareObjects([3, 43], { "id": 342, "name": "Rami" }));
console.log(compareObjects([3, 43], 8));
console.log("hi","bye");
console.log("hi",8);
```
