# Lambda expressions, closures, or functions as types
***
#### Java
* Java supports Lambda expressions. Lambda expressions only work with a functional interface. To declare a functional interface make an interface with only one abstract method. Additionally you can use the `@FunctionalInterface` annotation that will signal the complier that the following interface is to be a functional interface and will produce an error if it is not one.  
```Java
    @FunctionalInterface
    public interface AFunctionalInterface {
        abstract void aMethod();
    }
    public static void main(String[] args) {
        AFunctionalInterface myFunctionalInterface = () -> System.out.println("hello functional world");
        myFunctionalInterface.aMethod();
    }
```
The above code shows how to create a functional interface and make use of its abstract method by defining your own implemtation of it. 
* Java's lambda expressions are closures. So Java supports closures.  Java's lambdas allow for the ablitiy to create functions at runtime, which can then be used by other code.
* Java does support functions as types. Any single method interface is its own funciton type. However, the way to pass functions as parameters and return functions is through passing around instances of functional interfaces.
#### C#
*   Like Java C# has Lambda expressions which are anonynomous funcitions. However in C# these can be used to create delegates. Delegates are similar to functional pointers. Here is an example of delegates:
```CSharp
delegate int Operation(int n);
class testDelegates{
    static int num = 0;
    public static int Add(int operand) {
        num += operand;
        return num;
    }

     public static int Mult(int operand) {
        num *= operand;
        return num;
    }
    static void Main(string[] args) {
         //create delegate instances
        Operation add = new Operation(Add);
        Operation mul = new Operation(Mul);
        
        add(5);
        //value of num is now 5 after Add 0 + 5 
        mul(5);
        //value of num is now 25 after Mul 5 * 5
    }
}
```
* C# also supports closures with delegates. The following example demonstrates this:
```CSharp
delegate void Printer();
static void Main(string[] args) {
  int x = 0;
  Printer ptr = delegate { Console.WriteLine(x); };
  x = 1;
  ptr();
//the output is 1
}
```
* The value of x is obtained by a reference with the delegate ptr. 
The C# complier creates a special class that "x" becomes a field of. Also the anonymous method assigned to ptr becomes an instance of that class. 
* Function types exsist in C# they are called delegates. There are two generic delegate types. Func<..> for methods that return a value and Action <...> for ones that do not.