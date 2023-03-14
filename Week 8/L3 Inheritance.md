Except for `java.lang.Object`, objects have more than 1 type. It's type include:
- its own class type
- all of its ancestor class types
- all of its interface types

The class
```java
public final class String extends Object implements Serializable, Comparable<String>, CharSequence
```
has types
- `String`
- `Object`
- `Serializable`
- `Comparable<String>`
- `CharSequence`

# Polymorphism
- definition by the dictionary: "The condition of occuring in several different forms"
- Java has subtype polymorphism
	- subtypes are substitutable for their ancestor types
	- This is possible because the type of the object includes the types of all its ancestor class
# Runtime Types
In an assignment or nitialization expression, the type of the value on the right-hand side of the `=` is the runtime type or the actual type. The declared type is the left hand side and determines what operations can be performed

```java
Counter c;
c = new StoppingCounter();
```
The declared type is `Counter` but the runtime type is `StoppingCounter`.

- The runtime type determines which version of a non-static method is called when using a variable, field, or parameter
```java
Object obj = new Counter();
String s = obj.toString();
```
causes the `Counter` version of `toString()` instead of the `Object` version at runtime

Consider the following program
```java
public class Printer {  
	public static void print(Object obj) {  
		System.out.println(obj.toString());  
	}  
}

String s = "hi there";  
Printer.print(s); // String version of toString  

ArrayList<Integer> t = new ArrayList<>();  
t.add(9);  
t.add(1);  
t.add(1);  
Printer.print(t); // ArrayList version of toString  

Object o = new Date();  
Printer.print(o); // Date version of toString
```