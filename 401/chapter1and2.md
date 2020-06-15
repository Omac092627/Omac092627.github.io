# Chapter 1

    INTRODUCING C# AND THE .NET FRAMEWORK

        Object Orientation:
            C# is a rich implementation of the object-oriented paradigm, which includes encapsulation, inheritance, and polymorphism. 

            ENCAPSULATION: means creating a boundary around an object, to separate its external (public) behavior from its internal (private) implementation details. The distinctive features of C# from an object-oriented perspective are:

                UNIFIED TYPE SYSTEM:
                    The fundamental building block in C# is an encapsulated unit of data and functions called a type. C# has a unified type system, where all types ultimately share a common base type. This means that all types, whether they represent business objects or are primitive types such as numbers, share the same basic functionality. For example, an instance of any type can be converted to a string by calling its ToString method.

                CLASSES and INTERFACES:
                    In a traditional object-oriented paradigm, the only kind of type is a class. In C#, there are several other kinds of types, one of which is an interface. An interface is like a class, except that it only describes members. The implementation for those members comes from types that implement the interface. Interfaces are particularly useful in scenarios where multiple inheritance is required(unlike languages such as C++ and Eiffel, C# does not support multiple inheritance of classes. )
                
                PROPERTIES, METHODS, AND EVENTS:
                    In the pure object-oriented paradigm, all functions are methods (this is the case in Smalltalk). In C#, methods are only one kind of function member, which also includes properties and events (there are others, too). Properties are function members that encapsulate a piece of an objects' state, such as a button's color or a label's text. Events are function members that simplify acting on objects state changes.

                While C# is primarily an object-oriented language, it also borrows from the functional programmingg paradigm. Specifically: 

                FUNCTIONS CAN BE TREATED AS VALUES:
                    Through the use of delegates C# allows functions to be passed as values to and from other functions.

                C# SUPPORTS PATTERNS FOR PURITY
                    Core to functional programming is avoiding the use of variables whose values change, in favor of declarative patterns. C# has key features to help with those patterns, including the ability to write unnamed functions on the fly that "capture" vairables (lambda expressions), and the ability to perform list or reactive programming via query expressions. C# also makes it easy to define read-only fields and properties for writing immutable (read-only) types. 
--------------------------------------------------------------------------------------------------
        TYPE SAFETY:
            C# is primarily a type-safe language, meaning that instances of types can interact only through protocols they define, thereby ensuring each type's internal consistency. For instance, C# prevents you from interacting with a string type as though it was an integer type.

            More specifically, C# supports static typing, meaning that the language enforces type safety at compile time. 

            Static typing eliminates a large class of errors before a program is even run. It shifts the burden away from runtime unit tests onto the compiler to verify that all the type in a program fit together correctly. Static typing allows tools such as IntelliSense in Visual Studio to hep you write a program, since it knows for a given variable what type it is, and hence what methods you can call on that variable.

            C# is also a strongly typed language because its type rules (whether enforced statically or at runtime) are very strict. For instance, you cannot call a function that's designed to accept an integer with a floating-point number, unless you first explicitly convert the floating-point number to an integer. This helps prevent mistakes. 

            Strong typings also plays a role in enabling C# code to run in a sandbox--an environment where every aspect of security is controlled by the host. In a sandbox, it is important that you cannot arbitrarily corrupt the state of an object by bypassing its type rules. 
--------------------------------------------------------------------------------------------------
        MEMORY MANAGEMENT:
            C# relies on the runtime to perform automatic memory management. The common Language Runtime has a garbage collector that executes as part of your program, reclaiming memory for objects that are no longer referenced. This frees programmers from explicitly deallocating the memory for an object, eliminating the problem of incorrect pointers encountered in lanuages such as C++.

            C# does not eliminate pointers: it merely makes them unnecessary for most programming tasks. For performance-critical hotspots and interoperability, pointers and explicit memory allocation is permitted in blocks that are marked unsafe. 
            
--------------------------------------------------------------------------------------------------
    LANGUAGE BASICS:            
            C# statements are executed sequentially and are terminated by a semicolon (like javascript).

            A method performs an action in a series of statements called a statement-block, a pair of {}.

            Writing higher level functions that call upon lower level functions simplifies a program.

            C# recognizes a method called Main as signaling the default entry point of execution. The Main method may optionally accept an array of strings as a paramter (that will be populated with any arguments passed to the executable.)

            Main is the default entry point of execution. 

            Static means that the method is associated with the class, not a specific instance (object) of that class.

            Void is if it doesn't return any value to its caller

            Example: static int Main (string[] args){...}

            Without string Example: static void Main().

            A class groups function members and data members to form an object-oriented building block. A class is a kind of type.

--------------------------------------------------------------------------------------------------
        COMPILATION:
            The C# compiler compiles source code, specified as a set of files with the .cs extension, into an assembly. 
            
            An assembly is the unit of packaging and deployment in .NET. It can either be an application or a library.

            A normal console or Windows application has a Main method and is an .exe file. 

            A library is a .dll and is equivalent to an .exe without an entry point. Its purpose is to be called upon by an application or by other libraries. The .NET framework is a set of libraries. 

            The name of the C# compiler is csc.exe. You can either use an IDE such as Visual Studio to compile, or call csc manually from the command line. (To do it manually, save the file is BlahBlahBlah.cs, and then go to the command line and invoke csc:     csc BlahBlahBlah.cs). This produces an application named BlahBlahBlah.exe.

            To produce a library(.dll): csc/target:library BlahBlahBlah.cs.

