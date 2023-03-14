Inheritance is a class relationship between 2 classes where one is derived from another class

![[Pasted image 20230314005427.png]]
- a subclass inherits all of the non-private fields and methods (but **not** constructors) from its superclass
- The `java.lang.Object` is the only class with no superclass and it's the class from which all other classes are descended from
- To inherit a class use the `extends` keyword
- We **must** use `super()` at the beginning to initialize the superclass' constructor