# Reflection
What reflection abilities are supported?
How is reflection used?
***
#### Java
* Reflection enables Java to regurgitate source code including fields and methods with their access modifiers of any class. 
* Refelction is used by programs that requrie the ability to examine/modifiy the runtime behavior of applications. In Java refelction is located in java.lang.reflect.* 
    ```Java
    import java.awt.Color;
    public class Ball {
        public Color color;
        public int size;
        public Ball(Color color){
            this.color = color;
        }
        public boolean isColor(Color color){
            return this.color == color;
        }
        public int getSize(){
            return size;
        }
        public void setSize(int size){
            this.size = size;
        }
    }
    
    import java.lang.reflect.*;
   public class MainClass {
        public static void main(String args []){
            Class aReflectedClass = Ball.class;
            String className = aReflectedClass.getName();
            System.out.println("Class name:" + className);
            System.out.println("Methods");
            
            Method[] classMethods = aReflectedClass.getMethods();
            
            for(Method method : classMethods){
                String methodName = method.getName();
                Class<?> returnType = method.getReturnType();
                
                Class[] parameterType = method.getParameterTypes();
                String parametersName = "";
                for(Class parameter : parameterType){
                    parametersName += parameter.getName() + " ";
                }

                System.out.println(returnType + " "+ methodName + "(" + parametersName + ")" );
            }
        }
    }
    ```
  In the above example it is demonstrated how to find out method names with parameters and access modifiers using refelction. 
#### C#
* C# is similar to Java it uses reflection for many of the same purposes. Typically one uses refelction in C# if you want to view metadata or build new types at runtime and for accessing methods on types created at runtime. Similar to Java you can also gain access to constructor information. 
    You can obtain type information using refelction as demonstrated in the following example:
    ```CSharp
        int age = 22;
        System.Type type =  age.GetType();
    ```
    type is then equal to System.Int32