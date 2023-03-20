Suppose we created an `IntStack` class and we want to make one for `String`  type. We can make a seperate `StringStack` class but all we do is just change the type `int` to `String`. There is a convenient way to do it for all types for our stack using generics.

We can use:
- `Stack<Integer>` instead of `IntegerStack`
- `Stack<String>` instead of `StringStack`

# Declaring a Generic Class
A generic class uses the following syntax
```java
class ClassName<T1, T2, ... , Tn> {}
```
The type parameters are single, uppercase letters. 

Naming convention for type parameters:
- `E` - Element
- `K` - Key
- `N` - Number
- `T` - Type
- `V` - Value

# Use Cases
We can't return multiple types in Java, we can use a generic class to hold multiple values for us
```java
public class Pair<T1, T2> {
	public T1 a;
	public T2 b;
}
```

## Generic Stack Class
```java
import java.util.Arrays;  
import java.util.EmptyStackException;  
public class ArrayStack<E> {  
	// the initial capacity of the stack  
	private static final int DEFAULT_CAPACITY = 16;  
	// the array that stores the stack  
	private E[] stack;  
	// the index of the top of the stack  
	private int topIndex;  
	/*
	* Create an empty stack.  
	*/  
	public ArrayStack() {  
		this.stack = new E[Stack.DEFAULT_CAPACITY]; // <-- This is NOT allowed
		this.topIndex = -1;
	}
}
```
We CANNOT create an array of our generic! The solution is to make an array of Object.

```java
import java.util.Arrays;  
import java.util.EmptyStackException;  
public class ArrayStack<E> {  
	// the initial capacity of the stack  
	private static final int DEFAULT_CAPACITY = 16;  
	// the array that stores the stack  
	private Object[] stack;  
	// the index of the top of the stack  
	private int topIndex;
	
	/*
	* Create an empty stack.  
	*/  
	public ArrayStack() {  
		this.stack = new Object[Stack.DEFAULT_CAPACITY];  
		this.topIndex = -1
	}
}
```

**Arrays are Covariant**
If `Sub` is a subtype of `Super` then the array type `Sub[]` is a subtype of the array type `Super[]`

**Generics are Invariants**
For any 2 distincts types `T1` and `T2`, `List<T1>` is neither a subtype nor supertype of `List<T2>`

See [this](https://www.javacodegeeks.com/2019/04/variance-java.html) article about covariant and invariant