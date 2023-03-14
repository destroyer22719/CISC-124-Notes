- Java maps provide similar functionality to Python dictionaries (or JavaScript objects)

### Main Kinds of Maps
[HashMap](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html)
[TreeMap](https://docs.oracle.com/javase/8/docs/api/java/util/TreeMap.html) - A dictionary that sorts its keys
[LinkedHashMap](https://docs.oracle.com/javase/8/docs/api/java/util/LinkedHashMap.html)- Preserves order based on when the values were added

They all have the methods `get`, `put`, `containsKey`
`HashMap`, and `LinkedHashmap` have O(1) time complexity for the operations whereas `TreeMap` is in O(logn) complexity

### Examples of Maps
```java
TreeMap<String, String> capitals = new TreeMap<String, String>();  
capitals.put("Ontario", "Toronto");  
capitals.put("Quebec", "Quebec City");  
capitals.put("Nova Scotia", "Halifax");  
capitals.put("New Brunswick", "Fredericton");  
capitals.put("Manitoba", "Winnipeg");  
capitals.put("British Columbia", "Victoria");  
capitals.put("Prince Edward Island", "Charlottetown");  
capitals.put("Saskatchewan", "Regina");  
capitals.put("Alberta", "Edmonton");  
capitals.put("Newfoundland and Labrador", "St. John\'s");

String bcCap = capitals.get("British Columbia");

//To get the all keys
Set<String> keys = capitals.keySet();

for (String k: keys) {
	System.out.println(k);
}

//To get all the values
Collection<String> values = capitals.values();

for (String value : values) {
	System.out.println(value);
}
```