# DAY 1: Introduction,Types And Coercion
# Introduction:
## Lesson Summary:
* [Kyle Simpson](https://github.com/getify) introduces the course and makes a case for why it matters to think deeply about JavaScript. He said that [JS specification](https://262.ecma-international.org/9.0/#Title) is the source of authority not the JS engine!
* Kyle describes how incorrect assumptions about how code is working causes bugs. He start to analyse the spec of ++ operator (the postfix operator) in this case .
* Kyke claims that Whenever there's a divergence between what your brain thinks is happening, and what the computer does, that's where **bugs** enter the code.
* JavaScript devides into three main pillars :
  1. Types:( Primitive Types, Abstract Operations, Coercion, Equality, TypeScript, Flow, etc)
  2. Scope:( Nested Scope, Hoisting, Closure, Modules)
  3. Objects (Oriented):( this, class { }, Prototypes, OO vs. OLOO)

# Types:
## Lesson Summary:
* _null_ primitive type is _not_ considered as an object!
* In JavaScript, variables don't have types, values do.
* We can use utilites like ```typeof``` operator to know what the type of a value which is always return a string e.g ```"undefined"``` :
    * ```typeof(null)``` will return the string ```"object"``` !!! . This is because a bug in JS spec! simple as that.


