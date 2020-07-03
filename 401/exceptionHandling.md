# Exception Handling

try Statements and Exceptions

    A try statement specifies a code block subject to error-handling or cleanup code.
    The try  block must be followed by a catch block, a finally block, or both. The catch block executes when an error occurs in the try block. The finally block executes after execution leaves the try block(or if the present, the catch block), to perform cleanup code, wheter or not an error occured. 

    A catch block has access to an Exception object that contains information about the error. You use a catch block to either compensate for the error or rethrow the exception. You rethrow an exception if you merely want to log the problem, or if you want to rethrow a new, higher-level exception type. 

    A finally block adds determinism to your program: the CLR endeavors to always execute it. It's useful for cleanup tasks such as closing network connections. 

            Example:    
                    try
                    {
                        //exception may get thrown within execution of this block
                    }
                    catch(ExceptionA ex)
                    {
                        //handle exception of type ExeptionA
                    }
                    catch(ExceptionB)
                    {
                        //handle exception of type ExceptionB
                    }
                    Finally
                    {
                        //cleanup the code
                    }



    The catch Clause
        A catch clause specifies what type of exception to catch. This must either be System.Exception or a subclass of System.Exception.

        Catching System.Exception catches all possible errors.

    Exception Filters
        You can specify an exception filter in a catch clause by adding a when clause:
            catch(WebException ex) when (ex.Status == WebExceptionStatus.Timeout)
            {
                ...
            }

    The finally Block
        The finally block always executes--whether or not an exception is thrown and whether or not the try block runs to completion. finally blocks are typically used for cleanup code. 

    The using statement
        Many classes encapsulate unmanaged resources, such as file handles, graphics handles, or database connections. These classes implement System.IDisposable, which defines a single paramterless method named Dispose to clean up these resources. The using statement provides an elegant syntax for calling Dispose on an IDisposable object within a finally block.

    Throwing Exceptions
        Exceptions can be thrown either by the runtime or in user code. 
    
    Throw Expressions
        Throw was always a statement prior to C# 7, now it can also appear as an expression in expression-bodied functions:
            public string Foo() => throw new NotImplementedException();

    Rethrowing an exception
        You can capture and rethrow an exception as follows:
            try{}
            catch (Exception ex)
            {
                //log error
                throw;
            }

    
    Key Properties of System.Exception
        The most important properties of System.Exception are 

            StackTrace - A string representing all the methods that are called from the origin of the exception to the catch block.

            Message - A string with a description of the error. 

            InnerException - The inner exception (if any) that caused the outer exception. This, itself, may have another InnerException.

    Common Exception Types
        The following exception types are used widely throughout the CLR and.NET Framework. You can throw these yourself or use them as base classes for deriving custom exception types. 

            System.ArgumentException - Thrown when a function is called with a bogus argument. This generally indicates a program bug. 

            System.ArgumentNullException - Subclass of ArgumentException that's thrown when a function argument is (unexpectedly ) null.

            System.ArgumentOutOfRangeException - Subclass of Argument Exception that's thrown when a (usually numeric) argument is too big or too small. For Example, this is thrown when passing a negative number into a function that accepts only positive values. 

            System.InvalidOperationException - Thrown when the state of an object is unsuitable for a method to successsfully execute, regardless of any particular argument values. Examples include reading an unopened file or getting the next element from an enumerator where the underlying list has been modified partway through the interation. 

            System.NotSupportedException - Thrown to indicate that particular functionality is not supported. A good example is calling the Add method on a collection for which IsReadOnly return true. 

            System.NotImplementedException - Thrown to indicate that a function has not yet been implemented. 

            System.ObjectDisposedException - thrown when the object upon which the function is called has been disposed. 

            NullReferenceException - CLR throws this exception when you attempt to access a member of an object whose value is null. 