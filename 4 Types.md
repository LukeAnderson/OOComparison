# Types
What types does the language support?
Are both reference and value types supported?
Can new value types be created?
***
#### Java 
* The languages supports both reference and value types

* Primitvies are value types. Both objects and enumerations are reference types. The defualt value of any reference type is null. The default values for primitives are as follows
    | primitve         	| default 	|
    |------------------	|---------	|
    | boolean          	| false   	|
    | byte, short, int 	| 0       	|
    | long             	| 0L      	|
    | float            	| 0.0f    	|
    | double           	| 0.0d    	|
    | char             	| 'u0000' 	|
* No but value types is a planned feature in Project Valhalla, which is an effort by Oracle to devlop new features for Java 10 + 
#### C#
* The languages supports both reference and value types as well as pointer types.

* Value types in C# all are derived from `System.ValueType` they encompass bool, byte, char, decimal, double, enum, float, int, long, sbyte, short, struct,uint, ulong, and ushort. 
Reference types in C# include class, delegate, dynamic, interface, object, string, and Interpolated Strings
`class`, `interface`, and `delegate` are keywords to declare refernce types. The other reference types are built into C#.
* Yes, you can create your own value types using `struct`
    Example
    ```CSharp
    struct Circle {
        public int x,y,radius;
        public Circle (int p1, int p2, int p3){
            x = p1;
            y = p2;
            radius = p3;
        }
    }
    ```