--------------------------------------------------------------------------------------------------
        SYNTAX:
            C# syntax is inspired by C and C++ syntax.

                Example: 
                    using System;
                    
                    class Test
                    {
                        static void Main()
                    {
                        int x = 12 * 30;
                        Console.WriteLine (x);
                        }
                    }

--------------------------------------------------------------------------------------------------
            IDENTIFIERS AND KEYWORDS:
                Identifiers are names that programmers choose for their classes, methods, variables and so on. These are the indentifiers in the example above in order: System, Text, Main, x, Console, WriteLine
                
                An identifier must be a whole word, essentially made up of Unicode characters starting with a letter or underscore. C# identifiers are case-sensitive. By convention, parameeters, local variables, and private fields should be in camel case(e.g., myMethod), and all other identifiers should be in Pascal case (e.g., MyMethod)

                Keywords are names that mean something special to the compiler. These are the keywords in our example above: using, class, static, void, int.

--------------------------------------------------------------------------------------------------
            AVOIDING CONFLICTS:
                If you really want to use an identifier that clashes with a reserved keyword, you do so by qualifying it with the @ prefix:
                    class class {...} //illegal
                    class @class {...}//legal

--------------------------------------------------------------------------------------------------
            CONTEXTUAL KEYWORDS:
                Some keywords are contextual, meaning they can also be used as identifiers: add , ascending, async, await...

--------------------------------------------------------------------------------------------------
            LITERALS, PUNCTUATORS, AND OPERATORS:
                Literals are primitive pieces of data lexically embedded into the program. The literals used in the example were 12 and 30. It's the information inputted by the programmer. The information used for the method.

                Punctuators help demarcate(set the boundaries) the structure of the program: {}, ";"... The braces group multiple statements into a statement block. The semicolon terminates a statement. You can have multi-line statements. 

                Operators: ., (), *, =. They transform and combine expressions.

                A period denotes a member or a decimal point with numeric literals.

                Parantheses are used when declaring or calling a method; empty parentheses are used when the method accepts no arguments.

                An equal sign performs an assignment, the double equal sign performs equality comparison.

                Comments are the same as javascript. 
                
--------------------------------------------------------------------------------------------------
            TYPE BASICS:
                A type defines the blueprint for a value. In our example we used two literals of type int with values 12 and 30. We also declared a variable of type int whose name was x. 

                A variable denotes a storeage location that can contain different values over time. In contrast, a constant always represeents the same value.
                    Example: const int y = 360
                
                All values in C# are instances oof a type. The meaningg of a value, and the set of possible values a variable can have, is determined by its type.

--------------------------------------------------------------------------------------------------
            PREDEFINED TYPE EXAMPLES:
                Predefined types are types that are specially supported by the compiler. The int type is a predefined type for representing the set of integers that fit into 32 bits of memory, and is the default type for numeric literals within this range. We can perform functions such as arithmetic with instances of the int type as follows: int x = 12 * 30;

                Another predefined C# type is string. The string type represents a sequence of characters, such as ".NET" or "https://orielley.com." we can work with strings by calling functions on them as follows:
                    string message = "Hello World";
                    string upperMessage = message.ToUpper();
                    Console.WriteLine (upperMessage) // HELLO WORLD

                    int x = 2015;
                    message = message + x.ToString();
                    Console.WriteLine (message); // Hello world2015

                The predefined bool type has exactly two possible values: true and false. The bool type is commonly used to conditionally branch execution flow based with an if statement:
                    bool simpleVar = false;
                    if (simpleVar)
                        Console.WriteLine("This will not print");

                    int x = 5000;
                    bool lessThanAMile = x < 5280;
                    if (lessThanAMile)
                        Console.WriteLine ("This will print");

--------------------------------------------------------------------------------------------------
            CUSTOM TYPE EXAMPLES:
                Just as we can build complex functions from simple functions, we can build complex types from primitive types. In this example, we will define a custom type named UnitConverter -- a class that serves as a blueprint for unit conversions.

--------------------------------------------------------------------------------------------------
            MEMBERS OF A TYPE:
                A type contains data members and function membes. The data member ofo UnitConverter is the field called ratio. The function members of UnitConverter 
                are the Convert method and the UnitConverter's constructor.

--------------------------------------------------------------------------------------------------
            INSTANCE VERSUS STATIC MEMBERS:
                The data members and function members that operate on the instance of the type are called instance members. The UnitConverter's Convert method and the int's ToString method are examples of instance members.

                Data members and function members that don't operate on the instance of the type, but rather on the type itself, must be marked as static. The Test.Main and Console.WriteLine methods are static methods. The Console class is actualy a static class, which means all its members are static. You never actually create instances of a Console -- one console is shared across the whole application.
                    Example: 
                        public class Panda
                        {
                            public string Name; //Instance field
                            public static int Population; //Static field

                            public Panda (string n) //constructor
                            {
                                Name = n; //assign the instance field
                                Population = Population + 1; //incrememnt the static Population field
                            }
                        }

                        using System;

                        class Test
                        {
                            static void Main()
                            {
                                Panda p1 = new Panda ("Pan Dee");
                                Panda p2 = new Panda ("Pan Dah");

                                Console.WriteLine (p1.Name); //Pan Dee
                                Console.WriteLine (p2.Name); //Pan Dah

                                Console.WriteLine (Panda.Population); //2
                            }
                        }

