# DAY 1 : Introduction,DOM,Values & Data Types And Operators

# Introduction:
[Frontend Masters course “JavaScript First Steps"](https://frontendmasters.com/workshops/javascript-first-steps/) which constructed by _[Anjana Vakil](https://twitter.com/AnjanaVakil)_. This course will lead you through your first steps with the JavaScript programming language, equip you with the key concepts & skills you need to become a productive JS programmer, and give you a solid foundation for your onward journey into advanced JS, functional programming, frontend frameworks, and beyond.
# DOM:
## Lesson Summary:
* DOM as tree of objects JS dealing with in web pages.
* .getElementById ,.querySelector,.length and much more document methods to see in [MDN](https://developer.mozilla.org/en-US/)
   * Exercise code example __[tic tac toe](https://anjana.dev/javascript-first-steps/1-tictactoe.html)__:
  ##### // Find the letter X in p1 element 
   * ```javascript
     // Find the letter X in p1 element 
        const textX=document.getElementById("p1-symbol").textContent;

     ```
    ##### //Find the number of squares 
   * ```javascript
     const squares = document.querySelectorAll(".square").length;


     ```
    ##### //Change the player names to you & neighbor
   * ```javascript
      document.getElementById('p1-name').textContent ="mohammad"


     ```
# Values & Data Types :
## Lesson Summary:
* typeof operator
* Primitive data types:
    * strings(made of character units) , numbers ,boolean, undefine ...etc
* Objects:
    * includes null as a historical mistake when JS had implemented as i understood.
#### Exercise code example __[tic tac toe](https://anjana.dev/javascript-first-steps/1-tictactoe.html)__:
  ##### //Capitalize the heading "Tic Tac Toe"

   * ```javascript
      document.querySelector('h1').textContent.toUpperCase();


     ```
# Operators:
## Lesson Summary:
* * ,+, -, / , %,> , < , ===, == , !== , ..etc

     
 # Coding Exercises
* [Find the Length of a String](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/find-the-length-of-a-string)
## My Solution
```javascript
// Setup
let lastNameLength = 0;
const lastName = "Lovelace";

// Only change code below this line
lastNameLength = lastName.length ;

``` 
* [Use Bracket Notation to Find the Nth-to-Last Character in a String](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-bracket-notation-to-find-the-nth-to-last-character-in-a-string)

## My Solution
```javascript
// Setup
const lastName = "Lovelace";

// Only change code below this line
const secondToLastLetterOfLastName = lastName[lastName.length -2]; // Change this line

``` 
