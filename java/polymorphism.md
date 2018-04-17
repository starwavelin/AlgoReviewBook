# Polymorphism

Method overriding is one of the ways in which Java supports Runtime Polymorphism.   
Dynamic method dispatch is the mechanism by which a call to an overridden method is resolved at run time, not in compile time.  

* When an overridden method is called through a superclass reference (ie. Shape), Java determines which version(superclass/subclasses) of that method is to be executed based upon the type of the object being referred (ie. Shape or Rectangle) to at the time the call occurs.  
* Upcasting means: A superclass reference variable can refer to a subclass object.
``` SuperClass obj = new Subclass(); ```  

