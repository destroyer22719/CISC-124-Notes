An enumerated type (or enum) is a type whose values consist of a fixed set of constants

### Old way of doing enums
```java
public static final int SUNDAY = 0;  
public static final int MONDAY = 1;  
public static final int TUESDAY = 2;
```

The problem with using ints to represent enums is that any integer can work and there is no type safety.

For enums like this it is common to use strings instead of ints
```java
public static final String SUNDAY = "SUNDAY";  
public static final String MONDAY = "MONDAY";  
public static final String TUESDAY = "TUESDAY"
```
It's not much better because there is still no real type safety.

### Java Enums
- Java 1.5 finally added an enum type
- Enums can have fields and methods and can implement interfaces

```java
public enum Day {
	SUNDAY,  
	MONDAY,  
	TUESDAY,  
	WEDNESDAY,  
	THURSDAY,  
	FRIDAY,  
	SATURDAY;
}
```
Examples of using the `Day` enum:
```java
Day t = Day.THURSDAY;

System.out.println(d); //Thursday
```

### Enums can have fields
```java
public enum Month {  
	JANUARY(31), //initializes the Month constructor
	FEBRUARY(28),  
	MARCH(31),  
	APRIL(30),  
	MAY(31),  
	JUNE(30),  
	JULY(31),  
	AUGUST(31),  
	SEPTEMBER(30),  
	OCTOBER(31),  
	NOVEMBER(30),  
	DECEMBER(31);  
	
	private final int days;

	Month(int days) {  
	this.days = days;  
	}
	
	public int days(int year) {  
		if (this != FEBRUARY) {  
		return this.days;  
		}  
		
		if (year % 400 == 0 ||  
		(year % 4 == 0 && year % 100 != 0)) {  
		return this.days + 1;  
		} 
		 
		return this.days;  
	}
}
```

### The values method
Returns an array of the enum consts in the order they were declared

```java
System.out.println(Arrays.toString(Month.values()));
// [JANUARY, FEBRUARY, MARCH, APRIL, MAY, JUNE, JULY, AUGUST, SEPTEMBER, OCTOBER, NOVEMBER, DECEMBER]
System.out.println(Arrays.toString(Month.values()));  
for (Month m : Month.values()) {  
	System.out.println(m + " : " + m.days(2018));  
}
```
