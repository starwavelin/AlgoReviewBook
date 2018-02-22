# IO in Java

### Read From File
口诀：  
filename -> File -> FileReader -> BufferedReader  
代码： 
```java 
BufferedReader br = new BufferedReader(new FileReader(new File(filename)));```

When doing actual reading  
We usually use a variable ```String line``` to store the line read from ```br.readLine()``` because once ```br.readLine()``` is called, a line is read and we don't want to invoke this statement multiple times.  

Example:  
```java
String line;
while ((line = br.readLine()) != null) {
	String[] strs = line.split(" ");
	// Further logic
}
```


### Output To File
口诀：  
outputFilename -> File -> FileOutputStream -> OutputStreamWriter -> BufferedWriter  
代码： 
```java 
BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(new FileOutputStream(new File(outputFilename))))```


### End
```java
br.close();
bw.close();
```
