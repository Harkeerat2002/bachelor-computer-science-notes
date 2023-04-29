#subject
[Semester:: 2]   •   [Year:: 1]   •   [ECT:: 6]• [Completed:: ✅]
# Accessor and mutator methods

## Accessor Methods:

**Methods** which _return_ information to the called about the state of an object is called as the accessor methods. An accessor methods usually contains a _return_ statement in order to pass back that information. An accessor could be thought as as method which requests information.

**Example of an Accessor Method:**

```java
public int getBalance() {    return balance: //returning information}
```

## Mutator Methods:

Methods that change the value of one or more fields of an object each time that they are called, is known as Mutator methods. A mutator could be think as a method which is asked for an object to change its state.

**Example of a Mutator Methods:**

```java
public void insertMOney(int amount) {    balance = balance + amount;}
```

# If-Statements

In If-Statements, there would be either a

```java
if(amount > 0) {
    balance = balance + amount;
} else {
    System.out.println("Use a positive amount rather than: " + amount);
}
```

# For-Each loop

A _for-each loop_ is one way to perform a set of actions repeatedly on the items in a collection, but without having to write out those actions more than once.

**Example:**

```java
for(String filename : files) {
    System.out.println(filename);
}
// "String filename" = ElementType element
// "files" = collection
```

# Abstraction and Modularization

Dividing the problem into sub-problems, then again into sub-sub-problems, and so on, until the individual problems are small enough to be easy to deal with. Once we solve one of the sub-problems, we do not think about the details of that part any more, but treat the solution as a single building block for our next problem. This technique is also sometimes referred to as _divide and conquer_. Whereas, modularization is the process of dividing large problems into smaller parts, where abstraction is the process of ignoring details to focus on the bigger picture.

# Primitive Types and Object Types

Java knows two very different kings of type: _primitive types_ and _object types_. Primitive types are predefined in the Java language. the include **int** and **boolean**.

Object types are those defined by classes. Some classes are defined by the standard Java system (such as String); others are those classes we write ourselves.

The main difference between primitive types and object types are that the way they store the values. Primitive values are stored directly in a variables. Objects, on the other hand are not stored directly in the variable, but instead a reference to the object is stored.

**Example of Primitive Types:**

-   int
-   boolean
-   char
-   double
-   long

# ArrayList and Array

**Arrays** are simple fixed size arrays that is created in Java, like bellow:

```java
int arr[] = new int[10];
```

**ArrayList** are Dynamic sized arrays in Java that implement List interface:

```java
ArraList<Type> arrL = new ArraList<Type>();// Here "Type" is the type of elements in the ArraList to be created
```

## Differences between Array and ArrayList:

1.  An array is basic functionality provided by Java. ArrayList is part of **collection** **framework** in Java. Therefore array members are **accessed using** **[]**, while ArrayList has a set of methods to **access** **elements** and **modify** them.
    
    **Example:**
    
    ```java
    // A Java program to demonstrate differences between array
    // and ArrayList
    import java.util.ArrayList;
    import java.util.Arrays;
      
    class Test
    {
        public static void main(String args[])
        {
            /* ........... Normal Array............. */
            int[] arr = new int[2];
            arr[0] = 1;
            arr[1] = 2;
            System.out.println(arr[0]);
      
            /*............ArrayList..............*/
            // Create an arrayList with initial capacity 2
            ArrayList<Integer> arrL = new ArrayList<Integer>(2);
      
            // Add elements to ArrayList
            arrL.add(1);
            arrL.add(2);
      
            // Access elements of ArrayList
            System.out.println(arrL.get(0));
        }
    }
    ```
    
2.  Array is a **fixed** **size** **data** structure while **ArrayList** is **not**. One need not to mention the size of ArrayList while creating its object. Even if we specify some initial capacity, we can add more elements.
    
    **Example:**
    
    ```java
    // A Java program to demonstrate differences between array
    // and ArrayList
    import java.util.ArrayList;
    import java.util.Arrays;
    class Test
    {
        public static void main(String args[])
        {
            /* ........... Normal Array............. */
            // Need to specify the size for array 
            int[] arr = new int[3];
            arr[0] = 1;
            arr[1] = 2;
            arr[2] = 3;
            // We cannot add more elements to array arr[]
      
            /*............ArrayList..............*/
            // Need not to specify size 
            ArrayList<Integer> arrL = new ArrayList<Integer>();
            arrL.add(1);
            arrL.add(2);
            arrL.add(3);
            arrL.add(4);
            // We can add more elements to arrL
      
            System.out.println(arrL);
            System.out.println(Arrays.toString(arr));
        }
    }
    ```
    
3.  **Array** can **contain** both **primitive** **data** **types** as well as **objects** of a class depending on the definition of the array. However, **ArrayList** **only supports object entries**, not the primitive data types.
    
    Note: When _arraylist.add(1);_ is done it converts the primitive int data types in an Integer Object.
    
    **Example:**
    
    ```java
    import java.util.ArrayList;
    class Test
    {
        public static void main(String args[])
        {
           // allowed
            int[] array = new int[3];
      
            // allowed, however, need to be initialized
            Test[] array1 = new Test[3];
      
            // not allowed (Uncommenting below line causes
            // compiler error)
            // ArrayList<char> arrL = new ArrayList<char>();
      
            // Allowed
            ArrayList<Integer> arrL1 = new ArrayList<>();
            ArrayList<String> arrL2 = new ArrayList<>();
            ArrayList<Object> arrL3 = new ArrayList<>();
        }
    }
    ```
    

# Iterator

An **Iterator** is an object that can be used to loop through collections, like ArrayList. It is called and “iterator” because “iterating” is the technical term for looping.

**Example:**

