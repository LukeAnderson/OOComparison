# Null/nil references
Which does the language use? (null/nil/etc)
Does the language have features for handling null/nil references?
***
#### Java
* Java uses null.  Null is to be used when the object is not referencing anything. Java in addtion to the regular primitive types has wrapper classes that 'wrap' primitives into objects. For instance there is int and Integer. Primitive types like int can not be set to null. However Integer can be set to null as Integer is a class . 
#### C#
* C# uses null. Objects can be assigned null to indicate that they are not referencing anything. Addtionally C# has nullable types where data types can be assigned null. Nullable is in System. To create a nullable type add a question mark after the keyword of the primitive your trying to make or use the longhand version by writing out Nullable<Type>. For example:
```CSharp
    int aTypicalInt = 1;
    int? aNullableType = null;
     Nullable<anotherNullableType> = null;
    //to set aTypicalInt to aNullableType do one of the following:
    aTypicalInt = (int)aNullableType;
    aTypicallInt = aNullableType.Value;
    //an exception will be created if aNullableType is null
```
