# DAY 4: Classes & Prototypes (OOP)
## Lesson summary : 
* Core of development :
1. Save data (e.g. in a quiz game the scores of user1 and user2)
1. Run code (functions) using that data (e.g. increase user 2’s score)



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
