# DAY 2 : Expressions, Arrays And Objects
# Expressions:
## Lesson Summary:
*  * 4 / 2 * 10
   * "Frontend" + "Masters"
    * 5 > 4 !== 3 > 4   
  ARE examples of expressions  __an expression evaluates to a value__   


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
