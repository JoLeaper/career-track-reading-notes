# Class 01 Reading

Question 1. Why would you want to run JavaScript code outside of a browser?

Answer: For backend development, thanks to Node.js. 

Question 2. What is the difference between a module and a package?

Answer: A module is a singular JavaScript file that has functionality. A package is a group of modules where there is a package.json file and sometimes includes metadata.

Referenced (https://stackoverflow.com/questions/20008442/difference-between-a-module-and-a-package-in-node-js, answer 2)

Question 3. What does the node pacakage manager do?

Answer: It puts modules into place so that node can find them and manages dependency conflicts intelligently.

Referenced (https://docs.npmjs.com/cli/npm)

Question 4. Provide code snippers showing 3 different ways to export a function from a node module.

```js
    // export as function 
    module.exports = function () {
        console.log('hello')
    }
```

```js
    // export as anonymous function
    const helloMe = () => {
        return 'hello Me'
    }
    exports.helloMe = helloMe;
```

```js
// export as class
    module.exports = function () { 
    this.name = 'Joey'; 
    this.info = () => { 
        console.log(`My Name - ${this.name}`); 
     } 
} 
```
Referenced (https://www.geeksforgeeks.org/node-js-export-module/ AND https://www.sitepoint.com/understanding-module-exports-exports-node-js/)

| Term   | Definition  |
|---|---|
| **ecosystem**  | 'a collection of software projects, which are developed and co-evolve in the same environment' -Mircea Lungu  |
| **Node.js**  | A JavaScript environment/module that allows JavaScript to be used server-side.  |
| **V8 Engine**  | A webengine that improves performance (especially with Node.js)  |
| **module** |  Similar to a JavaScript library. Pre-written code that adds additional mechanisms to JavaScript.  |
| **package**  | A file/directory, described in package.json. |
| **npm**  | node pacakage manager.  |
| **server**  | The back-end, databases, etc.  |
| **environment**  | Where a code is being executed.  |
| **interpreter**  | Something that reads over all the JavaScript lines and interprets them. (https://web.stanford.edu/class/cs98si/slides/overview.html)|
| **compiler**  | transforms code written by humans into source code, which can be read by the computer |