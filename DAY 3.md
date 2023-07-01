# DAY 3: Quiz Project And Quiz Project Functions


## I intend to summarize the knowledge acquired from the Frontend Master videos. However, since I don't currently have access to these courses via my GitHub Education benefits pack, which is still unavailable, I will focus on summarizing FreeCodeCamp coding exercises and including code implementation. As per GSG guidelines, once the benefits become accessible, I will watch the videos and update this file accordingly.
# Coding Exercises
* [Global Scope and Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-scope-and-functions)
## My Solution
```javascript
// Declare the myGlobal variable below this line
let myGlobal=10

function fun1() {
  // Assign 5 to oopsGlobal here
  oopsGlobal=5
}

// Only change code above this line
```
* [Local Scope and Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/local-scope-and-functions)
## My Solution 
```javascript
function myLocalScope() {
  // Only change code below this line
  let myVar=9
  console.log('inside myLocalScope', myVar);
}
myLocalScope();
```
* [Global vs. Local Scope in Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-vs--local-scope-in-functions)
  ## My Solution
```javascript
// Setup
const outerWear = "T-Shirt";

function myOutfit() {
  // Only change code below this line
 const outerWear = "sweater"
  // Only change code above this line
  return outerWear;
}

myOutfit();
```

* [Stand in Line](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/stand-in-line)
  ## My Solution
```javascript
function nextInLine(arr, item) {
  // Only change code below this line
  arr.push(item)
  return arr.shift();
  // Only change code above this line
}
```
