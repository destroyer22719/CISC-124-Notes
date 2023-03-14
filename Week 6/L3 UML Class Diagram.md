![[Pasted image 20230314000150.png]]
Access modifiers for fields
- `+` public
- `-` private
- `~` package private (default)
- `#` protected

### Classes that implement an interface
To show that a class implements the `Comparable` interface we can use the lollipop notation
![[Pasted image 20230314000245.png]]

### Dependency
Class `X` depends on `Y` if `Y` appears as:
- A field of `X` (variable inside a class)
- A parameter or a variable type in the method or constructor of `X`
- A return type of a method in `X`

![[Pasted image 20230314000549.png]]
In the UML Diagram above `Point2` depends on `Vector2` and `String` while `Vector2` depends on `String`

### Association
Association is a strong form of dependency. If a class `X` has a field of type `Y`, then we say that it has an association of `Y`

It can be shown in a UML class diagram using a solid line connecting the two classes

![[Pasted image 20230314000840.png]]
There are 1 `SimpleImage` objects that participate in the relation

## Aggregation and Composition
- Composition implies ownership
	- A university is a composition of its departments, if the university dissapears then all of its departments dissapear
- Aggregation does not
	- If the university department dissapears, the professors don't
	- Thus a department is an aggergation of professors
- Unlike association and dependency, they are one-way relationships
- ![[Pasted image 20230314001246.png]]
### Composition
![[Pasted image 20230314002315.png]]
- Never return a reference to a field, always return a deep copy.
```java
public Y getY() {
return this.y;
}
```
- If you do that the client and the `X` object will share the same `Y` object, this is called a privacy leak
	-  Note: A shallow copy points to the same referece whereas deep copy copies all fields 
- If `X` has a method that sets its `Y` object provided by the client it must make a deep copy of the client-provided `Y` object and validate it
```java
public void setY(Y y) {
	Y copyY = new Y(y) // defensive copy
	this.checkY(copyY);
	this.y = copyY;
}
```

### Class Invariance
A condition that must hold true for the life of an object of the class. For example our bank account class can't have its balance exceede 0 and the `withDrawMoney()` method should respect that.

### Privacy Leaks
Occurs when a class exposes a reference to a non-public field that's not primitive or immutiable

```java
public X(Y y) {
	this.y = y;
}

public Y getY() {
	return this.y;
}
```
A privacy leak allows some other object to control the state of the object

### Recipe for Immutability
- Do not provide any methods that can alter the state of the object
- Prevent the class from being extended (inherited)
- Make all fields `final` and `private`
- Prevent clients from obtaining a reference to any mutable fields