# DAY 2: Closures
## Lesson Summary:
* A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function's scope from an inner function. In JavaScript, closures are created every time a function is created, at function creation time. **Ref** [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)
* When a function is defined, it gets a bond to the surrounding Local Memory (“Variable Environment”) in which it has been defined.
* _Recommended readings_
   * [I never understood JavaScript closures](https://medium.com/dailyjs/i-never-understood-javascript-closures-9663703368e8) _article_
   * [If Hemingway Wrote JavaScript](https://nostarch.com/hemingway). _A book by Angus Croll_.
* Closure technical definition and review:
    * What can we call this ‘backpack’?
        - Closed over ‘Variable Environment’ (C.O.V.E.)
        - Persistent Lexical Scope Referenced Data (P.L.S.R.D.)
        - ‘Backpack’
        - ‘Closure’
* [Pair programming challenges](http://csbin.io/closures) and [solutions](https://github.com/FrontendMasters/fm-snippets/blob/main/javascript-hard-parts-v2/closures.js) . 

# Coding Exercises:
### Question 1:
Write a closure named createCounter that takes an initial value start and returns a function. The returned function, when invoked, should increment the counter by 1 and return the updated value.
### My solution:
```javascript
function createCounter(start) {
  let counter = start;

  function incrementCounter () {
    counter++;
    return counter;
  }

  return incrementCounter ;
}

const counter = createCounter(1);

console.log(counter()); // Output: 2
console.log(counter()); // Output: 3

```
### Question 2:
Write a closure named calculateAverage that takes an array of numbers, nums, and returns a function. The returned function, when invoked, should calculate and return the average of the numbers in the array.
### My solution:
```javascript
function calculateAverage(nums) {
    let sum = 0;
    let count = nums.length;
  
    nums.forEach((num) => {
      sum += num;
    });
  
    return function () {
      return sum / count;
    };
  }
  const nums = [1, 2, 3, 4];
  const average = calculateAverage(nums);

   console.log(average()); // Prints: 2.5
```
### Question 3:
Write a closure named powerOf that takes a base number base and returns a function. The returned function, when invoked with an exponent exp, should calculate and return the result of base raised to the power of exp.
### My solution:
```javascript
function powerOf(base) {
    function exponentFun(exp) {
        return base ** exp;
    }
    return exponentFun
}

let base = 2;
const result = powerOf(base)
console.log(result(2)); // Prints: 4
```
### Question 4:
Write a closure named compose that takes multiple functions as arguments and returns a new function. The returned function should apply the provided functions in reverse order, passing the result of each function as an argument to the next function.
### My solution:
```javascript
function compose(...functions){ //????????
    return function (){

    }

}
```