--------------------------------------------------------------------------------------------------
           
            THE PUBLIC KEYWORD:
                The public keyword exposes members to other classes. In this example, if the Name field in Panda was not marked as public, it would be private and the Test class could not access it. Making a member public is how a type communicates: "Here is what I want other types to see--everything else is my own private implementation details." In object-oriented terms, we say that the public members encapsulate the private members of the class. 

--------------------------------------------------------------------------------------------------
         
            C# can convert between instances of compatatible types. A conversion always creates a new value from an existing one. Conversions can be either implicit or explicit: 

            Implicit conversions are allowed when both of the following are true:
                The compiler can guarantee they will always succeed.
                No information is lost in conversion.

            Explicit conversions are required when one of the following is true:
                The compiler cannot guarantee they will always succeed. 
                Information may be lost during conversion.

--------------------------------------------------------------------------------------------------
            VALUE TYPES VERSUS REFERENCE TYPES:
                All C# types fall into the following categories:
                    Value types
                    Reference types
                    Generic type parameters
                    Pointer types

                Value type: content of a value type variable or constant is simply a value. For example, the content of the built-in value type, int, is 32 bits of data.

                You can define a custom value type with the struct keyword:
                    public struct Point {public int X; public int Y;}
                    
                    or

                    public struct Point {public int X, Y;}

                Value type always copies the instance.

          ---------------------------------------------------------

                Reference type: has two parts: an object and the reference to that object. 
                - The content of a reference-type variable or constant is a reference to an object that contains the value. 
                
                Here is the Point type from our previous example rewritten as a class, rather than a struct:
                    public class Point {public int X, Y;}

                Assigning a reference-type variable copies the reference, not the object instance. This allows multiple variables to refer to the same object--something not ordinarily possible with value types. This allows multiple variables to refer to the same object--something not ordinarily possible with value types. 

                Null can also be assigned but don't do value type reference with Null. 

--------------------------------------------------------------------------------------------------

            STORAGE OVERHEAD:
                Value-type instances occupy precisely the memory required to store their fields. In this example, Point takes eight bytes of memory. 

                Reference types require separate allocations of memory for the reference and object. The object consumes as many bytes as its fields, plus additional administrative overhead. 

--------------------------------------------------------------------------------------------------

            PREDEFINED TYPE TAXONOMY:
                The predefined types in C# are:
                    Value types:
                        Numeric
                            - signed integer (sbyte,short,int,long)
                            - unsigned integer(byte, ushort, uint, ulong)
                            - real number (float, double, decimal)

                        Logical(bool)
                        Character(char)

                    Reference types:
                        String(string)
                        Object(object)

                The set of predefined value types exluding decimal are known as primitive types in the CLR(common language runtime). Primitive types are so called because they are supported directly via instructions in compiled code, and this usually translates to direct support on the underlying processor. 

--------------------------------------------------------------------------------------------------

            NUMERIC TYPES:
                    C# has the predefined numeric types:

                    C#type        System type     Suffix    size    Range
                    
                    Integral-signed

                    sbyte          SByte                     8bits
                    short          Int16                     16bits
                    int            Int32                     32bits
                    long           Int64                     64bits

                    Integral-unsigned

                    Real

                Of the integral types, int and long are first-class citizens and are favored by both C# and runtime. The other integral types are typically used for interoperability or when space efficiency is paramount.

                Of the real number types, float and double are called floating-point types and are typically used for scientific and graphical caluclations. The decimal type is typically used for financial calculations, where base-10-accurate arithmetic and high precision are required.

--------------------------------------------------------------------------------------------------
            
            NUMERIC LITERALS:
                Integral-type literals can use decimal or hexadecimal notation; hexadecimal is denoted with the 0px prefix. For Example: int x = 127; / long y = ox7f;

                From C# 7.0, you can insert an underscoore anywehre inside a numeric literal to make it more readable:
                    int million = 1_000_000;

--------------------------------------------------------------------------------------------------

            NUMERIC LITERAL TYPE INFERENCE:
                By default the compiler infers a numeric literal to be either double or an integral type.
                    - if the literal contains a decimal point or the exponential symbol (E), it is a double.
                    - Otherwise, the literal's type is the first type in the list that can fit the literal's value: int, uint, long, and ulong.

--------------------------------------------------------------------------------------------------

            NUMERIC SUFFIXES:   
                Numeric suffixes specifically define tye type of a literal. Suffixes can be either lower or uppercase, and are as follows:
                    F or f: float; ex: float f = 1.0F;
                    D or d: double; ex: double d = 1D;
                    M or m: decimal; ex: decimal d = 1.0M;
                    U or u: uint; ex: uint i = 1U; 
                    L or l: long; ex: long i = 1L;
                    UL or ul: ulong i = 1UL;

                F and M are the most important, always use them when specifying decimals, decimal literals, and floats.
