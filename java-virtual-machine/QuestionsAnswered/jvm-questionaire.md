# In your own words what is the JVM?
It is in charge of interpreting the compiled Java code for a computer's processor, so that it can execute Java's language instructions. 
It can be seen as an abstraction between the operating system and the programming language. 
It does Garbage collection.
Allows portability, so applications compiled could be run on any platform without requiring to be recompiled.
It has the ability of either interpret the compiled byte code or compiling it using the JIT.
It acts as a sandbox.

# What about JIT? What is it?
It stand up for Just-in-time compilation. Compilation at runtime.
Basically, the compiler runs once the program has started. 
Compiler translates high-level language into pseudo-code, which in turn will be interpreted to run the program.
This eliminates de use of executables, making the code more portable.

# How can you execute GC?
With "System.gc();" command.

# What are the downsides of GC?
- Takes away control from the developer.
-Performance issues.
-While the GC will never collect a live object, it doesn't guarantee the collection of all dead objects.

# In few words what can you say about the heap space?
Is the amount of memory available for Java applications to store data when they are running. 
It is managed by de JVM.
It contains: 
	Eden Space
	Survivor Space
	Tenured Generation

# What about PermGen? How to increase?
The place where class loading happens, loading and unloading of classes, methods, String pool, etc.
It is independent from the heap area.
GC run less frequently in this space.
To increase de size, the application launch configuration must be configured specifiying parameter -XX:MaxPermSize.

# How to increase Java heap?
The size of the heap can be customized by setting parameter -Xmx. If you do not set the size explicitly, defaults will be used.

# Explain Hotspot Heap structure
Eden Space (heap): The first pool from which memory is allocated initially for new objects.
Survivor Space(heap): The pool that contains objects that have survived the GC.
Tenured Generation (heap): The pool that cointans objects that have survived some GCs.
Permanent Generation (non-heap): The pool containing class and method objects.
Code Cache (non-heap): Memory used for compilation and storage of native code.

# Give two scenarios where you can get an OutOfMemoryError error
java.lang.OutOfMemoryError: PermGen which indicates that the Permanent Generation area in memory is exhausted.
java.lang.OutOfMemoryError: Java heap space error when the application is attempting to add, but the space is full.

# How can VM technology be beneficial for slow programs? 
The usage of JIT compliler in the VM makes optimization for the CPU that the program would run on, producing more "optimal code".
The code is compiled into low-level machine languaje which can be cached for later usage.