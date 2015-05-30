##  Style
------
### **Function names**

Naming methods is a hard problem for developers. If a method is named get_time_of_day_routing and it is asking for input form a caller, then that’s an inaccurate method name. And probably a misleading function name.

### **Variable names**
`foo` or `bar` are not useful names for data structures. `e` is equally not as useful when compared to `exception` . Be as verbose as you need to be. Expressive variable names make it easier to understand code when we have to revisit it later.

### **Functionl length**
The rule of thumb is that if the function is over 50 lines, then it should likely be broken up into smaller pieces.

### **Class length** 
The rule of thumb for classes, is that they should be under 300 lines in total. Ideally, they should be less than 100 lines. If classes are over 100 lines or approaching, 300 then it's likely they can be broken out into separate objects.

### **File length** 
The rule of thumb for file length should be no more than 1,000 lines per file. Anything above 1,000 lines is a good sign that the file should be broken up into smaller, more focused files. As the file size goes up, discoverability goes down.

### **Comments**
For complex functions or methods, provide some explanation of what each argument does if it is not obvious. Also if there is any specific logic inside the function or method that's worth noting, then a small descripton may be helpful when revisiting the code at a later time.

### **Commented code** 
All commented code should be removed from production code. If there is important information that should be included, convert the commented code into a comment

### **Readability**
Is  the code easy to understand? Have you had someone who has not been working on that code review the information and can they understand it? If you have to pause frequently when you're reviewing in order to decipher the code, then there may be an opportunity to improve on it.

## Unit Testing
### Creating unit tests
When creating tests, how thoughtful is the testing? You should include testing for all paths within an applications. For example, if a call flow has several routes, are you testing all of them. Are you testing for failure conditions in the call flow? Finally, are your tests easy to read, so that when the code should need to be updated and tests fail, then you can understand where the failure is to learn more.