--------------------------------------------------------------------------------------------------                

            NUMERIC CONVERSIONS:    
                Converting between integral types:
                    Integral type conversions are implicit when the destination type can represent every possible value of the source type. Otherwise an explicit conversion is required. 
                        Example:
                            int x = 12345; //int is a 32-bit integer
                            long y = x; //Implicit conversion to 64-bit integral type
                            short z = (short)x;//Explicit conversion to 16-bit integral type

                Converting between floating-point types:
                    A float can be implicitly converted to a double, since a double can represent every possible value of a float. The reverse conversion must be explicit.

                Converting between floating-point and integral types:
                    All integral types may be implicitly converted to all floating-point types: 
                        int i = 1;
                        float f = i;
                    The reverse conversion must be explicit:
                        int i2 = (int)f;

                Decimal Conversions:
                    All integral types can be implicitly converted to the deecimal type, since a decimal can represent every possible C# integral-type value. All other numeric conversions to and from a decimal type must be explicit.

--------------------------------------------------------------------------------------------------

                Arithmetic Operators:
                    The arithmetic operators are:
                        + = addition
                        - = subtraction
                        * = mulitiply
                        / = division
                        % = remainder after division

--------------------------------------------------------------------------------------------------
                Increment and Decrement operators:
                    (++, --) add 1 or minus 1 and can precede or go after the variable.
--------------------------------------------------------------------------------------------------

                Specialized Operations on Integral Types
                (The integral types are int, uint, long, ulong, short, ushort, byte, and sbyte)

                Division: 
                    Division operations on integral types always truncate remainders (round toward zero). Dividing by a variable whose value is zero generates a runtime error.
                        Example: 
                            int a = 2/3 //0

                            int b = 0;
                            int c = 5/b; // throws DivideByZeroException
                        Dividing by the literal or constant 0 generates a compile-time error. 

--------------------------------------------------------------------------------------------------

                OverFlow:
                    At runtime, arithmetic operations on integral types can overflow. By default, this happens silently--no exception is thrown, and the result exhibits "wraparound" behavior, as though the computations was done on a larger integer type and the extra significant bits discarded. For example, Decrementing the minimum possible int value results in the maximum possible int value:
                        int a = int.MinValue;
                        a--;
                        Console.WriteLine (a == int.MaxValue); //True

                OverFlow check operators: 
                    The checked operator teells the runtime to generate an OverflowException rather than overflowing silently when an integral-type expression or statement exceeds the arithmetic limits of that type. The checked operator affects expressions with the ++, --, +, - (binary and unary), *, /, and explicit conversion operators between integral types. 
                    (It has no effect ono the double and float types)

                    Checked can be used around either an expression or a statement block.
                        int a = 100000;
                        int b = 100000;

                        int c = checked (a*b); //checks just the expression

                        checked
                        {
                            ...                      //checks all expressions
                            c=a*b;                   //in a statement block
                            ...
                        }

                    You can make arithmetic overflow checking the default for all expressions in a program by compiling with the /checked+ command-line switch (in Visual Studio, go to Advanced Build Settings). If you then need to disable overflow checking just for specific expressions or statements, you can do so with the unchecked operator.
                            int x = int.MaxValue;
                            int y = unchecked (x + 1);
                            unchecked { int z = x + 1; }

                
                OverFlow checking for constant expressions:
                    Regardless of the /checked compiler switch, expressions evaluated at comopile time are always overflo-checked -- unless you apply the unchecked operator:
                        int x = int.MaxValue + 1; // Compile-time error
                        int y = unchecked (int.MaxValue + 1) // no errors

--------------------------------------------------------------------------------------------------

                Bitwise operators:
                    C# supports the following bitwise operators: 

                    ~ = compliment
                    & = And
                    | = Or
                    ^ = Exclusive Or
                    << = Shift left
                    >> = Shift Right
--------------------------------------------------------------------------------------------------

                8 and 16 bit Integral Types: 
                    the 8- and 16-bit integral types are byte, sbyte, short, and ushort. These types lack their own arithmetic operators, so C# implicitly converts them to larger types as required. This can cause a compile-time error when trying to assign the result back to a small integral type:
                        short x = 1, y = 1;
                        short z = x + y; //compile-time error

                    In this case, x and y are implicitly converted to int so that addition can be performed. This means the result is also an int, which cannot be implicitly cast back to a short (because it could cause loss of data). To make this compile, we must add an explicit cast:
                        short z = (short)(x + y); //ok

--------------------------------------------------------------------------------------------------

                Special Float and Double Values
                    Unlike integral types, floating-point types have values that certain operations treat specially. These special values are NaN (not a number), +∞, -∞, and -0. The float and double classes have constants for NaN, +∞, and -∞, as well as other values (MaxValue, MinValue, and Epsilon).

                Special Value, Double Constant, Float Constant:
                    NaN, double.NaN, float.NaN
                    +∞, double.PositiveInfinity, float.PositiveInfinity
                    -∞, double.NegativeInfinity, float.NegativeInfinity
                    -0, -0.0, -0.0f

                Dividing a nonzero number by zero results in an infinite value. 
                    Console.WriteLine (1.0/0.0) // Infinity
                    Console.WriteLine(-1.0/0.0) //-Infinity
                    Console.WriteLine (1.0/-0.0) //-Infinity
                    Console.WriteLine (-1.0/-0.0) //Infinity

                Dividing zero by zero, or subtracting infinity from infinity, results in a NaN.
                    Console.WriteLine (0.0/0.0) //NaN
                    Console.WriteLine (1.0/0.0) - (1.0/0.0) //Nan

                When using ==, a NaN value is never equal to another value, even another NaN value.

                    Console.WriteLine (0.0/0.0 == double.NaN) //false

                To test whether a value is NaN, you must use the float.IsNaN or double.IsNan method:
                    console.WriteLine (double.IsNaN (0.0/0.0)) //true

                When using object.Equals, however, two NaN values are equal:
                    Console.WriteLine (object.Equals (o.o/o.o, double.NaN)) // true
                
