# Node Ecosystem, TDD, CI/CD

---

## Review, Research, and Discussion
In your reading notes page for this class, provide answers to the following prompts. Cite any external sources

1. Describe (in plain English) what Array.map() does
    - Array.map() creates a new array populated with the results of calling a provided function on every element in the calling array.
    
    - In laymens terms - using Array.map() allows you to populate a new array using an existing array of information based on what you tell the function to do. 
    
    - Example - Array.map(x => x * 2), input - [1,2,3,4,5], output - [2,4,6,8,10]

    - [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)



2. Describe (in plain English) what Array.reduce() does
    - Array.reduce() executes a reducer function (that you provide) on each element of the array, resulting in a single output value.

    - In laymens terms - you provide a function to the Array.reduce method that allows you to add, subtract, divide, and so on, to each item in the array and produce a single output.

    - Example - 
    const array1 = [1,2,3,4];
    reducer = (accumulator, currentValue) => accumulator + currentValue;
    console.log(array1.reduce(reducer))
    Output = 10

    - [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)


---

### Code Snippets for Superagent

Provide code snippets showing how to use superagent() to fetch data from a URL and log the result


1. With normal Promise .then() syntax

    Example:

        const superagent = require('superagent');

        let myArray = [1,2,3,4,5,6];

        function isEven(number){

        return new Promise((resolve, reject) =>{
        if(number % 2 === 0){
            resolve('Is Even');
        }else{
            reject(false);
        }
        })
        }

        for(let i = 1; i < myArray.length; i++){
        isEven([i])
        .then( result => console.log(i, result))
        .catch(err => console.log());
        }

        isEven(4)
        .then( status => console.log('Success:', status))
        .catch(err => console.error('Error:', err))


2. Again with async / await syntax

    Example:
    
        async function whereWeGoin(cityName){
        let results = await superagent.get('https://geocode.xyz/chicago?json=1');
        console.log(results.body);
        console.log('Longitude: ', results.body.longt);
        console.log('Latitude: ', results.body.latt);
        }



        whereWeGoin();


3. Explain promises as though you were mentoring a Code 301 level student

    - The Promise object represents the eventual completion (or failure) of an asynchronous operation and its reulting value.

    - A promise is basically a facade for a value not necessarily known when the promise is created.


4. Are all callback functions considered to be Asynchronous? Why or Why Not?

    - Callback functions are Asynchronous. Asynchronous items go into a queue until the other main code has run. Callbacks do the same, they go onto the callback queue as explained per The Event Loop. As long as the callback is an asynchronous callback.

---

## Preview

Skim the following materials in preparation for the upcoming lecture. Note the following as you browse the material, and be prepared to participate in discussions during lecture

### Which 3 things had you heard about previously and now have better clarity on?

    - I have heard of the Chrome V8 engine, but I honestly never looked under the hood. Learning about The Event Loop was fascinating and I still do not completely understand it. I mean, I get the gist of the how the process works, but when it came to more complicated problems, I would have to spend more time understanding. Overall, I know about data structures, and how the stack and the heap operate, I didn't know that Chrome's V8 engine was functioning in a non-blocking I/O functionality. A single threaded i/o engine that can process multiple calls with a queue. Bravo.

    - The second thing would be asynchronous calls using superagent. It's been quite a while since using superagent but I forgot how effective it is. Being able to make calls to an api to retrieve data with asynchronous methods is a great advantage. As opposed to always using callbacks or promises, you can set timeouts among other things to make calls when you want to.

    - Lastly, I forgot how much fun Javascript is. For the last 4 months I've been doing .Net/C#. The language is so strict it would turn off anyone who's used to Javascript. It puts a smile on my face to be able to learn stronger foundations utilizing a loosely typed language. I hope to apply the knowledge I've gained from my past 401 and expand my knowledge.


### Which 3 things are you hoping to learn more about in the upcoming lecture/demo?

    - I'm hoping to learn more about React. I love backend, but front-end is where I shine. Design and theme make so much difference when it comes to overall product of a site. My dream job is to work at Netflix and hopefully as a front-end engineer as I feel I could bring a lot to the table for such an established company.

    - Secondly, I hope to better my skills in data structures and algorithms. I've grown a lot over the past year in my programming abilities and the true test is Data Structures. Getting a job is no easy feat. When it comes time to perform the monkey test and get a job, I want to be ready. What better way to do that than to practice, practice, practice.

    - Lastly, I hope to learn how to listen better. Listening is such a powerfull skill because the more you listen the more you know. I love to talk and entertain people, listening was never my strong suit growing up. That is, until I really became aware that I wasn't listening enough to anything. Paying attention, taking notes, and participating is how I plan to get ahead. 

