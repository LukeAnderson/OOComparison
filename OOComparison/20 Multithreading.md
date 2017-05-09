# Multithreading
Threads or thread-like abilities
How is multitasking accomplished?
***
#### Java
* There are threads. A programmer can create a thread by either making a class and implementing the `Runnable` interface and then making a new thread with that such as ` Thread myThread = new Thread(new MyRunnableInterface());` or by makinmg a class extend `java.lang.Thread` and just using that like `Thread myThread = new MyThread();`. In both cases the programmer overides the run method. The `run()` method is executed while the thread is running. The thread is alive until the execution of the run method is complete. The method `start()` also needs to be called before the thread obj can call run().  
* Java supports multithreading. Here is an example of using multiple threads in Java.  
```Java
public class MyThread extends Thread{
    @Override
    public void run(){
        System.out.println(this.currentThread().getName());
    }
}
public class MyMultiThread {
    public static void main ( String [] args){
        MyThread thread1 = new MyThread();
        thread1.setName("thread1");
        
        MyThread thread2 = new MyThread();
        thread2.setName("thread2");
        
        MyThread thread3 = new MyThread();
        thread3.setName("thread3");
        thread3.setPriority(Thread.MAX_PRIORITY);
        
        thread1.start();
        thread2.start();
        thread3.start();
    }
}
```
The output is the threads stating their names. Thread3 is set to max priority so it should be ran before the other threads. However, this is system architecture dependent and may not be the case. 

#### C#
* Threads are implemented in C# by `using System.Threading;` The following example shows how to implement multiple threads in C#:
```CSharp
using System;
using System.Threading;
public class MyThread {
    public static void RunThread1() {
        for (int i = 0; i < 10; i++) {
            Console.WriteLine("Thread1 {0}", i);
        }
    }
    public static void RunThread2() {
        for (int i = 0; i < 10; i++) {
            Console.WriteLine("Thread2 {0}", i);
        }
    }
}
public class MainClass {
        public static void Main() {
                Thread t1 = new Thread(new ThreadStart(MyThread.RunThread1 ) );
                Thread t2 = new Thread(new ThreadStart(MyThread.RunThread2 ) );
                t1.Start();
                t2.Start();
        }
}
```
This will run two threads until they both finish counting up to ten. C# uses the ThreadStart delegate located in System.Threading to help create the threads. This delegate takes in a method that will be used to run the thread. Like the run() method is used in Java for running threads. Then to create a new thread simply state `Thread myThread = new Thread(ThreadStart(threadRunThis));` so the Thread class takes the thread delegate so that it has knowledge of what method to run and all the other added delegate benefits and then to start the thread is done the same as it was in Java with calling the start() method. 