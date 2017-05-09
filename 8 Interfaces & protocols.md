# Interfaces / protocols
What does the language support?
What abilities does it have?
How is it used?
***
#### Java
* Java has interfaces 
* Java's interfaces are comprised up of:
    * abstract methods
        * These make up the bread and butter of java interfaces. When a class implements an interface it must instantiate the abstract methods that the interface has. 
    * constants
        * Classes implementing interfaces gain access to all the constants declared in the interface. This is generally not a good use of interfaces as an children of the class implementing the interface with constants, will also get those constants regardless if it needed them or not.  
    * default methods
        * These allow interfaces to declare a default implementation for one of the necessary methods of the interface if a concrete class does not provide an implementation
    * static methods
        * These are similar to regular static methods called in concrete classes. They were implemented to allow utility methods relavent to the interface to be part of the interface itself. They provide an implementation that cannot be overridden. Concrete classes implementing an interface with a static method have to use the interfaces name to call the static method. For example:
        ```Java 
        public interface StringMethods{
            static boolean isEmpty(String str){
                if(str == null | str.equals("")) return true;
                return false;
            }
        }
        
        public class MyString implements StringMethods {
            String str;
            MyString (String str){
                if(StringMethods.isEmpty(str))
                    this.str = "Interface static method called found str 'empty'";
                else 
                    this.str = str;
            }
        }
        ```

Java's interfaces allow for unrelated objects to communicate with each other. So it is usefull for orgainizing and managing various similar objects.


#### C#
* C# supports interfaces. They are similar to Java's including implementation wise. However, C# does not support anonymously auto-implementated interfaces as Java does. In Java you can do this
```Java
public interface Tester{
    void Test();
}
public void NeedInterface(Tester test){
//code
}
public void Go(){
    NeedInterFace(new Tester){
        @Overide
        public void Test(){
        }
    }
}
```
In C# this can not be done. Instead C# uses delegates which are more powerver than using this anonyomous class approach in Java. C# delegates are examined in the delegate section of this wiki.

* C# Interfaces are used similarly to how interfaces are used in Java. That provide a base code for objects that have similar functions allowing for code designed to work based on the interfaces code to work for all namespaces that implement that interface.


