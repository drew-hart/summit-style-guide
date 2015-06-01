# Code Review Best Practices Guide
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

## Review first, push second
Before submitting my code, I will often do a git add for the affected files or directories and then run a `git diff --staged` to examine the changes I have not yet committed. Usually I’m looking for things like:

* Did I leave a comment or TODO in?
* Does the function name make sense?
* Does the variable name make sense?
* Should the function be split up?
* Do the comments makes sense?
* Do I have commented code included?

Make sure that you give your own code a passing grade before pushing it to the repository. Also, don't subject other people to finding easy mistakes that you can fix on your own. Doing this will let others who review your code focus on providing you with creative ideas on how to improve the code, instead of style.

## The Code Review
**Ask questions**

* How does this method work?
* If something the function relies on changes, what happens?
* Should the function be more modular or should it be specific to the application? 

**Compliment / reinforce good practices**
One of the most important parts of the code review is to reward developers for their effort and to comment on their growth. Few things feel better than getting praise from a peer. Offer as many positive comments as possible. There's no such thing as too much.

**In person or share via comments?**
This depends on the situation, but if there are big changes that are taking place, then it may be easier to discuss it in person rather than sharing comments or insights via in-line comments in the code. Another situation where it may make sense to discuss in person, is if there is a lot of comments going back and forth. It simply may be easier to have a discusison in these cases as well. 

**Explain reasoning**
Just telling someone to do something, can't really hamper the learning curve. Instead, it can be better to ask the originating developer if there’s a better alternative to writing the code. The reviewing developer would do well by justifying why they think the code is worth fixing as well, so that the original developer has some context on what you're thikning. What you really want to avoid is the perception that the beneficial changes you're suggesting do not seem nit-picky. The additoinal context or explanation will go a long way to getting other developers to buy in on your suggestions and changes. And lastly, keep the commentary about the code and not the developer.

**Suggest importance of fixes**
Not all suggestions are created equal. Clarify which items are important to fix before considering the code review done. This is immensly useful for both  the reviewer and the reviewee. It makes the results of a review clear and actionable.


