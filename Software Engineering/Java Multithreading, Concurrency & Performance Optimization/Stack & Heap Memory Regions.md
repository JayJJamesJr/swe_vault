
What we learn in this lecture

- Stack Memory Region
- Heap Memory Region

What is the [[stack]] ?
- Memory Region where:
	- Methods are called
	- Arguments are passed
	- Local variables are stored
- Stack + Instruction Pointer = State of each thread's execution 

### Information stored in a stack

- Method arguments
- Local Variables

For each additional method call a new stack frame is created where any additional method arguments and local variables will be stored. For example if a method call is made from the inside of a stack frame, a new stack frame will be created to process the result of that method call and store it in the previous stack that the call was made from. 


## Heap Memory Region

The heap is a shared memory region that belongs to the process. 

## What is allocated in the heap? 

- Objects (anything created with the *new* operator)
	- String
	- Object
	- Collection 
- Members of classes (Instance Variables)
- Static variables

## Heap Memory Management

- Governed and managed by [[Garbage Collector]]
- Objects - stay as long as we have a reference to them.
- Member of classes - exist as long as their parent objects exist (same life cycle as their parents)
- Static variables - stay forever

** Look into the difference between an object and a reference

## What's the difference between an object and a reference? 

1. **Object:**
    
    - An object is a specific instance of a data structure that has a particular type or class.
    - It represents a chunk of memory that has been allocated to store the data and methods associated with a particular type or class.
    - Objects can have attributes (data members) and methods (functions associated with the class).
2. **Reference:**
    
    - A reference is a value that refers to the memory address of an object.
    - It does not contain the actual data but points to the location in memory where the object is stored.
    - References are used to access and manipulate objects indirectly.
