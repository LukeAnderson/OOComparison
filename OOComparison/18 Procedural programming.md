# Procedural programming
Does the language support procedural programming?
***
#### Java
* Yes, however Java was designed and is an object oriented language. If you want to code procedurally in Java then make methods static.
```Java 
public class ObjectProceduralNamespace {
    public static void main(String [] args){
        double width = 4.0;
        double height = 5.0;
        double area;
        area = calculate_area(width,height);
        System.out.println(area);
    }
    public static double calculate_area(double width,double height){
        return width*height;
    }
}
```
#### C#
* Yes in C# one can code procedurally by using static functions similar to the Java example. 