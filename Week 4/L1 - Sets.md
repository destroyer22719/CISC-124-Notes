#sets
- Sets are a collection with no duplicates
- Java allows devs to use different types of sets, the two main ones are:
	- [HashSets](https://docs.oracle.com/javase/8/docs/api/java/util/HashSet.html) - Most similar to Python sets
	- [TreeSet](https://docs.oracle.com/javase/8/docs/api/java/util/TreeSet.html) - A set that sorts elements

### Creating a set of strings
```java

HashSet<String> t = new HashSet<String>();
//We can omit the type on the constructor call after Java 7
HashSet<String> t = new HashSet<>();
```
**Note:**
Like `ArrayLists`, for generic type we can't use the primitive type, we must use the wrapper
```java
//Incorrect
HashSet<int>
//Correct
HashSet<Integer>
```
### Methods for sets
**Creating an empty Set**
```java

//Creating an empty Set
HashSet<String> t = new HashSet<>();

t.isEmpty();
int size = t.size();
t.add(val);
t.contains(val);
t.remove(val);

//copy a set
HashSet<String> newSet = new HashSet<>(t);
```

### HashSets
- Very fast, `add`, `remove`, `contains` have O(1) complexity
- Makes no gaurantees as to the iteration order
### TreeSet
- Same thing as `HashSet` but slower, O(logn) complexity
- Elements are sorted
- Elements must have a type that implements `Comparable` or the set must be initialized with a `Comparator` objefct
### LinkedHashSet
- Same everything for `HashSet` but slightly slower
- Iteration order is guaranteed to be identical to the order in which elements were added to the set
- More memory than `HashSet`


### Iterating over a set
Sets do not support indexing, thus you must use a `for-each` loop

```java
for (String s: t) {
//...
}
```
### Using sets to remove duplicates
```java
ArrayList<String> csAcc = ArrayList<>()

HashSet<String> uniqueAcct = new HashSet<>(csAcct);
// We can use TreeSet if we want a sorted set of accounts
// We can use LinkedHashSet if we want to maintain the same order as the input list
```
### Using sets to find the duplicated values
```java
HashSet<String> uniqueAcct = new HashSet<String>();  
HashSet<String> duplicateAcct = new HashSet<String>();  
for (String acct : csAcct) {  
	if (!uniqueAcct.add(acct)) {  
		duplicateAcct.add(acct);  
	}  
}
```
### Set Operations
```java
HashSet<String> s1 = new HashSet<String>(); //a, b c
HashSet<String> s2 = new HashSet<String>(); //c, d, e

//unions
HashSet<String> union = new HashSet<string>(s1);
union.addAll(s2); // a, b, c, d, e
//intersections
HashSet<String> interSect = new HashSet<string>(s1);
interSect.retainAll(s2); // c
//difference
HashSet<String> diff = new HashSet<string>(s1);
diff.retainAll(s2); //a, b
```