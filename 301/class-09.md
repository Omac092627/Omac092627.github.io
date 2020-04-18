REFACTORING FUNCTIONAL PROGRAMMING: 
    What is functional programming?
Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data

Pure function:
    The first fundamental concept we learn when we want to understand functional programming is pure functions. But what does that really mean? What makes a function pure?
    So how do we know if a function is pure or not? Here is a very strict definition of purity:
    It returns the same result if given the same arguments (it is also referred as deterministic)
    It does not cause any observable side effects

    Reading Files
If our function reads external files, it’s not a pure function — the file’s contents can change.

Random number generation
Any function that relies on a random number generator cannot be pure.

It does not cause any observable side effects
Examples of observable side effects include modifying a global object or a parameter passed by reference.
Now we want to implement a function to receive an integer value and return the value increased by 1.

Observation: mutability is discouraged in functional programming.

Pure functions benefits
The code’s definitely easier to test. We don’t need to mock anything. So we can unit test pure functions with different contexts:
Given a parameter A → expect the function to return value B
Given a parameter C → expect the function to return value D
A simple example would be a function to receive a collection of numbers and expect it to increment each element of this collection.