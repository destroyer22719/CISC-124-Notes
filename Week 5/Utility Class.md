The purpose of a utility class is to group together related fields and methods where creating an object is not necessary. **A utility class is never used to create objects**

To make it so you can't create an object of the utility class make a private constructor

```java
public class MyUtilityClass {
	private MyUtilityClass() {}
}
```

## Static Factory Methods
A common use of static methods in non-utility classes is to create a static factory method

A static factory method is a static method that returns an instance of the class

```java
public class Point2 {
	private double x;
	private double y;

	public Point2(double x, double y) {
		this.x = x;
		this.y = y;
	}

	//static factory method
	public static Point2 polar(double r, double theta) {
		double x = r * Math.cos(theta);  
		double y = r * Math.sin(theta);  
		return new Point2(x, y);
	}
}
```