# Readings: Classes, Inheritance, Functional Programming

---
## Review, Research, and Discussion

In your reading notes page for this class, provide answers to the following prompts. Cite any external sources

### Why would you want to run JavaScript code outside of a browser?
    Running JavaScript inside a browser means you are interacting with Web UI (HTML and CSS components) which is displayed on a user's screen. Running JavaScript without/outside a browser means you are using node. js technology to execute your JavaScript code.

[source](https://www.quora.com/What-exactly-does-running-JavaScript-inside-a-browser-and-outside-of-a-browser-mean#:~:text=Running%20JavaScript%20inside%20a%20browser%20means%20you%20are%20interacting%20with,to%20execute%20your%20JavaScript%20code.)

---

### What is the difference between a module and a package?
    A module is a single JavaScript file that has some reasonable functionality. A package is a directory with one or more modules inside of it and a package. json file which has metadata about the package. Now it's very common for people to refer to a package as a module.

[source](https://stackoverflow.com/questions/20008442/difference-between-a-module-and-a-package-in-node-js#:~:text=A%20module%20is%20a%20single,has%20metadata%20about%20the%20package.&text=Now%20it's%20very%20common%20for,a%20package%20as%20a%20module.)

---

### What does the node package manager do?
    Provides hosting for software development and hosting using git.
---

### Provide code snippets showing 3 different ways to export a function from a node module

Example:

exports.SimpleMessage = 'Hello world';



Example: 

module.exports.SimpleMessage = 'Hello world';



Example:

module.exports = {
    getUser,
    getUsers
}

---


### Document the following Vocabulary Terms

| Term                          | Definition|
| ----------------------------- | ----------------------------- |
| ecosystem                     | collection of libraries       |      
| Node.js                       | runtime environment           |     
| V8 Engine                     | Event Loop/Asynchronous queue |
| module                        | single JS file                |
| package                       | multiple JS files             |
| node package manager (`npm`)  | host for modules/packages     |
| server                        | CRUD                          |    
| environment                   | Dev playground                |    
| interpreter                   | Reads in browser              |
| compiler                      | Converts to machine code      |




---

## Preview
Skim the following materials in preparation for the upcoming lecture. Note the following as you browse the material, and be prepared to participate in discussions during lecture

### Which 3 things had you heard about previously and now have better clarity on?
    ecosystems, node.js, and the v8 engine.


### Which 3 things are you hoping to learn more about in the upcoming lecture/demo?
    react, backend, more react.



### What are you most excited about trying to implement or see how it works?

    Testing out server side applications.
