# Debugging


HOW TO DEBUG FOR BEGINNERS


Without fail, the code we write as software developers doesn’t always do what we expected it to do. Sometimes it does something completely different! When this happens, the next task is to figure out why, and although we might be tempted to just keep staring at our code for hours, it’s much easier and efficient to use a debugging tool, or debugger.

A debugger, unfortunately, isn’t something that can magically reveal all the problems or “bugs” in our code. Debugging means to run your code step by step in a debugging tool like Visual Studio, to find the exact point where you made a programming mistake. You then understand what corrections you need to make in your code, and debugging tools often allow you to make temporary changes so you can continue running the program.

Using a debugger effectively is also a skill that takes time and practice to learn but is ultimately a fundamental task for every software developer. In this article, then, we introduce the core principles of debugging and provide tips to get you started.

Clarify the problem by asking yourself the right questions
It helps to clarify the problem that you ran into before you try to fix it. We expect that you already ran into a problem in your code, otherwise you wouldn't be here trying to figure out how to debug it! So, before you start debugging, make sure you've identified the problem you're trying to solve:

What did you expect your code to do?

What happened instead?

If you ran into an error (exception) while running your app, that can be a good thing! An exception is an unexpected event encountered when running code, typically an error of some kind. A debugging tool can take you to the exact place in your code where the exception occurred and can help you investigate possible fixes.

If something else happened, what is the symptom of the problem? Do you already suspect where this problem occurred in your code? For example, if your code displays some text, but the text is incorrect, you know that either your data is bad or the code that set the display text has some kind of bug. By stepping through the code in a debugger, you can examine each and every change to your variables to discover exactly when and how incorrect values are assigned.

Examine your assumptions
Before you investigate a bug or an error, think of the assumptions that made you expect a certain result. Hidden or unknown assumptions can get in the way of identifying a problem even when you are looking right at the cause of the problem in a debugger. You may have a long list of possible assumptions! Here are a few questions to ask yourself to challenge your assumptions.

Are you using the right API (that is, the right object, function, method, or property)? An API that you're using might not do what you think it does. (After you examine the API call in the debugger, fixing it may require a trip to the documentation to help identify the correct API.)

Are you using an API correctly? Maybe you used the right API but didn't use it in the right way.

Does your code contain any typos? Some typos, like a simple misspelling of a variable name, can be difficult to see, especially when working with languages that don’t require variables to be declared before they’re used.

Did you make a change to your code and assume it is unrelated to the problem that you're seeing?

Did you expect an object or variable to contain a certain value (or a certain type of value) that's different from what really happened?

Do you know the intent of the code? It is often more difficult to debug someone else's code. If it's not your code, it's possible you might need to spend time learning exactly what the code does before you can debug it effectively.

 Tip

When writing code, start small, and start with code that works! (Good sample code is helpful here.) Sometimes, it is easier to fix a large or complicated set of code by starting with a small piece of code that demonstrates the core task you are trying to achieve. Then, you can modify or add code incrementally, testing at each point for errors.

By questioning your assumptions, you may reduce the time it takes to find a problem in your code. You may also reduce the time it takes to fix a problem.

Step through your code in debugging mode to find where the problem occurred
When you normally run an app, you see errors and incorrect results only after the code has run. A program might also terminate unexpectedly without telling you why.

Running an app within a debugger, also called debugging mode, means that the debugger actively monitors everything that’s happening as the program runs. It also allows you to pause the app at any point to examine its state, and to then step through your code line by line to watch every detail as it happens.

In Visual Studio, you enter debugging mode by using F5 (or the Debug > Start Debugging menu command or the Start Debugging button Start Debugging in the Debug Toolbar). If any exceptions occur, Visual Studio’s Exception Helper takes you to the exact point where the exception occurred and provides other helpful information. For more information on how to handle exceptions in your code, see Debugging techniques and tools.

If you didn't get an exception, you probably have a good idea where to look for the problem in your code. This is where you use breakpoints with the debugger to give yourself a chance to examine your code more carefully. Breakpoints are the most basic and essential feature of reliable debugging. A breakpoint indicates where Visual Studio should pause your running code so you can take a look at the values of variables, or the behavior of memory, or the sequence in which code runs.

In Visual Studio, you can quickly set a breakpoint by clicking in the left margin next to a line of code. Or place the cursor on a line and press F9.

To help illustrate these concepts, we take you through some example code that already has several bugs. We are using C#, but the debugging features apply to Visual Basic, C++, JavaScript, Python, and other supported languages.