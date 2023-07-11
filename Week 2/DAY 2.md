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
* [Pair programming challenges](http://csbin.io/closures). 

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
