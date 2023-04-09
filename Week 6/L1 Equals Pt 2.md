The version of `equals` from last week is fine if the class is never used as part of an inheritance hierarchy

Otherwise we should consider using the version of equals discussed in this lecture

Refer to [[Equals]]
#### New Things

- Instances of compatible types can be equal
	`val instanceof MyType`
	
	```java
	if (!(this instanceof Point2)) {
		return false;
	}
```

### HashCode
If you override `equals` you **must** override hashCode or else:
```java
Point2 p = new Point2(1.0, -2.0);  
HashSet<Point2> h = new HashSet<>();  
h.add(p);  
System.out.println(h.contains(p)); // true  
Point2 q = new Point2(1.0, -2.0);  

System.out.println(h.contains(q)); // false!
```
To implement a custom one
```java
public class Point2x {  
	public float x;  
	public float y;  
	@Override  
	public int hashCode() {  
	return Objects.hash(this.x, this.y);  
	}
}
```
### Comparable Objects
If your class has a natural ordering, consider implementing the `Comparable` interface. Doing so allows clients to sort arrays or `Collections` of your object

The `Comparable` interface has just one method
```java
public interface Comparable<T> {  
int compareTo(T t);
}
```
The `compareTo()` method:
- returns a negative int when it's less than
- a positive int when it's greater than
- 0 when it's equal to the specified object
- Throws a `ClassCastException` if  the specified object type can't be compared to this object

To compare two double values
```
Java.lang.Double

//...
return Double.compare(x, y)
```

```java
public void retain(Predicate<E> pred) {
	Node curr = this.top;
	while(true) {
		if (!curr.next) {
			return;
		}
		if (!pred.test(curr.next)) {
			Node validNode;
			while(true) {
				if (!curr.)
			}
		}
	}
}
```