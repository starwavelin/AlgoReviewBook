# Marker Interface

### What is a marker interface?
Marker interface is an empty interface, with no fields or methods. Example of marker interfaces are Serializable, Cloneable, and Remote interface.  

*Then why do we need such empty(marker) interfaces?*  
Per this stackoverflow top-voted [answer](https://stackoverflow.com/questions/25850328/marker-interfaces-in-java), any class implementing a marker interface will have **Java class library** treats it specially. For example, when a class implements Cloneable, that means now the ```clone()``` method in the Object class can be invoked, and we usually override this ```clone()``` method in this implementing class. Otherwise, purely invoke ```clone()``` method without implementing will cause ```CloneNotSupportedException```.  

Top voted answer also alluded that Annotations may be better than marker interfaces. Annotations let you achieve the same purpose of conveying metadata about the class to its consumers without creating a separate type for it. Annotations are more powerful, too, letting programmers pass more sophisticated information to classes that "consume" it. Annotations may be viewed as Marker Interface 2.0.  

### Example of Marker Interface

1. Cloneable  
See the discussion above  

2. Serializable  
Serializable interface is present in ```java.io``` package. It is used to make an object eligible for **saving its state into a file**. This is called Serialization.
Classes that do not implement this interface will not have any of their state serialized or deserialized. All subtypes of a serializable class are themselves serializable.

3. Remote interface  
Remote interface is present in java.rmi package. A remote object is an object which is stored at one machine and accessed from another machine.  
So, to make an object a remote object, we need to flag it with Remote interface. Here, Remote interface serves to identify interfaces whose methods may be invoked from a non-local virtual machine. Any object that is a remote object must directly or indirectly implement this interface.  
RMI (Remote Method Invocation) provides some convenience classes that remote object implementations can extend which facilitate remote object creation.
