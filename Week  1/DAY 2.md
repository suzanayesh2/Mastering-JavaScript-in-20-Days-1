# DAY 2 : Expressions, Arrays And Objects
# Expressions:
## Lesson Summary:
*  * 4 / 2 * 10
   * "Frontend" + "Masters"
    * 5 > 4 !== 3 > 4   
  ARE examples of expressions  (_an expression evaluates to a value_)
* Variables point(not contan) to values
* An expression asks JavaScript for a value, while a statement tells JavaScript to do something.


# Coding Exercises
* [Profile Lookup](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/profile-lookup)
## My Solution
```javascript
function lookUpProfile(name, prop) {
  // Only change code below this line
  for (let i = 0; i < contacts.length; i++) {
    if(contacts[i].firstName === name) {
      return contacts[i][prop] || "No such property";
    }
  }
  return "No such contact";

 
    // Only change code above this line
}

``` 
* [Copy Array Items Using slice()](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/copy-array-items-using-slice)
## My Solution
```javascript
function forecast(arr) {
  // Only change code below this line
  const array = arr.slice(2,4)
  return array;
}

```
* [Combine Arrays with the Spread Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/combine-arrays-with-the-spread-operator)
* ## My Solution

```javascript

function spreadOut() {
  let fragment = ['to', 'code'];
  let sentence = ['learning',...fragment,'is','fun']; // Change this line
  return sentence;
}

console.log(spreadOut());
```
