# Singleton
How is a singleton implemented?
Can it be made thread-safe?
Can the singleton instance be lazily instantiated?
***
#### Java
* In Java a singleton is implemented by the programmer making their own class, with a constructor that can't be called by other classes. Additionally programmers make a static instance of the singleton class in the singleton class and provide a public static method for acessing the only instance.  The following code shows a simplified singleton class. 
```Java
    public class MySingleton{
        private static MySingleton theInstance = null;
        private MySingleton(){}
        public static MySingleton getInstance(){
            if(theInstance == null)
                theInstance = new MySingleton();
            return theInstance;
        }
    }
```
Other classes that would want to use the singleton class would retrieve the instance like so:
```Java
    MySingleton obj = MySingleton.getInstance();
```

* In Java a singleton can be made thread-safe however the above example is not thread-safe. To make a singleton in Java thread-safe you have to change the singleton class. Add a dummy object, use the `synchronized` keyword and change the `getInstance()` such as in the following:
```Java
    public class MySingleton{
        private static MySingleton theInstance = null;
        private static Object mutex= new Object();
        private MySingleton(){}
        public static MySingleton getInstance(){
            if(theInstance == null){
                synchronized(mutex){
                    if(theInstance == null){
                    theInstance = new MySingleton();
                    }
                }
            }
            return theInstance;
        }
    }
```
The above is an example of double-check locking and is  a way developers code for thread safety.

* In Java the singleton instance can be lazily instantiated as seen in the `first` example given. This means that the singleton instance is not created until `getInstance()` is called.  
#### C#
* In C# a singleton is implemented similarly to Java as seen in the following example:
```CSharp
using System;
public class MySingleton{
   private static MySingleton instance;
   private MySingleton() {}
   public static Singleton Instance {
        get {
            if (instance == null) {
               instance = new Singleton();
            }
        return instance;
        }
    }
}
```
* In C# a singleton can be made thread-safe however the example above is not thread-safe. The developer can do double-check locking similar to what is done in the 2nd Java example.
* In C# the singleton instance can be lazily instantiated similarily to when Java implements a thread-safe singleton