JAVASCRIPT:
  Execution context:
    Every statement in a script lives in one of three execution contexts:
      Global context: code that is in the script but not in a function. There is only one global context in any page.

      Function Context: 
        Code that is being run within a function.

      Eval context:
        Text is executed like code in an internal function.


      The Stack:
        The javascript interpreter processes one line at a time. When a statement needs data from another function, it stacks or piles the new function on top of the current task.

      Error Objects:
          When an error object is created, it will contain the following properties:
            Name: type of execution.
            Message: Description
            fileNumber: Name of the javascript file
            lineNumber: line number of error.

      There are seven types of built-in error objects in javascript. You'll see them on the next two pages:
          Error: generic error - the other errors are all based upon this error
          SyntaxError: Syntax has not been followed
          ReferenceError: tried to reference a variable that is not declared
          TypeError: An unexpected data type that cannot be coerced
          RangeError: Numbers not in acceptable range
          URIError: encodeURI(), decodeURI(), and similar methods used incorectly
          EvalError: eval () function used incorrectly