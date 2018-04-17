# Abstraction

### Real life example
Consider a real-life example of a man driving a car. The man only knows that pressing the accelerators will increase the speed of car or applying brakes will stop the car but he does not know about how on pressing the accelerator the speed is actually increasing, he does not know about the inner mechanism of the car or the implementation of accelerator, brakes etc in the car. This is what abstraction is.

### In Java
Abstraction is achieved by interfaces and abstract classes.  
We can achieve 100% abstraction using [interfaces](interface.md).

### Abstract class and Abstract method
- An abstract class is a class that is declared with abstract keyword.
- An abstract method is a method that is declared without an implementation.
- An abstract class may or may not have all abstract methods. Some of them can be concrete methods
- A method defined abstract must always be redefined in the subclass, thus making overriding mandatory OR either make subclass itself abstract.
- An abstract doesn't necessarily to have an abstract method. Abstract class makes itself no instance!
- But, any class that contains one or more abstract methods must also be declared with abstract keyword (abstract class).
- An abstract class can have parametrized constructors and default constructor is always present in an abstract class.

### Encapsulation vs Data Abstraction
- Encapsulation is data hiding(information hiding) while Abstraction is detail hiding(implementation hiding).
- While encapsulation groups together data and methods that act upon the data, data abstraction deals with exposing the interface to the user and hiding the details of implementation.
