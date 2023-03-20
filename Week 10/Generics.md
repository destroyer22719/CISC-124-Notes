Suppose we created an `IntStack` class and we want to make one for `String`  type. We can make a seperate `StringStack` class but all we do is just change the type `int` to `String`. There is a convenient way to do it for all types for our stack using generics.

We can use:
- `Stack<Integer>` instead of `IntegerStack`
- `Stack<String>` instead of `StringStack`

