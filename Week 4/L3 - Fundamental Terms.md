---
tag: types, classes
---
### Type
A type is a set of values and operations that can be performed with those values

For example:
- `int`
	- 32-bit signed integer value
	- supports arithmetic and comparrison operations
### Primitive Types
A primitive types are the built-in numeric types and type boolean
![[Pasted image 20230313170236.png]]
### Reference Types
Every type that's not primitive is a reference type

**Examples:**
-` int[]`
- `String`
- `ArrayList<>`
### Class
- A class is an implementation of a reference type
- A class is a type but all types are classes
### Object
An object is an instance of a class
![[Pasted image 20230313170430.png]]
### Reference
- A reference is an identifier that can be used to find a particular object
- In the case above, `t` is the reference to the object
- Any variable whose type is not primitive stores a reference

## Elements of Object Orientated Programing
- Abstraction
	 Abstraction is about showing only the necessary information but hides/abstracts the unnecessary information
- Encapsulation
	Encapsulation is the process of grouping together related information. It is achieved when objects keeps its state private from other objects. If you want objects to communicate with others it must use its public methods
- Modularity
	The act of seperating the program into individual components

### Organization of a Java Program
![[Pasted image 20230313171536.png]]
### Packages
- Packages are used to organize Java classes into namespaces
- A namespace is a container for names
- packages are used to organize related classes and interfaces
	- e.g all of Java's API classes are in the package named `java`
- packages can have subpackages
	- e.g `java` contains packages `lang`, `util`, `io`, etc.
- packages can contain classes and interfaces
	- e.g the package `java.lang` contains classes `Object`, `String`, `Math`, etc.
- The fully qualified name of the class is the fully qualified name of the containing package followed by a period followed by the class name
	- e.g `java.lang.Math`
- Packages are supposed to ensure that fully qualified names are unique
### Access modifiers
![[Pasted image 20230313173121.png]]

### Types of Methods
- Mutator Methods: Change the state of the object
- Accessor Methods: Returns information about the state of an object

### Method Header
```java
public Point2 set(double x, double y)
```
- `public` is the modifier
- `Point2` is the return type
- `set` is the method name
- `(double x, double y)` is the parameter list
### Method Signature
- Every method has a signature, which contains the method name and types in the parameter list
- In the case above the method signature is
	`set(double x, doubley)`
- Method signatures must be unique
- Two or more methods with the same name but different signatures is called an <u>overload</u>
### Method Return Types
All Java methods return either `void` (nothing) or a single type of value

In java every class is actually a child class of the class `java.lang.Object`
Which means that every class has methods it inherits from it. Which contain 11 methods but the 3 most important are:
- `toString()`
- `equals`
- `hashCode`
### Copy Constructors
A copy constructor initializes the state of an object by copying the state of another object of the same time
```java
public Point2(Point2 other) {  
	this.x = other.x;  
	this.y = other.y;
}
```
### Constructor Chaining
A constructor is allowed to invoke another constructor, when that happens it's called <u>Constructor Chaining</u>. You must use the `this` keyword and it must be the first line. You **can't** do it in a method to invoke a constructor
![[Pasted image 20230313174618.png]]