### What are you most excited about trying to implement or see how it works?

    - I'm most excited about project week. Putting together a new project with a fresh group of people is something I'm excited for. I have so many ideas and I love to help people in their quest to bring their ideas to life as well. 

---

## Preparation Materials

1. NodeJS

[NodeJS Introduction](https://www.w3schools.com/nodejs/nodejs_intro.asp)

What is Node.js?
Node.js is an open source server environment
Node.js is free
Node.js runs on various platforms (Windows, Linux, Unix, Mac OS X, etc.)
Node.js uses JavaScript on the server

Why Node.js?
Node.js uses asynchronous programming!

A common task for a web server can be to open a file on the server and return the content to the client.

Here is how PHP or ASP handles a file request:

Sends the task to the computer's file system.
Waits while the file system opens and reads the file.
Returns the content to the client.
Ready to handle the next request.
Here is how Node.js handles a file request:

Sends the task to the computer's file system.
Ready to handle the next request.
When the file system has opened and read the file, the server returns the content to the client.
Node.js eliminates the waiting, and simply continues with the next request.

Node.js runs single-threaded, non-blocking, asynchronously programming, which is very memory efficient.

What Can Node.js Do?
Node.js can generate dynamic page content
Node.js can create, open, read, write, delete, and close files on the server
Node.js can collect form data
Node.js can add, delete, modify data in your database
What is a Node.js File?
Node.js files contain tasks that will be executed on certain events
A typical event is someone trying to access a port on the server
Node.js files must be initiated on the server before having any effect
Node.js files have extension ".js"


---

2. What Exactly is NodeJS?

[What is NodeJS](https://www.freecodecamp.org/news/what-exactly-is-node-js-ae36e97449f5/)

Node.js is a JavaScript runtime environment. Sounds great, but what does that mean? How does that work?

The Node.js run-time environment includes everything you need to execute a program written in JavaScript.

Node.js came into existence when the original developers of JavaScript extended it from something you could only run in the browser to something you could run on your machine as a standalone application.

Now you can do much more with JavaScript than just making websites interactive.

JavaScript now has the capability to do things that other scripting languages like Python can do.

Both your browser JavaScript and Node.js run on the V8 JavaScript runtime engine. This engine takes your JavaScript code and converts it into a faster machine code. Machine code is low-level code which the computer can run without needing to first interpret it.

Blocking I/O
In the blocking method, user2's data request is not initiated until user1's data is printed to the screen.

If this was a web server, we would have to start a new thread for every new user. But JavaScript is single-threaded (not really, but it has a single-threaded event loop, which we’ll discuss a bit later). So this would make JavaScript not very well suited for multi-threaded tasks.

That’s where the non-blocking part comes in.

Non-blocking I/O
On the other hand, using a non-blocking request, you can initiate a data request for user2 without waiting for the response to the request for user1. You can initiate both requests in parallel.

This non-blocking I/O eliminates the need for multi-threading since the server can handle multiple requests at the same time.


---


3. Introduction to NPM -> Node Package Manager

[what is npm](https://docs.npmjs.com/about-npm/index.html)

npm is the world’s largest software registry. Open source developers from every continent use npm to share and borrow packages, and many organizations use npm to manage private development as well.

npm consists of three distinct components:

the website
the Command Line Interface (CLI)
the registry
Use the website to discover packages, set up profiles, and manage other aspects of your npm experience. For example, you can set up Orgs (organizations) to manage access to public or private packages.

The CLI runs from a terminal, and is how most developers interact with npm.

The registry is a large public database of JavaScript software and the meta-information surrounding it.

Use npm to . . .
Adapt packages of code for your apps, or incorporate packages as they are.
Download standalone tools you can use right away.
Run packages without downloading using npx.
Share code with any npm user, anywhere.
Restrict code to specific developers.
Create Orgs (organizations) to coordinate package maintenance, coding, and developers.
Form virtual teams by using Orgs.
Manage multiple versions of code and code dependencies.
Update applications easily when underlying code is updated.
Discover multiple ways to solve the same puzzle.
Find other developers who are working on similar problems and projects.

---

## Bookmark

[nodeJS docs](https://nodejs.org/en/docs/)

[npm docs](https://docs.npmjs.com/)

