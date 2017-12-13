# Templates of String problems


### Longest Substring
```java 
public int lengthOfLongestSubstring(String s) { /* could have another parameter for number of distince chars */
	// 1. Defensive Check over s
	
	// 2. Setup an array map of 256
		// Think (1): initialize the cells with 0 or -1?
		// (2): what will this map store, key - char, value - occurrence of a char, or the last index of the occurrence of this char?
	
	// 3. Initilize left pointer, maxLen, (and count - the number of distince chars)
	for (int r = 0; r < s.length(); r++) {
		/* In what circumstances you need to move l? */


		maxLen = max(maxLen, r - l + 1);
	}
	return maxLen;
}
```

