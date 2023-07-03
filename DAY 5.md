# DAY 5:Data Fetching & Promises, Destructuring Data ,Async And Modules
This README provides an overview of the JavaScript lessons covering Data Fetching & Promises, Destructuring Data ,Async And Modules. Each topic is briefly summarized below in my own words.

# Data Fetching & Promises:
## Lesson Summary:
Here are the key points covered:
* APIs provide URLs that point at data we want.
* fetch() function use JS to load resource or piece of  data from APIs. It returns Promise.
* Promises is a construct in JS that represent a value that we don't have yet!
  * promises can be in three states :
     * Pending 
     * Fulfilled
     * Rejected
* fetch() is asynchronous function which return a promise. So we use **await** keyword to wait and capture that promise in an object (response) .So await going to deal with fetch as a synchronous operation .
* response object have alot of information include **body** which we interested in. so to retrive body data we use json()(response.json())
* **response.json()** also return a promise so we use **await** again e.g :
  
```javascript
let body = await response.json();
```
to finally access body data.
