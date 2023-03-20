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