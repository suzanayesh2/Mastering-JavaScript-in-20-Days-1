# DAY 3: Asynchronous JavaScript And Promises 
##  Asynchronous JavaScript:
## Lesson summary : 
* JS is a synchronous, blocking, single-threaded language. That just means that only one operation can be in progress at a time.
    * JavaScript is:
      - Single threaded (one command runs at a time)
      - Synchronously executed (each line is run in order the code appears)
#### Asynchronousity in javascript:
* JavaScript engine has 3 main parts:
  - Thread of execution
  - Memory/variable environment
  - Call stack
* We need to add some new components:
  - Web Browser APIs/Node background APIs
  - Promises
  - Event loop, Callback/Task queue and micro task queue
#### Asynchronous Browser Features:
* To interact with the features that the browser offers, JavaScript offers "facade functions" that look like JavaScript, but are actually part of the browser. Examples of these functions include console, fetch, document, and setTimeout.

 #### Web API Example('setTimeout()'):
* When setTimeout is called, it doesn't break the rule of JavaScript being single-threaded.