--------------------------------------------------------------------------------------------------

            Double Versus decimal:
                double is useful for scientific computations  (such as computing spatial coordinates) decimal is useful for financial computations and values that are man-made rather than the result of real-world measurements.

--------------------------------------------------------------------------------------------------

            Real Number Rounding Errors
                float and double internally represent numbers in base 2. For this reason, only numbers expressible in base 2 are represented precisely. Practically, this means most literals with a fractional component(which are in base 10) will not be represented precisely. 
                    float tenth = 0.1f;
                    float one = 1f; 
                    Console.WriteLine( one - tenth * 10f) // -1.490116E-08

                This is why float and double are bad for financial calculations. In contrast decimal works in base 10 and so can precisely represent numbers expressible in decimal can precisely represent numbers as 0.1. However, neither double nor decimal can precisely represent a fractional number whose base 10 representation is recurring.

--------------------------------------------------------------------------------------------------


            Boolean Type and Operators:
                C$'s bool type (aliasing the System.Boolean type) is a logical value that can be assigned the literal true or false. 

                Although a Boolean value requires only one bit of storage, the runtime will use one byte of memory, since this is the minimum chunk that the runtime and processor can efficiently work with. to avoid space inefficiency in the case of arrays, the Frameworkd provides a BitArray class in the System.Collections namespace that is designed to use just one bit per Boolean value. 


                Bool Conversions:
                    No casting conversions can be made from the bool type to numeric types or vice versa. 


--------------------------------------------------------------------------------------------------

                Equality and Comparison Operators:
                    == and != test for eqality and inequality of any type, but always return a bool value. Value types typically have a very simple notion of equality:
                        int x = 1; 
                        int y = 2;
                        int z = 1;
                        Console.WriteLine (x == y) // False
                        Console.WriteLine (x == z) // true

--------------------------------------------------------------------------------------------------

            Conditional Operators:
                The && and || operators test for and and or conditions. 

            Conditional operator (ternary operator)
                The conditional operator (more commonly called the ternary operator, as it's the only operator that takes three operands) has the form q ? a : b, where if condition q is true, a is evaluated, else b is evaluated. 

                    static int Max (int a, int b)
                    {
                        return (a > b) ? a :b
                    }

--------------------------------------------------------------------------------------------------

            Strings and Characters:
                C#'s char type (aliasing the System.Char type) represents a Unicode character and occupies 2 bytes. A char literal is specified inside single quotes:

                    char c = 'A'; // Simple character

                Escape sequences express characters that cannot be expressed or interpreted literally. An escape sequence is a backslash followed by a character with a special meaning.
                    char newLine = '\n'
                    char backSlash = '\\';

                
                Escape sequence chart:

                \' = Single quote
                \" = Double quote
                \\ = Backslash
                \0 = Null
                \a = Alert
                \b = Backspace
                \f = Form Feed
                \n = New line
                \r = Carriage return 
                \t = Horizontal tab
                \v = Vertical tab

                The \u (or \x) escape sequence lets you specify any Unicode character via its four-digit hexadecimal code

                    char copyrightSymbol = '\u00A9';
                    char omegaSymbol = '\u03A9';
                    char newLine = '\u000A';
--------------------------------------------------------------------------------------------------
        
        String Type:
            C#'s string type (aliasing the System.String type, covered in depth in Chapter 6) represents an immutable sequence of Unicode characters. A string literal is specified inside double quotes:
                string a = "Heat";
                    String is a reference typee, rather than a value type. It's equality operators, however, follow value-type semantics:
                        string a = "test";
                        string b = "test";
                        Console.Write (a == b); //true
                The escape sequences that are validi for char literals also work inside strings:
                    string a = "Here's a tab:\t";

                The cost oof this is that whenever you need a literal backslash, you must write it twice:
                    string a1 = "\\\\server\\fileshare\\heloworld.cs";
                To avoid this problem, C# allows verbatim string literals. A verbatim string literal is prefixed with @ and does not support escape sequences. The following verbatin string is identical to the preceding one:
                    string a2 = @"\\server\fileshare\helloworld.cs";
                It can also span multiple lines.

            String concatenation:
                The + operator concatenates two strings:
                    string s = "a" + 5; //a5

            String interpolation:
                A string preceded with the $ character is called an interpolated string. Interpolated strings can include expressions inside braces:
                    int x = 4; 
                    Console.Write ($"A square has {x} sides"); // Prints: A square has 4 sides
            Any valid C# expression of any type can appear within the braces, and C# will convert the expression to a string by calling its ToString method or equivalent. You can change the formatting by appending the expression with a colon and a format string (format strings are described in "String.Format and composite format strings" on page 234):
                string s = $"255 in hex is {byte.MaxValue:x2}"; // x2 = 2-digit hexadecimal//Evaluates to "255 in hex is FF"

            Interpolated strings must complete on a single line, unless you also specify the verbatim string operator (@):
                int x = 2;
                string s = $@"this spans {
                x} lines";

            Strings does not support < and > operators for comparisons. you must use string's CompareTo method, described in chapter 6. 


