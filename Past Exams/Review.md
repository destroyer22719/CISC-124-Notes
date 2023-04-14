# Review

# Q1
## A
c represents the amount of times the constructor got instantiated
## B
Because it's a static field
## C
The error in the floating point arithmetics
## D
That the count can never be below zero
## E
Because it would allow it to be manipulated outside the `Counter` class and we don't want that for what we intend for `value` to behave and represent
## F
A defensive copy is a copy that won't result in a privacy leak

## H
For classes to implement an interface they must use the implements keyword while they have to use the extends keyword to use an abstract class

Abstract classes can define implementations for methods while interfaces can only define the method signature

## I
- Iterable
- Comparable
- Set

## J
No, generics are invariant

## K
The declared type is `Object` while the runtime type is `String`

## L
No, type `Object` doesn't have the method of `toUpperCase()`;

## M
Because you can only use binary search on a sorted list of data while linked lists don't have to be

## N ?
O(N)

```java

```

# Q2
```java
DimmableLight() {
	super()
}

DimmableLight(Brightness b) {
	if (b.getLevel() > 0) {
		super(true)
	} else {
		super(false);
	}
}

@Override
public void off() {
	this.level = 0;
}

@Override
public void on() {
	this.level = 100;
}

void brighter() {
	if (this.level >= 100) return;
	this.level++;
}
```

# Q3

```java
public int indOf(Object o) {
	if (!(o isintanceof Node<E>)) {
		throw new IllegalArguementException();
	}
	

	int currIndex = 0;
	Node<E> curr = this.head;
	Node<E> target = (Node<E>) o;
	while(curr != null) {
		if (c.elem == o.elem) {
			return currIndex;
		}
		currIndex++;
		curr = curr.next;
	}

	return -1;
}

private int search(Node<E> target, Node<E> curr, int index) {
	if (node  {
		return index;
	} else if (target.elem == curr.elem) {
		return -1;
	}
	return search(target, curr.next, index++)
}

public int indexOf(Object o) {
	if (!(o isintanceof Node<E>)) {
		throw new IllegalArguementException();
	}
}

public void moveAllToEnd(Object o) {
	if (!(o isintanceof Node<E>)) {
	
	}
}
```