# DAY 5: Data Fetching & Promises, Destructuring Data ,Async And Modules
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
  * The Promise we get from fetch() resolves to a Response object. It's body contains the data we care about ( in console shows as ``` body : ReadableStream ``` ) this why we use .json()
# Destructuring Data( _const {👤, 🎂,📍 } = person_ )

## Lesson Summary:
* we can extrac values from an object with their property names (order does not matter).
* We can also destructure Arrays, assigning variables for their items (order matters).
* We can ignore specific properties/ values.
* we can use spread(...) to capture remaining values into array instead of expanding
  ##### code example:
  ```javascript
   const [babySpice, ...adultSpices] = spices;
  ```
# Async:
## Lesson Summary:
* We use _async_ keyword when declaring a function to fetch data as shown in code below:
  ```javascript
    async function fetchResponse(url) {
    const response = await fetch(url);
    return response;
   }
  ```
  * This fucntion will return a promise so we use the _await_ again to extract data as this function is already asynchronous operation.
   ```javascript
     await fetchResponse(url) 
  ```

# Modules:
## Lesson Summary:
* Modules let us split big codebases across multiple files.
* Modules create their own scope,so to let multiple module files access different data from each other, we use _import_ & _export_ .
   * export lets us expose variables from our module's scope to the outside world
   * import lets us use an exposed variable from another module
 * console.log() (or .warn() or .error()) is one way to understand what's happening when your program runs.
 * The debugger statement creates a breakpoint where JS will pause and let you look around
 * #### Error handling:
    _try_ lets us "watch out" for potential error its friend _catch_ lets us manage errors when they occur
*  Rick and Morty API Task:
  ## My solution:
  
```javascript
const url = "https://rickandmortyapi.com/api/character";

async function retrieveStatus(url) {
    try {
        const response = await fetch(url);
        const body = await response.json();
        for (let i = 0; i < body.results.length; i++) {
            if (body.results[i].status === "Alive") {
                const newli = document.createElement("li");
                const newContent = document.createTextNode(body.results[i].name);
                newli.appendChild(newContent);
                const currentUl = document.getElementById("characterList");
                document.body.insertBefore(newli, currentUl);


                // console.log(body.results[i].name, body.results[i].image,
                //              body.results[i].location,
                //              body.results[i].species, body.results[i].gender);
            };
        }
        // console.log(body.results[7].status);
    } catch (error) {
        console.log("ERROR!!", error);
    }


};
retrieveStatus(url);
// let  response =await fetch("https://rickandmortyapi.com/api/character")
// let body = await response.json();
//
// body.results[18].status

```
