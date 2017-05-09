# Functional programming
Does the language support functional programming?
***
#### Java
* Yes, as seen in section 15 Java has lambdas and anonymous funciton that work in a functionl way. 
#### C#
* Yes C# supports functional programming. As seen in section 15 C# has lambdas and delegates that can operate in a funcitonal way. 
* For both Java and C#  the programmer needs to make sure that the signitures for the mathematical functions they define are honest, meaning that there will be for all possible inputs some valid output. For example:
```CSharp
public static int Divide(int x , NonZeroInteger y){
    return x/y.Value;
}
```
This is one way the programmer can make their function more honest than just `Divide(int x,int y)` as it deals with the edge case if someone tried to divde by 0. 