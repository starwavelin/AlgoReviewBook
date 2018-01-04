# Templates for Reversing word/array


### reverse function, char[] example
```java 
public void reverse(char[] s, int start, int end) {
	while (start < end) {
		char tmp = s[start];
		s[start++] = s[end];
		s[end--] = tmp;
	}
}
```