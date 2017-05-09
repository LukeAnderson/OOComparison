# Errors and exception handling
***

#### Java
* Java can throw exceptions. The `Exception classs` contains many of the exceptions that are thrown in Java. Programmers use many of the predefined exceptions in the Java platform additonally custom exceptions can be created by subclassing the exception class.
    * Here is an example of throwing an exception.
    ```Java
    if(val == 0){
       throw new IllegalStateException("val is equal to zero");
    }
    ```
* Thrown exceptions are often done by using the try block and are caught in the following catch block. This is so the problem is addressed and the program continues instead of producing an error that crashes the program.
    ```Java
        int val = 0;
        if(val == 0) {
            try {
               throw new IllegalStateException("bad state val == 0");
            } catch(IllegalStateException e){
                System.out.println("caught illegal state exception");
                val = 1;
            } finally {
                System.out.println("State is set");
            }
        }
    ```
* Also the finally block runs regardless if an exception is thrown or not. The finally block ensures that its section of code will be executed and is useful for cleaning up resources.
#### C#
* C# is similar to Java in that it has try, catch, and finally blocks that are used the same way as Java. There are classes in C# that deal with exceptions most notably System.SystemException, which is the base classs for all predefined system exceptions, and System.ApplicationException, which provides exceptions related to applications.
* Like Java programmers can make thier own exceptions. To do so they need to subclass System.Exception like below.
    ```CSharp 
        public class CustomException : Exception {
            public CustomException (string msg) : base("CustomException: " + msg){
            }
        }
    ```
* Here is an example of a try/catch/finally block similar to the one in Java. 
    ```CSharp
            int val = 0;
            if (val == 0) {
                try {
                    throw new InvalidOperationException("bad state val == 0");
                }
                catch (InvalidOperationException e) {
                    Console.WriteLine("Caught InvalidOperationException");
                    val = 1;
                }
                finally {
                    Console.WriteLine("All set for valid operation");
                }
            }
    ```
* C# differs from java in that the catch block does not require a parameter. If one is not provided then the catch block will catch any exception. 
* C# also does not support checked exceptions like Java does. 