--------------------------------------------------------------------------------------------------


            1. Arrays as Objects:
                You can store multiple variables of the same type in an array data structure. You declare an array by specifying the type of its elements. If you want the array to store elements of any type, you can specify object as its type. In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from Object.

                Example: 
                //type[] arrayName;

                The following creates single-dimensional, multidimensional, and jagged arrays:

                Examples: 
                    //    class TestArraysClass
                    {
                    //    static void Main()
                        {
                    // Declare a single-dimensional array of 5 integers.
                    int[] array1 = new int[5];

                    // Declare and set array element values.
                    int[] array2 = new int[] { 1, 3, 5, 7, 9 };

                    // Alternative syntax.
                    int[] array3 = { 1, 2, 3, 4, 5, 6 };

                    // Declare a two dimensional array.
                    int[,] multiDimensionalArray1 = new int[2, 3];

                    // Declare and set array element values.
                    int[,] multiDimensionalArray2 = { { 1, 2, 3 }, { 4, 5, 6 } };

                    // Declare a jagged array.
                    int[][] jaggedArray = new int[6][];

                    // Set the values of the first array in the jagged array structure.
                    jaggedArray[0] = new int[4] { 1, 2, 3, 4 };
                }
            }


                    An array has the following properties:

                    An array can be Single-Dimensional, Multidimensional or Jagged.
                    The number of dimensions and the length of each dimension are established when the array instance is created. These values can't be changed during the lifetime of the instance.
                    The default values of numeric array elements are set to zero, and reference elements are set to null.
                    A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to null.
                    Arrays are zero indexed: an array with n elements is indexed from 0 to n-1.
                    Array elements can be of any type, including an array type.
                    Array types are reference types derived from the abstract base type Array. Since this type implements IEnumerable and IEnumerable<T>, you can use foreach iteration on all arrays in C#.
                        The following keywords are used to declare reference types:

                                class

                                interface

                                delegate

                                C# also provides the following built-in reference types:

                                dynamic

                                object

                                string
--------------------------------------------------------------------------------------------------


                2. Single-Dimensional Arrays:
                You create a single-dimensional array using the new operator specifying the array element type and the number of elements. The following example declares an array of five integers:
                    Example: 
                    //int[] array = new int[5];

--------------------------------------------------------------------------------------------------


                3. Multidimensional Arrays:
                    Arrays can have more than one dimension. For example, the following declaration creates a two-dimensional array of four rows and two columns.
                        Example: 
                        //int[,] array = new int[4, 2];

                    The following declaration creates an array of three dimensions, 4, 2, and 3.
                        Example: 
                        //int[, ,] array1 = new int[4, 2, 3];
--------------------------------------------------------------------------------------------------


                4. Jagged Arrays:
                    A jagged array is an array whose elements are arrays. The elements of a jagged array can be of different dimensions and sizes. A jagged array is sometimes called an "array of arrays." The following examples show how to declare, initialize, and access jagged arrays.

                    The following is a declaration of a single-dimensional array that has three elements, each of which is a single-dimensional array of integers:
                        Example: int[][] jaggedArray = new int[3][];

                    Before you can use jaggedArray, its elements must be initialized. You can initialize the elements like this:
                        Example:  jaggedArray[0] = new int[5]; jaggedArray[1] = new int[4];  jaggedArray[2] = new int[2];

--------------------------------------------------------------------------------------------------

                5. Using for each with arrays:
                    The foreach statement provides a simple, clean way to iterate through the elements of an array.

                    For single-dimensional arrays, the foreach statement processes elements in increasing index order, starting with index 0 and ending with index Length - 1:
                        Example: int[] numbers = { 4, 5, 6, 1, 2, 3, -2, -1, 0 };
                                foreach (int i in numbers)
                                {
                                    System.Console.Write("{0} ", i);
                                }
                                // Output: 4 5 6 1 2 3 -2 -1 0

                    For multi-dimensional arrays, elements are traversed such that the indices of the rightmost dimension are increased first, then the next left dimension, and so on to the left:
                        Example: int[,] numbers2D = new int[3, 2] { { 9, 99 }, { 3, 33 }, { 5, 55 } };
                        // Or use the short form:
                        // int[,] numbers2D = { { 9, 99 }, { 3, 33 }, { 5, 55 } };

                        foreach (int i in numbers2D)
                        {
                            System.Console.Write("{0} ", i);
                        }
                        // Output: 9 99 3 33 5 55

                        However, with multidimensional arrays, using a nested for loop gives you more control over the order in which to process the array elements.

