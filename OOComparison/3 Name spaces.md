# Name spaces
How are name spaces implemented?
How are name spaces used?
***
#### Java 
* Implementation
    * Packages
* Usage 
    * Separation of groups of variables, methods and classes
    * Prevention of name collisions between classes
    * Example
        ```Java
        
        import java.util.*;
        public class Dog{ ... }
        ```
    Here the Java code defines a namespace called animals. Class Dog has a full qualified name of `animals.Dog` this differentiates this class Dog from any other class Dog. Import is how Java shares definitions. 
***
#### C#

* Implementation 
    * namespaces
* Usage
    * Seperation of groups of variables, methods and classes 
    * Example
        ```CSharp
        using Bio = Earth.biology
        namespace Animals {
            class Dog{ ... }
        }
        ```
    Here the C# code defines a namespace called animals. Class Dog has a full qualified name of `Animals.Dog` this differentiates this class Dog from any other class Dog. `Using` is how C# shares definitions. C# also allows for alliases, in the expample above one can type `Bio` instead of `Earth.biology` to further reference that namespace. 