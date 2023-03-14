What happens when we create a value class that extends `Object` but we don't override `equals()`?

```java
Obj a = new Obj("1");
a.equals(a); //true

Obj b = p;
b.equals(a); //true

Obj c = new Obj("1");
c.equals(a); //false
```
`Object.equals`  only checks if the references are the same

### Conditions for when we overriding the `equals()` method
- An instance is always equal to iteself
	```java
	this == obj;
```
- An instance is never equal to null
- Instances of the same type can be equal
	```java
	if (this.getClass() != obj.getClass()) {
	return false;
	}
```
- Instances with the same state are equal
	- if the field is a primitive type other than `float` or `double` use `==`
	- if the field type is `float` use `Float.floatToIntBits`, for doubles use `Double.doubleToLongBits`
		Why?
		
		`Double.Nan == Double.Nan`  gives false but not for `Double.doubleToLongBits`
		Same for `-0.0==0.0` which would be true but false if we use `Double.doubleToLongBits`
		
	- if the field is an array use `Arrays.equals()`
	- If the field is a reference type use `equals` but beware of fields that may be null




### Equals Contract
- Reflective
	`x.equals(x)` is true
- Symmetry
	- `x.equals(y)` $\iff$ `y.equals(x)`  
- Transitivity
	if
	`x.equals(y)` is true
	and
	`y.equals(z)` is true
	then
	`x.equals(z)` must be true
- Consistency
	Repeatedly comparing two objects yield the same result assuming the state of the objects do not change
- Non-nullity
	`x.equals(null)` is always falls and doesn't throw an exception
	