--------------------------------------------------------------------------------------------------

                6. Passing Arrays as Arguments:
                    Arrays can be passed as arguments to method parameters. Because arrays are reference types, the method can change the value of the elements.


                    You can pass an initialized single-dimensional array to a method. For example, the following statement sends an array to a print method.
                        Example: int[] theArray = { 1, 3, 5, 7, 9 };
                                    PrintArray(theArray);

                    The following code shows a partial implementation of the print method.
                        Example: void PrintArray(int[] arr)
                                {
                                    // Method code.
                                }

                    You can initialize and pass a new array in one step, as is shown in the following example.
                        Example: PrintArray(new int[] { 1, 3, 5, 7, 9 });

                    You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.
                        Example: int[,] theArray = { { 1, 2 }, { 2, 3 }, { 3, 4 } };
                Print2DArray(theArray);

--------------------------------------------------------------------------------------------------

                7. Rectangular arrays: 
                        They are declared using commas to separate each dimension. The following declares a rectangular two-dimensional array, where the dimensions are 3 by 3:
                            int[,] matrix = new int[3,3]
                        
                        The GetLength method of an array returns the length for a given dimension.
--------------------------------------------------------------------------------------------------
                
                Variables and parameters:
                    A variable represents a storage location that has a modifiable value. 

                    The Stack and the Heap are where variables and constants reside. 

                The Stack: 
                    is a block of memory for storing local variables and paramters. The stack logically grows and shrinks as a function is entered and exited. 
                The Heap:
                    The heap is a block of memory in which objects reside. Whenever a new object is created, it is allocated on the heap, and a reference to that object is returned. 

--------------------------------------------------------------------------------------------------

                Definite Assignment:
                    C# enforces a definite assignment policy. In practice, this means that outside of an unsafe context, it's impossible to access unintialized memory. Definite Assignment has three implications:
                        Local variables must be assigned a value before they can be read. 
                        Function arguments must be supplied when a method is called.
                        All other variables are automatically intialized by the runtime.(arrays)
--------------------------------------------------------------------------------------------------

                Default values:
                    All type instances have a default value. 
                        Predefined Types:
                            All reference types = null
                            All numeric and enum types = 0
                            char type = '\0'
                            bool type = false

--------------------------------------------------------------------------------------------------

                Parameters: 
                    A method has a sequence of paramters. Paramters define the set of arguments that must be provided for that method.

                    You can control how parameters are passed with ref and out modifiers:
                        ref = reference going ini
                        out = reference going out

--------------------------------------------------------------------------------------------------

                Passing Arguments by Value:
                    By default, arguments in C# are passed by value, which is by far the most common vase. This means a copy of the value is created when passed to the method.
--------------------------------------------------------------------------------------------------

                The ref modifier:
                    To pass by refernce, C# provides the ref parameter modifier:
                        class Test
                        {
                            static void Foo (ref int p)
                            {
                                p = p + 1; 
                                Console.WriteLine(p);
                            }
                            static void Main()
                            {
                                int x = 8;
                                Foo (ref x); // ask foo to deal directly with x
                                Console.WriteLine(x); //x is now 9
                            }
                        }
                    Now assignming p a new value changes the contents of x. Notice how the ref modifier is required both when writing and when calling the method.

--------------------------------------------------------------------------------------------------

                The out modifier:
                    An out argument is like a ref argument, except it:
                        Need not be assigned before going into the function.
                        Must be assined before it comes out of the function. 
                    the out modifier is most commonly used to get multiple return values back from a method:
                        class Test
                        {
                            static voiid Split(string namee, out string firstNames, out string lastName)
                            {
                                int i = name.LastIndexOf('');
                                firstNames = name.Substring (0, i);
                                lastName = name.Substring (i + 1);
                            }

                            static void Main()
                            {
                                string a, b;
                                Split ("Stevie Ray Vaughan", out a, out b);
                                Console.WriteLine (a); // Stevie Ray
                                Console.WriteLine(b); //Vaughhan
                            }
                        }
                
                Out variables and discards:
                    From C# 7, you can declare variables on the fly when calling methods with out parameters:
                        static void Main()
                        {
                            Split("Stevie Ray Vaughan", out string a, out string b);
                            Console.WriteLine(a); //Stevie Ray
                            Console.WriteLine(b); //Vaughan
                        }

--------------------------------------------------------------------------------------------------

                Implications of Passing by reference:
                    When you pass an argument by reference, you alias the storage location of an existing variable rather than create a new storage location. 
                        x and y can both have the same instance using the same variable.

--------------------------------------------------------------------------------------------------

                Params Modifier:
                    The params parameter modifier may be specified on the last parameter of a method so that the method accepts any number of arguments of a particular type. The parameter type must be declared as an array.
                            class Test 
                            {
                                static int Sum (params int[] ints)
                                {
                                    int sum = 0;
                                    for (int i = 0; i < ints.Length; i++)
                                        sum += ints[i];
                                    return sum
                                }
                                static void Main()
                                {
                                    int total = Sum (1, 2, 3, 4);
                                    Console.WriteLine (total);
                                }
                            }
--------------------------------------------------------------------------------------------------

                Optional Parameters:
                    From C#, methods, constructors, and indexers (Chapter 3) can declare optional parameters. A parameter is optional if it specifies a default value in its declaration:
                        void Foo (int x = 23) {Console.WriteLine (x); }
                    
                    Optional parameters may be omitted when calling the method:
                        Foo(); //23

                    The default argument 23 is actually passed to th optional parameter x -- the compiler bakes the value 23 into the compiled code at the calling side. The preceding call to Foo is sematically identical to:
                        Foo(23);
                    
                    Because the compiler simply subsitutes the default value of an optional parameter wherever it is used.

                    The default value of an optional parameter must be specified by a constant expression, or a parameterless constructor of a value type. Optional parameters cannot be marked with ref or out. 

                    Mandatory parameters must occur before optional parameters in both the method declaration and the method call. In the following example

