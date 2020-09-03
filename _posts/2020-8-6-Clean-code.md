---
layout: post
title: Clean Code by Robert C Martin!
---

![_config.yml]({{ site.baseurl }}/images/s2bgjgyu60e1yltnhoa3.webp)

Hello World,

Recently, I read the book Clean Code by Robert C Martin and I loved it! This book consists of great concepts with a lot of examples that clear your every doubt. We learn to write good code, build, optimize, and whatnot. In an early stage of career sometimes we miss (Or maybe you don't even know) a lot of important points which are helpful and imperative. This book opens you to the new level of programming practices that leads you to new doors.

Being a programmer, I would love to point out some of the best practices that I feel worth sharing:

##### 1. Meaningful Names
##### 2. Do one thing
##### 3. Comments
##### 4. Formatting
##### 5. Error Handling

<br>

### 1. Meaningful Names

  We use names for almost everything, for software, for functions, for classes, etc. Names being an integral part of software must be meaningful and reveal intention. Intention regarding what role will it play in the process, like if we use 'Date' we know that it is depicting date, on the other hand, if we used' we won't be able to understand what this variable intends to do. What we usually do is just name variables anything, mostly just alphabets that are easy to write. Writing good names takes some time but it eases the readability of the code, Not only will others be happier to see it but also you.
  
  Is just writing good names enough? Almost. But keeping them Meaningful is best. Like I have mentioned regarding 'Date' in the earlier paragraph we know it is a date but we are unaware regarding what this Date wants to reveal. So, using 'Date-of_birth' or 'start-date' would have been a better choice. 
  
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
  
  I wrote a simple example of copying some bits from source to destination, As Example 1.1 pictures the code is fine and working but it is taking some time to understand while from example 1.2 we saw as soon as you read the function name you understand what we're trying to accomplish in this function and the story becomes much clearer.
  
  Choosing good names surely takes some time but it is worth it.

<br>

### 2. Do one thing
  
  Think Small! One thing that a function should be, is that it should be as small as it could. How short it should be? I read a story in this book which I would certainly love to share. 
  
  <br>
  
  ***In the eighties we used to say that a function should be no bigger than a screen-full. Of course we said that at a time when VT100 screens were 24 lines by 80 columns, and our editors used 4 lines for administrative purposes. Nowadays with a cranked-down font and a nice big monitor, you can fit 150 characters on a line and a 100 lines or more on a screen. Lines should not be 150 characters long. Functions should not be 100 lines long. Functions should hardly ever be 20 lines long.***
  
  <br>
   
   When we write a function we want it to handle all our problems. Most of the time we try to complete our task in a single function. It might complete the work but doesn't ease it for future roles. So, to handle this problem we should try to design it in a way that it is easy to reuse, change, or add more elements. The solution to the problem is to divide your problem as much as you could. If a function is performing addition as well as subtraction then split it. If a function is checking as well as iterating, break it. Try to segment it.

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
Here, in the above example 2.1 and 2.2 we can see how breaking the copy_source_data into another function made this whole code a lot easier to understand and read. Each function is doing just one thing and working what they are assigned for. 
<br>

   ***"Functions should do one thing and that one thing well"***

<br>            
<h3>3. Comments</h3>
  
  The ratio of a code written to the reading is 1-to-10. we surely need to write a code that is more readable and understandable to our fellow developers for their ease as well as ours. Therefore, comments play a vital role in accomplishing this task and will help in decreasing the complexity of the code. If we write meaningful Function name half of our task is resolved as we would not need a comment to explain the use of that function.
  See whether you can understand that in the next Example:

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

Example 2.2 is quite clear as we can see that we are copying data to function name just says copy source data. The comments clear out the little bit of confusion that could have arrived due to source1 and source2 as both are the source and the comment clear out the tension.

<br>
<h3>4. Formatting</h3>
  
  The neatness of a code matter as much as the working code. It enhances the readability of the code. Formatted code pleases the eye and motivates a reader to keep going on with it. The more the code is formatted more it can communicate. To have a Formatted code we must create some simple rules so that we do not have to come to it again and again. Being in a team you can decide some simple rules and work with that. Horizontal and Vertical are the two types of formatting. Combining both of them build great empire.<br> 
  
  Vertical Formatting deals with the line of code that a function should consist of. In older times developers used to keep the length of a function by half of the screen size. That's the other point that the size of the screen used to be small earlier.
  Example 2.1 and 2.2 are best examples for Vertical Formatting<br>
  
  Horizontal Formatting deals with the indentation of the code. An indented code is a best-expressed language. It defines the systematic flow of the code. It is an important part of python.

I think an example would be better here for Horizontal formatting:

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

  I know indentation in Python is an important part. Whereas there have been libraries that allow us to use curly braces in python. On the other hand, here I would like to bring your attention more towards the indentation. From Example 4.1 and 4.2 you can analyze the importance of horizontal indentation. The code in 4.1 will fail to throw an indentation error. The code in Example 4.2 is much more cleaner and easy to read than in Example 4.1.

<br>
<h3>5. Error Handling</h3>
  
  Error handling is an integral part of a code. Things may go wrong, devices fail and many abnormal things might can take place. Therefore, even if any error occurs it should be handled gracefully. The code must be smooth. It comes with an understanding of knowing where your code can break and we need to make sure that even if an error occurs our code does it's work.

Example - 5.1

 ```
 def divide(n1, n2):
  try:
    result = n1/n2
  except ZeroDivisionError:
    print("Oops! Divided by Zero Error occurred.")
  return result
 ```
<br>  
***Writing a clean program is not an easy task it needs consistency and effort. Earlier it might slow down your pace but it is best for the long run. The more you do the more you learn. Keep Learning!***
