# Inheritance

In practice, inheritance and polymorphism are used together in java to achieve fast performance and readability of code.

### What can we do in a subclass?
* We can write a new instance method in the subclass that has the same signature as the one in the superclass, thus overriding it
* We can write a new static method in the subclass that has the same signature as the one in the superclass, thus hiding it.
* We can write a subclass constructor that invokes the constructor of the superclass, either implicitly or by using the keyword super.
* others

### Overriding
* Overriding is a feature that allows a subclass or child class to provide a specific implementation of a method that is already provided by one of its super-classes.  
* Method overriding is one of the way by which java achieve Run Time Polymorphism.The version of a method that is executed will be determined by the object that is used to invoke it.  
* Private, final methods cannot be overridden.  
* Static method, is not called overridden but called hiding in subclass.  
* You must override an abstract method in the interfact/abstract class in the subclass, otherwise compile error (or you can declare this method abstract again and let sub-sub-class to override it)
