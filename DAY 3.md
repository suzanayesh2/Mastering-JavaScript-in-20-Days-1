# DAY 3: Quiz Project And Quiz Project Functions
# Quiz Project:
* we start our quiz project with a starter [_strater_](https://anjana.dev/javascript-first-steps/2-jsquiz-starter.html) ,we learned to open it in VS Code. Here the exercise with related solution code :
  * Exercise
     * declare statement, optionButtons, and explanation variables with their corresponding element(s).
       
         ```javascript
          const statement = document.getElementById("statement");
          const optionButtons = document.querySelector("#options").children;
           const explanation = document.getElemntById("explanation"); 
        ```
     * create a facts object representing one true/false fact you've learned about JS.
        ```javascript
          const fact = {
                statement :" Arrays are like objects",
                answer : true,
                explanation:"Arrays are a kind of object with special properties"
        }; 
        ```
     * use the statement element to display your fact.
        ```javascript
            statement.textContent = fact.statement;
        ```
           
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
