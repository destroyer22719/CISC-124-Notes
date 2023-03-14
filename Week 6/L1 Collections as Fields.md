Often we want to implement a class that has a collection as a field (variable inside a class)

Collections holds references to instances, but not the instances itself
![[Pasted image 20230314003346.png]]

- If `X` owns its collection but not the objects in the collection then the copy constructor can perform a shallow copy
```java
//performing a shallow copy of a list named dates
ArrayList<Date> shallow = new ArrayList<Date>(dates);
```
- If  `X` owns its collection and the objects in the collection then the copy constructor must perform a deep copy of the collection
```java
ArrayList<Date> deep = new ArrayList<Date>();

for (Date d : dates) {
	deep.add(new Date(d.getTime()));
}
```
