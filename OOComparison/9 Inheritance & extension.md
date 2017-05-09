# Inheritance / extension
***
#### Java
*   Classes can extend only one other class. The class that extends another is said to be the child of the other and thus the other class is said to be the parent. The child class can call methods from the parents so long as they are not private. If the child class has a method with the same signiture as the parent classs calling that method in the child class would call the child class's implementation. In order to call the parent class's implementation use the keyword `super` like in the following example.
    ```Java
        public class TheParent{
            public void print{
                System.out.println("Called print in TheParent class");
            }
        }
        
        public class TheChild extends TheParent{
            public void print{
                System.out.println("Called print in TheChild class");
            }
            
            public void printParentThenChild(){
                super.print();
                print();
            }
        }
    ```
*   Why extend only one class? Java does not allow multiple inheirtance with classes in part to avoid the diamond problem and promote better coding practices. This problem is when one class has two parents that each have their own implementation of a method with the same signature. So, when the child class calls for this method without its own definition for the method, the compiler cannot determine which parent's method to use for this. However, classes can implement multiple interfaces. As discussed in interfaces and protocols Java interfaces can have concrete default methods. This can cause the diamond problem to exist. The compiler will produce an error if such a situation were to happen and the implementing class would have to write its own definition to replace the default methods of the interfaces causing the diamond problem.     
*   Here is an example on  how to extend a class and implement multiple interfaces.
    ```Java
    public class ExampleClass extends ParentClass implements MyInterface1, MyInterface2{
        requiredInterface1Method(){
        }
        requiredInterface2Method(){
        }
        //... other concrete methods 
    }
    ```
#### C#
* Similar to Java classes can only inheirt one class. However unlike Java, C# clases are not virtual by default. See the following example:
```CSharp
class A {   
}
class B : A {
    public void Msg(){
        Console.WriteLine("B");
    }
}
class C : B {
    public void Msg(){
        Console.WriteLine("C");
    }
}
```
```CSharp
B b = new C()
b.Msg();
//output is B
```
While the output in Java would be C. To make it be C in C# you have to declare the function you want to be overidden as `virtual` and you need to use `override` if the child class's function is to override its parent. 
```CSharp
class B : A {
    public virtual void Msg(){
        Console.WriteLine("B");
    }
}
class C : B{
    public override void Msg(){
        Console.WriteLine("C");
    }
}
```
```CSharp
B b = new C()
b.Msg();
//output is C
```

