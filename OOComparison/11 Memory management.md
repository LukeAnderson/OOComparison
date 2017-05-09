# Memory management
How is it handled?
How does it work?
Garbage collection?
Automatic reference counting?
***
#### Java
* Memory management in Java is handled automonously. Programmers do not have to worry about allocating and deallocating memory space for their objects, it is all handled by the Java virtual machine.
* Objects made in Java exsist in the heap which is made at the startup of the Java virtural machine. When the heap becomes full then garbage is collected. The heap is broken up into two parts a young space, for short lived objects, and an old space for longer lived objects. Most objects will die in the young space of the heap as most objects are short lived.  
* Gabage collection is the process when objects which are no longer being used are removed from the heap to make room for new objects. In addition to removing objects when they are no longer being referenced. Garbage collection acts differently for the two parts of the heap. When the young space becomes full then gabage collection moves some objects from the young space to the old space. When the old space is full then garbage collection attempts to free up more space by compacting. 
* Java does not use automatic refernce counting it uses mark-and-sweep to remove objects from the heap. Garbage collection marks objects as reachable and sweeps unreachable objects from memory clearing them from the heap. 
#### C#
* In C# memory management is handled by an automatic process implemented by a garbage collector.
* If the object or any part of it is no longer accessable then the object is considered no longer in use and may be deleted. If the gabage collector elects to delete the object then that objects destructor will be called first if it has one. Afterwards the garbage collector eventually frees up the memory that inaccessable object takes up. 
* C#s garbage collection while typically running automatically, such as in Java's garbage collector, can be controlled using static methods in System.GC. Notably programmers can request a collection to occur and whether or not to run destructors. 
* C#'s garbage collector does not use automatic reference counting. The garbage collector behaves using a similar mark and sweep algorithm as Java does. The garbage collector is faster without reference counting.