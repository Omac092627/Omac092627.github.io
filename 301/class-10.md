Call Stack:

A call stack is a mechanism for an interpreter (like the JavaScript interpreter in a web browser) to keep track of its place in a script that calls multiple functions — what function is currently being run and what functions are called from within that function, etc.

When a script calls a function, the interpreter adds it to the call stack and then starts carrying out the function.
Any functions that are called by that function are added to the call stack further up, and run where their calls are reached.
When the current function is finished, the interpreter takes it off the stack and resumes execution where it left off in the last code listing.
If the stack takes up more space than it had assigned to it, it results in a "stack overflow" error.

LIFO: When we say that the call stack, operates by the data structure principle of Last In, First Out, it means that the last function that gets pushed into the stack is the first to be pop out, when the function returns.

What causes a stack overflow?
A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error.

The key takeaways from the call stack are:
1. It is single-threaded. Meaning it can only do one thing at a time.
2. Code execution is synchronous.
3. A function invocation creates a stack frame that occupies a temporary memory.
4. It works as a LIFO — Last In, First Out data structure.


Reference errors
This is as simple as when you try to use a variable that is not yet declared you get this type os errors.

This is also a common thing when using const and let, they are hoisted like var and function but there is a time between the hoisting and being declared so when you try to access them a reference error occurs, the fact that this happens to let and const is called Temporal Dead Zone (TDZ).
foo = 'Hello' // Uncaught ReferenceError: foo is not defined
let foo

Whatever you are using (var, let or const) the fix is as simple has declaring the variable before any declaration is made.
let foo;
foo = 'Hello'

Syntax errors
I know it’s in the name of the errors, but like it says itself, this occurs when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse.
JSON.parse( {'foo': 'bar'} ) // Uncaught SyntaxError: Unexpected token o in JSON at position 1
This can be solved by just fixing the syntax, in this case the object should be a JSON.
JSON.parse('{"foo":"bar"}')

Range errors
Try to manipulate an object with some kind of length and give it an invalid length and this kind of errors will show up.
var foo= []
foo.length = foo.length -1 // Uncaught RangeError: Invalid array length
An array for instance cannot have a negative length, why would you mess with the array length? Some people use it to set an array to empty, something of the likes of:
var foo = [0, 0]
foo.length = foo.length - 2 // (or foo.length - foo.length)
foo // would log [] instead of [0, 0]
I prefer not to mutate my variables whenever possible (making them constants and not variables) but this is a method that is available and now you know it.

Type errors
Like the name indicates, this types of errors show up when the types (number, string and so on) you are trying to use or access are incompatible, like accessing a property in an undefined type of variable.


DEBUGGING
To debug your JS code, the easiest and maybe the most common way its to simply console.log() the variables you want to check or, by using chrome developer tools, open your page with your JS code (press cmd+o in macOS or Ctrl+o in Windows) and choose your file to debug, click the line you wanna debug and refresh your page again (F5).