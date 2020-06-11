History of .Net and C#:

C# relies on types and methods
.Net delivers those types and methods in a number of packages.
    Example: Exception processing --> rep errors


TOOLING:

.Net core is an open source general purpose dev platform. You can create .Net core apps for Windows, MacOS, Unix, and ARM processors using multiple programming languages. Dev platform languages and libraries. 

.Net core runs anywhere.
.Net framework: websites, services, apps on Windows.
 Xamarin/Mono: .net for mobile.

.Net standard is a set of libraries from above. 

You can find the output of code in the bin.

Ctrl+F5= run without debugging
F5= run with debugging

Applications run in terminal.

Basic debugging = diagnostics
    Autos, locals, watch = search state of objects, which allows you to sift through to find errors or specifics. Basically a console?

    Use Break Points and use F5 to run debugger on specific lines of code.
    
    Conditional breakpoints: hover over the breakpoint, click gear, then condition, then make a condition using an if statement.

    Debugginv vs. Release: use release when you're ready to ship your product.

Managed Codoe = code who's execution is managed by a runtime.

Common Language Runtime or CLR is main runtime language.
Managed code is written in one oof the higher level languages that can be run on top of .Net, such as: c#, visual basic, F# and others.

Intermediate Language and Execution: Once you compile your code written in one of these languages, you will get a binary made out of intermediate language.

Side note: framework libraries = base class libraries. 

Unmanaged code interoperability.

Unsafe context designates a piece of code for which the execution is not managed by the common language runtime.

Common Language Runtime:
    .Net framework provides a runtime enviroment called common language runtime which runs the code and provides services that make development easier.

The Runtime uses metadata to locate and load classes, layout instances in memory, resolve method invocations, generate native code, enforce security, and set runtime context boundaries.

