---
layout: post
title: Clean Code by Robert C Martin!
---

![_config.yml]({{ site.baseurl }}/images/giphy.gif)

Hello World,

  Recently, I read a book Clean Code by Robert C Martin and I loved it. This books consists of great concepts with a lot many examples which clear out your any doubt. We  learn to write good code, build, optimize and what not. In an early stage of career sometimes we miss( Or maybe you don't even know) a lot important points which are really helpful and important. This book open you to the new level of programming practices that leads to new doors.

  I would love to share some of the best practices that I felt are really important being a programmer:

##### 1. Meaningful Names
##### 2. Do one thing
##### 3. Comments
##### 4. Formatting
##### 5. Error Handling

<br>

### 1. Meaningful Names
  
  We use names for almost everything, for softwares, for functions, for classes, etc. Names being an integral part of a software must be meaningful and reveal intention. Intention regarding what role will it play in the process like if we use 'Date' we know that it is depicting date on the other hand if we use 'd' we won't be able to understand what this variable intends to do. What we usaually do is just name variables anything, mostly just alphabets that are easy to write. Writing good names takes some time but it eases the readablity of the code, Not only will others be happier to see it but also you.
  
  Is just writting good names enough? Almost but keeping them Meaningful is best like I have mentioned regarding 'Date' in the earlier para we know it is date but we are unaware regarding what this Date wanna reveal. So, using 'Date-of_birth' or 'start-date' would have been a better choice. 
  
  *Follow me:*<br>

Example - 1.1

```
def func(a1, a2):
  for i in range(len(a1)):
    a2[i] = a1[i];
```

Example - 1.2

```
def copy_source_to_destination(source, destination):
    for bits in range(len(source)):
      destination[bits] = source[bits]

```

  I wrote a simple example of copying some bits from source to destination. from Example 1.1 you can see that the code is fine and working but it is taking some time to be understood while from example 1.2 as soon as you read the function name you understand what we are accomplishing in this function and the story become much more clearer.
  
  Choosing good names surely takes some time but it is worth it.

<br>

### 2. Do one thing
  
  Think Small! The one thing that a function should be is as small as it could. How short it should be? I read a story in this book which I would certainly love to share. 
  
  <br>
  
                          In the eighties we used to say that a function should be no 
                          bigger than a screen-full. Of course we said that at a time
                          when VT100 screens were 24 lines by 80 columns, and our editors
                          used 4 lines for administrative purposes. Nowadays with a
                          cranked-down font and a nice big monitor, you can fit 150
                          characters on a line and a 100 lines or more on a screen. Lines
                          should not be 150 characters long. Functions should not be 100
                          lines long. Functions should hardly ever be 20 lines long
  
  <br>
  
   When we write a functions we want it to handle all our problems. Most of the time we try to complete our task in a single function. When we write a code we try to design it in a way that it is easy to reuse, change or add more elements. It might complete the work but doesn't ease it for the future roles. Whenever additions will be asked the code will need rework. The solution to problem is divide your problem as much as toy could. I a function is performing addition as well as substraction than split it. If a function is checking as well as iterating break it. Break it as much as you can.

Let's get this more clear with an example:
 
 Example - 2.1
 
 ```
 def copy_source_data(source1, source2):
  if source1:
    for bits in range(len(source1)):
      source2[bits] = source1[bits]
  else:
    for bits in range(len(source2)):
      source1[bits] = source2[bits]
 ```
 
 Example - 2.2
 
 ```
 def copy_source_data(source1, source2):
    for bits in range(len(source)):
      source2[bits] = source1[bits]
      
 def check_data_containing_source(source1, source2):
    if source1:
      copy_source_data(source1, source2)
    else:
      copy_source_data(source2, source1)
 ```
<br>
Here in the above example 2.1 and 2.2 we can see how breaking the copy_one_source_to_another into another function made this whole code a lot easier to understand and read. Each function is doing just one thing and working what they are assigned for. 
<br>
            
                            "Functions should do one thing and that one thing well"
<br>            
<h3>3. Comments</h3>
  
  As I mentioned the ratio of a code written to the code read is 1-to-10. we surely need to code to be much more readable and understandable to our fellow developers for their ease as well as ours. Comments helps us most to accomplish this task. Write details about the code which will help in decreasing the complexity of the code. If we write meaningful Function name half of our task has been already solved as we would not need a comment to explain the use of that function.
  See wheather you can understand that in next Example:

 Example - 3.1
 
 ```
 # Copy data from one source to another
 def copy_source_data(source1, source2):
    for bits in range(len(source)):
      source2[bits] = source1[bits]
      
 def check_data_containing_source(source1, source2):
    if source1:
      copy_source_data(source1, source2)
    else:
      copy_source_data(source2, source1)
 ```

Example 2.2 is quite clear we can see that we are copying data te function name just says copy source data. The comments clear out the little bit of confusion that could have arrived due to source1 and source2 as both are source and the comment clear out the tension.

<br>
<h3>4. Formatting</h3>
  
  Neatness of a code matter as much as a working code. It enhances the readablity of the code. Formatted code eases the eye and motivates a reader to keep going with the code. The more the code is formatted the more it can communicate. To have a Formatted code we must create some simple rules so, that we do not have to come at it again and again. Being in a team you can decide some simple rules and work with that. Horizontal and Vertical are the two types of formatting. Combining both of tem together buids great empires.<br> 
  
  Vertical Formatting deals with the line of code that a function should consists of. In older times developers used to keep the length of a function by half of the screen size. That's the other point that the screen used to be small in size earlier.
  Example 2.1 and 2.2 are best examples for Vertical Formatting<br>
  
  Horizontal Formatting deals with indentation of the code. An indented code is the best expressed language. It defines the systematic flow of the code. It is an important part of python.

I think an example would be better here:

Example - 4.1

```
 def copy_one_source_to_another(source1, source2):
 for bits in range(len(source)):
 source2[bits] = source1[bits]
      
 def check_data_containing_source(source1, source2):
 if source1:
 copy_one_source_to_another(source1, source2)
 else:
 copy_one_source_to_another(source2, source1)
```

Example - 4.2

```
 def copy_one_source_to_another(source1, source2):
    for bits in range(len(source)):
      source2[bits] = source1[bits]
      
 def check_data_containing_source(source1, source2):
    if source1:
      copy_one_source_to_another(source1, source2)
    else:
      copy_one_source_to_another(source2, source1)
```

I know indentation in Python is an integral part. Whereas there have been libraries which allows us to use curly braces in python. On the other hand here I would like to bring your attention more towards the indentation. From Example 4.1 and 4.2 you can analyse the importance of horizontal indentation. The code in 4.1 will fail throwing an indentation error. The code in Example 4.2 is much more cleaner and easy to read than in Example 4.1.

<br>
<h3>5. Error Handling</h3>
  
  Error handling is one of the other part of a code. Things may go wrong, devices fail and there are many abnormal things that can happen. It is important for smooth working of a code, even if any error occur it should be handled gracefully. It comes with a understanding of knowing where your code can break and we need to make sure that even if error occurs our code does it's work.

Example - 5.1

 ```
 def divide(n1, n2):
  try:
    result = n1/n2
  except ZeroDivisionError:
    print("Oops! Divided by Zero Error occurred.")
  return result
 ```
  
  
