# Instance reference name in data type (class)
***
#### Java 
* Uses the keyword `this`
#### C#
* Uses the keyword `this`

Both Java and C# use`this` to refer to the current instance of an object that is running. 
```Java
    public class Cat{
        public int age; //public variable of Cat class 
        public Cat(int age){
            this.age = age;
        }
    }
```
In the above code the public variable, 'trees', gets referenced in the constructor using the keyword `this`. The public variable `trees` is then set equal to the parameter `trees` in the constructor of the class.