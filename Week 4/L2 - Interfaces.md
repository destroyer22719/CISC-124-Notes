- Interfaces are a specification, but not an implentation of an APi
- Interfaces say what methods and what they promise to do, but doesn't define how they are implemented
- A class that implements the interface must provide an implementation of every method in the interface
- An interface is a reference type
![[Pasted image 20230313164842.png]]
### Example:
```java
// interface
interface Animal {
  public void animalSound();
  public void run();
}

class Pig implements Animal {
	//...
}
```