```java
// Import the ArrayList class and the Iterator class
import java.util.ArrayList;
import java.util.Iterator;

public class Main {
  public static void main(String[] args) {

    // Make a collection
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");

    // Get the iterator
    Iterator<String> it = cars.iterator();

    // Print the first item
    System.out.println(it.next());
  }
}
```

# Recursion and Iteration

When Java function calls itself, it’s known as **recursion**. When we have a repeating loop, we’re are using **iteration**. Both approaches repeatedly execute lines of code and have an exit point to avoid creating infinite loop and system crashes.

## Recursion:

```java
public String execute(final VariableTable variables) {
        final OperandStack stack = new OperandStack();
        final Storage storage = new Storage(stack, variables);  
    
        while(i <= getLength()) {
            Instruction instruction = code.get(i);
            instruction.execute(storage);
            i++;
            execute(variables); //recusrive call
        }
    }
```

## Iteration:

In Java, iteration is a technique used to sequence through a block of code repeatedly until a specific condition either exists or no longer exists. Iterations are a very common approach used with loops.

Common examples include iterating through a list of grades to compute a final grade-point-average, processing a list of email addresses to validate their format, and processing a text file. We can also use iteration as an approach to the name reversal and factorial functions.

**Example:**

```java
public String execute(final VariableTable variables) {
        final OperandStack stack = new OperandStack();
        final Storage storage = new Storage(stack, variables);
    	for(int i = 0; i < code.getLength; i++) {
            code[i].execute(storage);              //iterative for-loop
        }
        return stack.pop();
    }
```

# Immutable and Mutable Objects

## Immutable Objects:

The immutable objects can not be changed to its value or state once it is created. An example is bellow:

```java
final int immutableObject = 10;    
// The term "final" reffers to immutableObject being immutable.
```

## Mutable Objects:

The mutable objects can be changed to any value or state without adding a new object. An example is bellow:

```java
int mutableObject = 10 // Making the mutable object
mutableObject = 1      // Changing the object
```

# Static and Non-Static Methods

A **static method** is a method which can also be accessed by other classes by just using the class name.

A Non-static method is a method which can only be accessed if an object is made of that class.

**Example:**

```java
public class Tiger {
    public void eat() {			// A non-static method
        System.out.println("Tiger eats");
    }
    
    public static void roar(){	// A  static method		
        System.out.println("Tiger roars");
    }
}
```

```java
public class JavaTester {
    public static void main(String args[]) {
        Tiger.roar();			// Directly accessing the method roar() through the class name itself
        Tiger tiger = new Tiger();
        tiger.eat();			// Accessing the method eat() by making an object of Tiger class
    }
    
}
```

# Public, Private and Protected

**Public** mean that **everyone** can see it. For instance if a class is public that means, that other classes can access it, or if a method is public that means that class itself and other classes can access it.

```java
public class publicClass {
	// methods immeted
}
```

**Protected** means that the **class and the sub-classes** can access it. It is same with the methods as well, only the class and the sub-classes can access it.

```java
protected class protectedClass {
	// methods immeted 
}
```

**Private** means that **only** **the** **class** **itself** access it, and it is same for the methods as well since only the class itself can access it.

```java
private class privateClass {
 	// methods immeted
}
```

# Inheritance and Polymorphism

## Inheritance

Inheritance is one in which a new class is created that inherits the properties of the already exist class. It supports the concept of code reusability and reduces the length of the code in object-oriented programming. There tends to be class hierarchy, in which there consists of a parent class, and then there are sub-classes which use the methods of its parent classes. This is the concept of abstraction and modularization in which a problem is divided into sub-problems or sub-sub-problems to make them much more easier to understand.

**Example:**

```java
public class Post {
    private String username;
    private long timestamp;
    private int likes;
    private ArrayList<String> comments;
	
    public Post(String author) {
        username = author;
        timestamp = System.currentTimeMillis();
        likes = 0;
        comments = new ArrayList<String>();
    } 
} //methods omitted
```

```java
public class MessagePost extends Post {
    private String message;
    
    public MessagePost(String author, String Text) {
        super(author);   // Calls the Post class's constructor
        message = text;
    }
}
```

## Polymorphism

Polymorphism is the treatment of the object as the same. Which means that all the object can be called by its parent class, which in detail means that it would be treated the same.

# Abstraction Techniques

## Abstract Class

Abstract class are classes in which it has a at least one method which is abstract. A method which is abstract means that it is not completed. Hence it get completed in its sub-classes. Therefore, the instance of a abstract class cannot be made.

## Interface Class

In a Interface all the methods are abstract methods, and it does not contain a constructor and neither any variables in the fields. There are also some differences between abstract and interface in the syntax as well.

### Difference between Interfaces and Abstract Class:

[Untitled](https://www.notion.so/1cdfc67cf4ec47068175d9f0cfc8e431)

### **Difference Syntax between Abstract Class and Interface:**

**Abstract Class:**

```java
public abstract class Animal {
    public void Animal(int x){       // Has a constructor
        x = 0;
    }
    public abstract void animalSound();
    public abstract void sleep();
}
```

```java
class Pig extends Animal {
    public void Pig(){       		// Has a constructor
        super.(1);
    }
    public void animalSound() {
        System.out.println("The pig says: wee wee");
    }
    public void sleep() {
    // The body of sleep() is provided here
    System.out.println("Zzz");
  }
}
```

**Interface Class:**

```java
interface Animal {
  public void animalSound(); // interface method (does not have a body)
  public void sleep(); // interface method (does not have a body)
}
```

```java
// Pig "implements" the Animal interface
class Pig implements Animal {
  public void animalSound() {
    // The body of animalSound() is provided here
    System.out.println("The pig says: wee wee");
  }
  public void sleep() {
    // The body of sleep() is provided here
    System.out.println("Zzz");
  }
}
```