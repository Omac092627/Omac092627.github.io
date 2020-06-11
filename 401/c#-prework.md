# C# 101

C# is an elegant type-safe object oriented language that enables developers to build a variety of secure and robust application that run on .Net.

Highly expressive but easy to learn!

OVERVIEW:

Arrays as Objects
Single-Dimensional Arrays
Multidimensional Arrays
Jagged Arrays
Using foreach with Arrays
Passing Arrays as Arguments


1. Arrays as Objects:
    You can store multiple variables of the same type in an array data structure. You declare an array by specifying the type of its elements. If you want the array to store elements of any type, you can specify object as its type. In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from Object.

    Example: type[] arrayName;

    The following creates single-dimensional, multidimensional, and jagged arrays:

    Examples: 
    class TestArraysClass
{
    static void Main()
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


2. Single-Dimensional Arrays:
    You create a single-dimensional array using the new operator specifying the array element type and the number of elements. The following example declares an array of five integers:
        Example: int[] array = new int[5];



3. Multidimensional Arrays:
    Arrays can have more than one dimension. For example, the following declaration creates a two-dimensional array of four rows and two columns.
        Example: int[,] array = new int[4, 2];

    The following declaration creates an array of three dimensions, 4, 2, and 3.
        Example: int[, ,] array1 = new int[4, 2, 3];


4. Jagged Arrays:
    A jagged array is an array whose elements are arrays. The elements of a jagged array can be of different dimensions and sizes. A jagged array is sometimes called an "array of arrays." The following examples show how to declare, initialize, and access jagged arrays.

    The following is a declaration of a single-dimensional array that has three elements, each of which is a single-dimensional array of integers:
        Example: int[][] jaggedArray = new int[3][];

    Before you can use jaggedArray, its elements must be initialized. You can initialize the elements like this:
        Example:  jaggedArray[0] = new int[5]; jaggedArray[1] = new int[4];  jaggedArray[2] = new int[2];


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


