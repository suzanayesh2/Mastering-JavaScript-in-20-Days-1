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
* To interact with the features that the browser offers, JavaScript offers "facade functions" that look like JavaScript, but are actually part of the browser. Examples of these functions include console (which is console in web browser), fetch/xhr(network request), document(HTML DOM), and setTimeout(Timer).

 #### Web API Example('setTimeout()'):
* When setTimeout is called, it doesn't break the rule of JavaScript being single-threaded.
#### Callback Queue And Event Loop:
* the functionality of the event loop, which ties the call stack and callback queue together.

 ### [Pair programming challenges :Asynchronicity](http://csbin.io/async)
 ###### Note: We recommend that after you complete a challenge, you re-comment out the test case for that challenge so the console output is not confusing when working on subsequent challenges.
#### My solution 
 ```javascript
/* CHALLENGE 1 */

function sayHowdy() {
  console.log('Howdy');
}

function testMe() {
  setTimeout(sayHowdy, 0);
  console.log('Partnah');
}
// After thinking it through, uncomment the following line to check your guess!
 //testMe(); // what order should these log out? Howdy or Partnah first? Answer : Partnah FIRST THEN Howdy .


/* CHALLENGE 2 */

function delayedGreet() {
  // ADD CODE HERE
  setTimeout(()=>{
    console.log("welcome")
  },3000)
}
// Uncomment the following line to check your work!
 //delayedGreet(); // should log (after 3 seconds): welcome


/* CHALLENGE 3 */

function helloGoodbye() {
  // ADD CODE HERE
  console.log("hello")
  setTimeout(()=>{
      console.log("good bye")

  },2000)
}
// Uncomment the following line to check your work!
 //helloGoodbye(); // should log: hello // should also log (after 3 seconds): good bye


/* CHALLENGE 4 */

function brokenRecord() {
  // ADD CODE HERE
  console.log("hi again")
  setTimeout(brokenRecord,1000)
}
// Uncomment the following line to check your work!
 //brokenRecord(); // should log (every second): hi again

/* CHALLENGE 5 */

function limitedRepeat() {
  let count = 0;
  let id = setInterval(() => {
    console.log("hi for now");
    count++
    if(count >= 5) {
      clearInterval(id)
    }
  }, 1000)
}
// Uncomment the following line to check your work!
// limitedRepeat(); // should log (every second, for 5 seconds): hi for now

/* CHALLENGE 6 */

function everyXsecsForYsecs(func,interval,duration) {
  // ADD CODE HERE
   let count = 0;
  let id = setInterval(() => {
func()
    count+=interval
    if(count >= duration) {
      clearInterval(id)
    }
  }, interval)
}

// Uncomment the following lines to check your work!
// function theEnd() {
//   console.log('This is the end!');
// }
// everyXsecsForYsecs(theEnd, 2, 20); // should invoke theEnd function every 2 seconds, for 20 seconds): This is the end!
```

##  Promises :
## Lesson summary : 
* #### There is a problem in ES5 Web Browser APIs with callback functions such that : Callback hell. So ES6+ comes with a solution : Promises
* Using two-pronged ‘facade’ functions that both:
  - Initiate background web browser work and
  - Return a placeholder object (promise) immediately in JavaScript
  - Special objects built into JavaScript that get returned immediately when we makea call to a web browser API/feature (e.g. fetch) that’s set up to return promises(not all are)
   - Promises act as a placeholder for the data we expect to get back from the web browser feature’s background work

* This diagram explains what happens in the _code example below_ involving both web browser APIs and promises.
   * The problem begins by instantiating functions into the global memory, then a setTimeout function is called, and a fetch call is made to a Twitter API. It's demonstrated how each of these things end up in the context of the web browser, callback queue, or call stack.
   * The promise is returned by the fetch call, and the "then" statement is reached and the function call is placed on the callback queue. The thread of execution is then blocked by a function, and a log statement is reached.
![1689287470974](https://github.com/M-Alsuleibi/Mastering-JavaScript-in-20-Days/assets/73719352/63bac9f0-849b-427b-9cea-104c8ae12cd8)

```javascript
function display(data){console.log(data)}
function printHello(){console.log("Hello");}
function blockFor300ms(){// blocks js thread for 300ms }
setTimeout(printHello, 0);
const futureData = fetch('https://twitter.com/will/tweets/1')
futureData.then(display)
blockFor300ms()
console.log("Me first!");
```
* Rules for the execution of our asynchronously delayed code: 
 1. Hold promise-deferred functions in a microtask queue and callback function in a task queue (Callback queue) when the Web Browser Feature (API) finishes
 1. Add the function to the Call stack (i.e. run the function) when:
    - Call stack is empty & all global code run (Have the Event Loop check this condition)
 3. Prioritize functions in the microtask queue over the Callback queue
# Code Exercises:
[Question 1](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day3-tasks/tasks.md)
## My Solution with CHATGPT Assessment:
##### Note: I tried to figure out what to pass in callback parameter in the given [task](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day3-tasks/tasks.md) but i get confused . So i get help from openAI hoping have a clearer idea about it.
```javascript
const executeInSequenceWithCBs = (tasks, callback) => {
    const messages = [];
    let completedTasks = 0;
  
    const executeTask = (task) => {
      task((message) => {
        messages.push(message);
        completedTasks++;
  
        if (completedTasks === tasks.length) {
          callback(messages);
        } else {
          executeTask(tasks[completedTasks]);
        }
      });
    };
  
    executeTask(tasks[0]);
  };
  executeInSequenceWithCBs(asyncTasks, (messages) => {
    console.log(messages);
  });
```
