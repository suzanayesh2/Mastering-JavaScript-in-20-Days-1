# Day 4 : Events & handlers ,Conditionals ,Map & filter And Doggos Quiz Game

This README provides an overview of the JavaScript lessons covering Events & Handlers, Conditionals, and Map & Filter. Each topic is briefly summarized below in my own words.

# Events & handlers:
## Lesson Summary:
Here are the key points covered:
* Events are being fired from web browser when a certain things happen. and these events need to be handeled by a hendler.
* Events can be detected with JS using an event listener . event listener is a mehod on a DOM element and it takes two pameters. First one is the name of the event.Second one is an arrow function  which is serve as a callback or an event handler function. Anytime the event being fired ,JS going to take this arrow function and run whatever code inside it.
* Event object passed as parameter to handler function ,which carries details about exactly what happened.e.g event.target is the element the event fired on.

# Conditionals
## Lesson Summary:

* JS evaluation boolean when using If statment to its Truthiness or falseness 
## Code Example 
```javascript
if (0) {
    console.log("zero is truthy");
} else {
    console.log("zero is falsy");
} // prints zero is falsy
```
```javascript
if ([]) {
    console.log("empty array is truthy");
} else {
    console.log("empty array is falsy");
} // prints empty array is truthy
// because array is an object(its something!)
```
*  for .. of loop iterate over items in a collection more easily than traditional loops
# Map & filter
## Lesson Summary:

  * ***map*** calls a function on each item in an array to create new array .
  *  ***filter*** calls a true/false function on each item and creates a new array only with items where the function returns true
  *  ***Spread(...)*** is another trick for iterating over arrays.Can be used to put all the items from one array inside another array
        * We can use it also to pass all elemnts of an array as an argument to a function:
```javascript
    const skills = ["HTML", "CSS", "JS"];
    const newSkills = ["React", "TypeScript", "Node"]
    skills.push(...newSkills);
    console.log(...skills);
```

# Coding Exercises:
* [Use Multiple Conditional (Ternary) Operators](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-multiple-conditional-ternary-operators)
## My Solution
```javascript
function checkSign(num) {
return (num=== 0)? "zero"
        : (num >0)? "positive"
        :"negative";
}

checkSign(10);
```

* [Golf Code](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/golf-code)
## My Solution:
```javascript
const names = ["Hole-in-one!", "Eagle", "Birdie", "Par", "Bogey", "Double Bogey", "Go Home!"];

function golfScore(par, strokes) {
  // Only change code below this line
  if(strokes === 1){
    return names [0]
  }else if(strokes <= par-2){
    return names [1] 
  }else if(strokes === par-1 ){
    return names [2]
  }else if(strokes === par){
    return names [3]
  }else if (strokes === par +1){
    return names [4]
  }else if (strokes === par+2){
    return names [5]
  }else if (strokes >= par +3){
    return names [6]
  }else{

  return "Change Me";
  }
  // Only change code above this line
}

golfScore(5, 4);
```
* [Use the map Method to Extract Data from an Array](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-the-map-method-to-extract-data-from-an-array)
  ## My Solution:
```javascript

```
