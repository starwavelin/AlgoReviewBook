# ArrayList and ArrayDeque

### ArrayList

#### Frequently Used Methods
add(object)  
add(index, object)  
get(index)   
set(index, object)  
remove(index)  
size()  

#### Resize
When starting, an arrayList has size = 0 and elementData.length = 0; then when you add one object into this arrayList, size = 1 and elementData.length = 10. Then when size = 10, arrayList will grow to the 1.5 times of the original size.  
Why 1.5x ?
Answer: Assume we don't know what the latter size should be, and we denote the latter size to be y. And we start the arrayList with size 1. Then we have  
1 y y^2  [when we reached y^2, we have GC collected 1 and y, so when continuous increasing needed, we can fill in the holes occurred in the front and will have ```1 + y = y^3 ==> y = 1.32```].  
Then, ```1 + y + ... + y^(n-2) = y^n``` gives us y = 1.618  
Cuz 1.618 is a float number, 1.5 is a better option.  
Wait? Isn't 1.5 also a float number? Let's see how we can get 1.5 in code:  
(1) len = len * 1.5  
(2) len = len * 3 / 2  
(3) len = len + len >> 1  
Option 1 will give us a double result, Option 2, times 3 may cause integer overflow. So, Option 3 is the best alternative in which ```len >> 1``` gives us a half of original length and make final result 1.5 times the original in int value. This is also why we don't use 1.618 cuz we cannot use bit operation to form 1.618.  

### ArrayDeque

