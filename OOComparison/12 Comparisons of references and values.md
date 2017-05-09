# Comparisons of references and values
How are values compared? (i.e. comparing two strings)
***
#### Java
* The code `==` tests for reference equality, that is whether or not two names are referencing the same object. While the `.equals` method tests if two objects values are logically equivalent. An example of both using Strings is presented in the following example.
    ```Java 
        String compare1 = "compare";
        String compare2 = new String("compare");
        String compare3 = "compadre";
        String compare4 = compare1;
        boolean result1 = compare1.equals(compare2);//TRUE
        boolean result2 = compare1 == compare2;//FALSE
        boolean result3 = compare1 == compare4;//TRUE
        boolean result4 = compare1.eqauls(compare3);//FALSE
    ```
#### C#
* C# also has functionallity for detemining reference equality and logical equality. To test for reference equality use `Object.ReferenceEquals(object1,object2)`. To test for logical equality use `object1.Equals(object2)`. Similarily to Java the code `==` tests for reference equality, EXCEPT it tests for logical equivalence between two strings so long as the two things that are being compared are actually of type string.