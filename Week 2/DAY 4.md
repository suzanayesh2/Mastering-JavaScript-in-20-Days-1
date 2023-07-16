# DAY 4: Classes & Prototypes (OOP)
## Lesson summary : 
* Core of development :
1. Save data (e.g. in a quiz game the scores of user1 and user2)
1. Run code (functions) using that data (e.g. increase user 2’s score)
* The principle of encapsulation is store functions with their associated data!
* Our code is getting repetitive, we're breaking our DRY principle. And suppose we have millions of users! What could we do?
  * Solution 1. Generate objects using a function:
  * Problems: Each time we create a new user we make space in our computer's memory for all our data and functions. But our functions are just copies.
  * Solution 2: Using the prototype chain (_The Core Solution_):
  * All objects have a __ proto __ property by default which defaults to linking to a big object - Object.prototype full of (somewhat) useful functions
  * Solution 3 - Introducing the keyword that automates the hard work: new
    * When we call the function that returns an object with new in front we automate 2 things
    1. Create a new user object
    2. Return the new user object
   * Solution 4: The class ‘syntactic sugar’





---
## Code Examples:
#### Iterate Over All Properties:
* You have now seen two kinds of properties: own properties and prototype properties. Own properties are defined directly on the object instance itself. And prototype properties are defined on the prototype.
```javascript
function Dog(name) {
  this.name = name;
}

Dog.prototype.numLegs = 4;

let beagle = new Dog("Snoopy");

let ownProps = [];
let prototypeProps = [];

// Only change code below this line
for(let property in beagle){
  if (beagle.hasOwnProperty(property)){
      ownProps.push(property)
  }else {
    prototypeProps.push(property)
  }
}

console.log(ownProps);
console.log(prototypeProps);
```
#### Remember to Set the Constructor Property when Changing the Prototype:
* There is one crucial side effect of manually setting the prototype to a new object. It erases the constructor property! This property can be used to check which constructor function created the instance, but since the property has been overwritten, it now gives false results.
* To fix this, whenever a prototype is manually set to a new object, remember to define the constructor property:
```javascript
  function Dog(name) {
  this.name = name;
}

// Only change code below this line
Dog.prototype = {
  constructor:Dog,
  numLegs: 4,
  eat: function() {
    console.log("nom nom nom");
  },
  describe: function() {
    console.log("My name is " + this.name);
  }
};
```
#### Use a Mixin to Add Common Behavior Between Unrelated Objects:
* Behavior is shared through inheritance. However, there are cases when inheritance is not the best solution. Inheritance does not work well for unrelated objects like Bird and Airplane. They can both fly, but a Bird is not a type of Airplane and vice versa.
* For unrelated objects, it's better to use mixins. A mixin allows other objects to use a collection of functions.
```javascript
let bird = {
  name: "Donald",
  numLegs: 2
};

let boat = {
  name: "Warrior",
  type: "race-boat"
};

// Only change code below this line
let glideMixin = function(obj){
  obj.glide = function(){
    console.log(" I am gliding!!")
  }
}
glideMixin(bird);
glideMixin(boat);
```
#### Understand the Immediately Invoked Function Expression (IIFE):
* Note that the function has no name and is not stored in a variable. The two parentheses () at the end of the function expression cause it to be immediately executed or invoked. This pattern is known as an immediately invoked function expression or IIFE.
```javascript
// function makeNest() {
//   console.log("A cozy nest is ready");
// }

// makeNest();
// Is equal to : 
(function(){
    console.log("A cozy nest is ready");
}) ();
```
* An immediately invoked function expression (IIFE) is often used to group related functionality into a single object or module.
```javascript
let isCuteMixin = function(obj) {
  obj.isCute = function() {
    return true;
  };
};
let singMixin = function(obj) {
  obj.sing = function() {
    console.log("Singing to an awesome tune");
  };
};

let funModule = (function () {
  return {
    isCuteMixin: function(obj) {
      obj.isCute = function() {
        return true;
      };
    },
    singMixin: function(obj) {
      obj.sing = function() {
        console.log("Singing to an awesome tune");
      };
    }
  }
})();
```
## Code Example:
[Use Prototype Properties to Reduce Duplicate Code](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/object-oriented-programming/use-prototype-properties-to-reduce-duplicate-code)
```javascript
function Dog(name) {
  this.name = name;
}

Dog.prototype.numLegs = 4;

let beagle = new Dog("Snoopy");

console.log(beagle.numLegs); // Output: 4

```