--------------------------------------------------------------------------------------------------

                Named arguments:
                    Rather than identifying an argument by position, you can identify an argument by name.
                        (int x, int y) / Foo (x:1, y:2) //named = a colon :
                    
                    You can mix named and positional arguments. Positional must come befre named:
                        Foo (1, y:2) //this is correct
                        Foo(y:2, 1) // this gives compile time error

                    Named arguments are particularly useful in conjuction with optional parameters:
                        void Bar (int a = 0, int b = 0, int c = 0, int d = 0) {...}

--------------------------------------------------------------------------------------------------

                Ref Locals:
                    C# 7 adds an esoteric feature, whereby you can define a local variable that references an element in an array or field in an object:
                        int[] numbers = {0, 1, 2, 3, 4};
                        ref int numRef = ref numbers [2];
                    In this example, numRef is a reference to the numbers[2]. When we modify numRef, we modify the array element:
                        numRef *= 10;
                        Console.WriteLine(numRef);
                        Console.WriteLine (numbers [2])

                    The target for a ref local must be an array element, field, or local variable; it cannot be a property(chapter3). Ref locals are intended for specialized micro-optimization scenarios, and are typically used in conjuction with ref returns. 
--------------------------------------------------------------------------------------------------

                Ref returns: 
                    You can return a ref local from a method. This is called a ref return:
                        static string X = "Old Value";
                        static ref string GetX() => ref X; // this method returns a ref
                        static void Main()
                        {
                            ref string xRef = ref GetX(); // Assign result to a ref local
                            xRef = "New Value" 
                            Console.WriteLine(X); // New Value 
                        }

--------------------------------------------------------------------------------------------------

                Var -- Implicitly Typed Local Variables:
                    It is often the case that you declare and initialize a variable in one step. If the complier is able to infer the type from the initizlization expression you can use the keyword var in place of type declaration:
                        var x = "hello";
                        var y = new System.Text.StringBuilder();
                        var z = (float)Math.PI
--------------------------------------------------------------------------------------------------

                Expressions and Operator:
                    An expression essentially denotes a value. The simplest kinds of expressions are contants and variables. Expressions can be transformed and combined using operators.

                Primary Expressions:
                    Primary expressions include expressions composed of operators that are intrinsic to the basic plumbing of the language:
                        Math.Log(1)
                
                Void Expressions:
                    A void expression is an expression that has no value:
                        Console.WriteLine (1)

                    A void expression, since it has no value, cannot be used as an operand to build more complex expressions:
                        1 + Console.WriteLine (1) // compile-time error

                Assignment Expressions:
                    An assignment expression uses the = operator to assign the result of another expression to a variable:
                        x = x * 5
                
                Operator Precedence Associativity:
                    When an expression contains multiple operators, precedence and assicativity determine the order of their evaluation. Operators with higher precedence execute before operators of lower precedence:
                        1 + 2 * 3;

                        1 + (2 * 3) // multiplication is higher precedence than addition. 
                
                Left Associative operators:
                    Binary operators are left associative. They are evaluated from left to right.

                Right associative operators:
                    The assignment operators, lambda, null coalescing, and conditional operators are right-associative, they're evaluated from right to left. 

--------------------------------------------------------------------------------------------------

                Null Operators:
                    C# provides two operators to make it easier to work with nulls: the null coalescing operator and the null-conditional operator. 


                Null Coalescing Operator:
                    The ?? operator is the null coalescing operator. It says "If the operand to the left is non-null, give it to me, otherwise, give me a default value:
                        string s1 = null;
                        string s2 = s1 ?? "nothing" //s2 evaluates to "nothing"

                Null-conditional Operator
                    The ?. operator is the null-conditional or "Elvis" operator (after elvis emoticon), was introduced in C# 6. It allows you to call methods and access members just like the standard dot operator, except that if the operand on the left side is null, the espression evaluates to null instead of throwing a NullReferenceException:
                        System. Text. StringBuilder sb = null;
                        string s = sb?.ToString(); //No error; s instead evaluates to null
                        basically its this: string s = (sb == null ? null: sb.ToString());

--------------------------------------------------------------------------------------------------

                Statements:
                    Functions comprise statements that execute sequentially in the textual order in which they appear. A statement block is a series of statements appearing between braces ({})

                Declaration Statements: 
                    A declaration statement declares a new variable, optionally intializing the variable with an expression. A declaration statement ends in a semicolon. You may declare multiple variables of the same type in a somma-separated list:
                        string someWord = "rosebud";
                        int someNumber = 42;
                        bool rich = true, famous = false;

                Local Variables:
                    The scope of a local variable or local constant extends through the current block. You cannot declare another local variable with the same name in the current block or in any nested blocks.
                
                Expression statements:
                    Expression statements are expressions that are also valid statements:
                        x =  1 + 2;
                        x++
                        new StringBuilder();