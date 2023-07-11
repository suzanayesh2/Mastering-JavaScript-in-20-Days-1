# DAY 1: Introduction, JavaScript Principles, Functions & Callbacks: 
# Introduction And JavaScript Principles:
## Lesson Summary:
When JavaScript code runs, it :
1. Goes through the code line-by-line and runs/ ’executes’ each line - known as **the thread of execution**
1. Saves ‘data’ like strings and arrays so we can use that data later - in its **memory** We can even save code (functions)
1. Execution context: Functions Created to run the code of a function - has 2 parts :
   * Thread of execution
   * Memory

4. **Call stack** : JavaScript keeps track of what
function is currently running
(where’s the thread of execution)
### The three core components of JS :
1. Memory to store data 
1. Thread of execution to go run line-by-line
1. Call stack to keep track where is our thread of execution is using our call stack 
# Functions & Callbacks:
## Lesson Summary:
* Generalize the function to make it reusable and to preserve the the principle _**DRY**_(Don't Repeat Yourself)
    * Parameters mean we don’t need to decide what data to run our functionality on until we run the function and then 
    * Then provide an actual value (argument) when we run the function.
* Callbacks and high order functions:
   * Higher-order funcion is the outer function that takes in a function or passes out a funcion
   * Callback function is the one we insert in.
* In JavaScript, all functions are first class functions.Functions that can be assigned to a variable, passed into another function, or returned from another function just like any other normal value, are called first class functions. 
 # Coding Exercises:
 * [Use Higher-Order Functions map, filter, or reduce to Solve a Complex Problem](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-higher-order-functions-map-filter-or-reduce-to-solve-a-complex-problem)
  ## My solution :
  ```javascript
    const squareList = arr => {
  // Only change code below this line
  return arr
          .filter(num => num > 0 && num % parseInt(num) === 0)
          .map(num => num * num);
  // Only change code above this line
   };

  ```
* [Apply Functional Programming to Convert Strings to URL Slugs](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/apply-functional-programming-to-convert-strings-to-url-slugs)
## My solution :

```javascript
// Only change code below this line
function urlSlug(title) {
return title
    .split(" ")
    .filter(substr => substr !== "")
    .join("-")
    .toLowerCase();

}
// Only change code above this line
urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone");
```
## Exercises for functions and callbacks:

* [Question 1: Functions and Callbacks](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day1-tasks/tasks.md)
## My solution :
```javascript
async function mapAsync(arr,instruction){
    const output = []
    for(let i = 0;i<arr.length;i++){
        output.push(instruction(arr[i]))
    }
    return output
} 
const result = mapAsync([1,2,3],input => input+3)
console.log(result); // prints : Promise { [ 4, 5, 6 ] }
```
* [Question 2: Call Stack and Recursion](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day1-tasks/tasks.md)
## My solution :
### with recursion
```javascript
function sumRange(r1,r2){ 
    if(r1==r2){
        return r1
    }else{

        return (r1 + sumRange(r1 + 1 ,r2));

    }
}
console.log(sumRange(1,7)); // prints: 28
```
### Without recursion:
```javascript
function sumRange(r1, r2) {
    let sum = 0;
    if (r1 < r2) {
        for (let i = r1; i <= r2; i++) {
            sum += i;
        }
    }
    return sum

}
const sum =sumRange(1, 7)
console.log(sum); // prints: 28
```



    
