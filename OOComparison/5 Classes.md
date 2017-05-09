# Classes
Defining
Creating new instances
Constructing/initializing
Destructing/de-initializing
***
#### Java 
* A class is defined in Java as follows: A template from which individual objects are instantiated from. Define your own classes by using the keyword `class` followed by a chosen name for the class. Additionally a class needs a constructor, which is a method named the same as the class. If you do not write a constructor for your class then an empty constructor will be made automatically. Meaning in the example below if there was no constuctor then the compiler would make a default one as `Person(){}` 
    ```Java
    public class Person{
        private String name;
        private int age;
        public Person(String name, int age){
            this.name = name;
            this.age = age;
        }
    }
    ```
* To create a new instance of a class use the keyword `new` and the objects name as well as pass parameters expected from that objects constructor(s). In the following example potus is a new instance of the Person class.
    ```Java
        Person potus = new Person("Donald Trump",70);
    ```
* The examples above provides information on how to construct / intialize a class. You must use the name of the class you want to initialize followed by the name of what you want this instance to be called. Then set that chosen name equal to `new`  one of the classes constructors with appropriate parameters. 
* Java's garbage collection automatically destucts instances of objects sometime after they no longer reachable.
#### C#
* A class in C# is similarly designed as  a class in Java: A class is a blueprint used for instantiating objects. In C# you define your own class by using the keyword `class`.
    ```CSharp
    public class Person {
        private string name;
        private int age;
        public Person(string name, int age){
            this.name = name;
            this.age = age;
        }
    }
    ```
    the above C# code is nearly identical to the Java code for all the same reasons. The only difference is there is `String` in the Java code and `string` in the C# code. You must use the keyword `String` in Java while in C# you can use either `String` or `string`. In C# both `String` and `string` refer to the same class `System.String`. 
* Creating a new instance is the same as Java.
    ```CSharp
        Person potus = new Person("Donald Trump",70);
    ```
* The above C# code sinpits display how to define your own classs and instantiate it using that classes constructor. It is similar to Java. 
* Similar to Java C#'s objects are destroyed by garbage collection. Additionally, C# allows for programmers to implement an optional destructor method 
C# destructors example:
    ```CSharp
        ~Person() {//destructor
        //cleanup 
        }
    ```
    Add the function, which is a destructor above to the C# person class. There can only be one destructor for a class. The destructor will be called when ever an object is about to be finalized by garbage collection.