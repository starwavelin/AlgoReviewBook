# Interface

### Default Method in Java 8
Java 8 introduces Default Methods that allows interfaces to have concrete method implementation.  
ie.  
```java
@FunctionalInterface
public interface Predicate<T> {
	boolean test(T t);

	default Predicate<T> and(Predicate<? super T> other) {
		Objects.requireNonNull(other);
		return (t) -> test(t) && other.test(t);
	}
}
```

#### Why Java 8 allows Default Methods?
Improve Code Reusability and Reduce Code Duplications  
ie. we already know ```Iterable``` <-- ```Collection``` <-- ```List```, and we want to add a new method called ```forEach()``` to apply to all of them    
In the past when we could not write default methods in interfaces, we need to write abstract method ```forEach()``` in Iterable, Collection, List, and write concreate method ```forEach()``` in each of the classes implementing ```List```. Oosh... Pain...  
Then for now we just need to write a default method ```forEach()``` in ```Iterable``` and auto apply to all sub-interfaces and all classes implementing these interfaces. 


#### Interface vs. Abstract Class
|               | Interface       | Abstract Class|
|---------------|-----------------| --------------|
| Method Types  | Allow abstract methods; concreate methods should have "default"; Java 8 allows static methods too.| Abstract and non-abstract methods |
| Variable Types| Variables are by default static and final | Can have final, non-final, static, non-static variables |
| Accessibility of Data Members | Members in interfaces are public by default | Members in an abstract class can be public, protected, default, and private. |
| Implementation| Interface cannot provide implementation of an abstract class| An abstract class can provide implementation of an interface|
| Inheritance   | An interface can extend another interface only | An abstract class can extend another Java class and implement multiple interfaces |


##### Some Q and A about the Interface and Abstract Class comparisons
1. Why are variables in an interface by default static and final?  
"static" is because Java interfaces cannot be instantiated in their own right; the value of the variable must be assigned in a static context in which no instance exists.  
"final" modifier is because the value assigned to the interface variable is a true constant that cannot be reassigned by program code.
