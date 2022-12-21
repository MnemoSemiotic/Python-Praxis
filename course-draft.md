# 000 - Introduction - What to expect from Python Praxis

## Goals:
* Accessible, Queer and "Leftist" series of courses in Data Analysis and Science
    * Why such a course is helpful or necessary
* Establish a culture where programming is a form of literacy, and is accessible to all who want to develop that literacy
* Scope of Python Praxis
* Big Picture

## Who am I
* 

## Why a "Leftist, Queer-inclusive" series of technical courses?
* Technical people are in positions of power, by way of decision and deferral to expertise
    * It's important that we build some relational ethics into the tech community, as currently it's very normitive, very white, and 
    * Decisions and analyses are infused with biases, and have major repurcussions and outcomes
        * [Sabelosethu Mhlambi: Decolonizing AI](https://www.youtube.com/watch?v=UqVwfuIuU2k&t)
            * Discusses racial bias in AI, and proposes a relational ethics
        * [William Isaac, DeepMind: Columbia Data Science Institue, Race + Data Science series](https://www.youtube.com/watch?v=fcJR6DIo3Mg)
* Technology is political (yeah everything is, actually)
* Technology has often been a haven for Queers, ND peopleo, etc., and I feel like we need to wrestle this back a bit from the tech bros and have safe space



## What is Python?
* General purpose and relatively easy to learn programming language
* Used in various domains
    * Data Science
    * Robotics
    * App building
    * etc
* Python is currently the most used language of Data Science
    * Extensive machine learning libraries
    * Generally supported on many types of platforms
    


## Programming is a creative endeavor
* If you have an idea and you know how to code within a given environment, you can actualize that idea
* There's a major issue of ableism within tech spaces, where intelligence is attributed when the real functional elements are familiarity and creativity.


## Why should you become literate in programming?
* So you can make stuff 
    * Games, art, music, generative text
* So you can analyze data
    * exs: Social Determinants of Health (SDoH), images, waveform signals, text
* So you can automate things you do over and over again
* So you can understand better the technology (and security involved) you are using
* Helps you to become a better problem-solver in a safe (sandboxed) way


## Making materials accessible
* There's a current exclusionary culture in tech, that glorifies what the culture sees as intelligence
* Programming, like any skill, is within reach by practice and application



## Scope of this course
* Covering Python from zero background through reasonable practical proficiency
    * At every step, we'll apply what we've just learned
    * Whenever possible, we'll use real-world examples (that maybe we even care about)
* There will be some probability and statistics
    * All concepts will be reasonably explained, with as little expectation of prior knowledge as possible
    * Probability and Stats are highly applicable to thinking about and writing code
* Specifically
    * Python basics, variables, data structures, and classes
    * Write a bunch of functions, that are often concerned with "counting", ranging from simple to fairly complex
    * Classes, class structure, and methods
    * Basics in Numpy and Pandas, with applications on images and data
        * these will be extended in their own courses, as well, so just enough to be dangerous 
    * A basic example of machine learning and how to think about this example more generally
    * Develop a simple application
* The general format will be looking at a problem, solving it, then explaining all the components of the solution. 


## Big Picture
* Intent is to include this course in a series, with further courses that explore 
    * Data Analysis 
    * Data Science 
    * Social Determinants of Health 
    * Natural Language Processing
    * Image and Signal Processing
    * Simple App / Gui development




## What does succeeding look like?
* Succeeding is relative to your goals, so take whatever you need, and let me know if you need something else, and I'll do my best to collab and make something with you
* I'll do my best to tie things into the real world, bc what I've seen and experience as "successful" learning, has been the result of meaningful application, not theory.
* Repetition and application definitely help in internalizing methodology of programming


## Resources
* The goal is to have each numbered lesson (000, 001, etc) have a video around 10-15 minutes in length
* Most code examples and some specific concepts will also have a short with just writing of that code
* The entirety of these lessons will be mapped out in this github repo 
    * including lesson scripts that will be uploaded as as video captions
* Most code examples will have a dedicated [repl.it](https://repl.it), for convenience
* I'll be streaming from time to time on these materials at [twitch.tv/MnemoSemiotic](https://MnemoSemiotic), and you can ask me questions there <3s



## In the Next Lesson...








-------------------------------------------------------------------------

#  - A Demo: Rolling the Dice

## Goals:
* This lesson is a proof of concept
* Give a simple introduction to programming
* Don't worry if you don't understand this lesson now, all concepts will be broken down in subsequent lessons
* Introduction to an immediately available Python environment using [repl.it](https://repl.it)


## This lesson is a proof of concept
* No expectation for you to understand everything in this lesson
* We'll cover everything in this lesson early in the subsequent lessons
* Feel free to skip to the next lesson if you find this one stressful



## Using [Repl.it](https://replit.com/) as a first coding environment.
* Create an account
* Create a repl.it for Python, and run: 

```python
print("Hello World")
```


## How to Program, simply stated
1. Think about the problem
2. Define what it means for the program to be working
3. Create a series of formal steps that lead to a repeatable, reusable operation


## Example: Making a Simple Dice Roller

Let's say you and your friends just acquired [Outward Bound](https://penflower-ink.itch.io/outward-bound), a TTRPG by [Penflower Ink](https://penflower-ink.itch.io/), and you realize that you don't have any dice. You know that you'll need to be rolling dice fairly often as you play, so you decide to figure out how to roll some dice using Python.

The first thing you'll try, is a basic `random` function that is provided by the Python Standard Library.

For your needs however, you will want to write something just a little more sophisticated, so that you are able to roll multiple dice with any number of sides.



### using `random.choice()`
* The quickest and dirtiest way to do this is by importing the `choice()` function from the `Random` module and calling it.
* `choice` is a function that is already defined


```python
from random import choice

# "roll" a 6-sided die
#    * choice is a function that chooses an item out of a collection (in this case, a list of numbers)
#    * print is a function, that prints something as text
print(choice([1,2,3,4,5,6]))

# choice can select from more than just a list of numbers
print(choice(['one', 'two', 'three', 'four', 'five', 'six']))
```
`example output:`
```
1
five
```



### writing a simple function that utilizes `random.choice()`
* You do not need to understand this right now, we'll cover functions in much more depth throughout the course

```python
# we import the choice function
from random import choice

# function definitions starts with the keyword def
def single_dice_roll(number_sides=6):
    # here we're going to create an empty list to hold numbers
    dice_sides = []

    # here we're going to fill that list with numbers from 1 up to the number_sides
    for side in range(1, number_sides+1):
        dice_sides.append(side)
        # print(dice_sides)
        # input()

    # here we're going to make a choice from that list of numbers
    selected_die_side = choice(dice_sides)

    # here we're going to return that single number that was chosen
    return selected_die_side


print(single_dice_roll(6))
print(single_dice_roll(36))
```
`example output:`
```
3
28
```


### Let's make our function a little cleaner
* 1. Use `range` directly to avoid the for-loop
* 2. Make the choice directly from the `range`
* 3. Return the operation directly


```python
from random import choice

# 1. Use `range` directly to avoid the for-loop
def single_dice_roll(number_sides=6):
    # here we're going to directly attach the desired range to dice_sides
    dice_sides = range(1, number_sides+1)

    # here we're going to make a choice from that list of numbers
    selected_die_side = choice(dice_sides)

    # here we're going to return that single number that was chosen
    return selected_die_side


print(single_dice_roll(6))
print(single_dice_roll(36))
```

`example output:`
```
6
15
```


```python
from random import choice
# 2. Make the choice directly from the `range`

# function definitions start with the keyword def
def single_dice_roll(number_sides=6):
    # here we're going to make a choice directly from the desired range
    selected_die_side = choice(range(1, number_sides+1))

    # here we're going to return that single number that was chosen
    return selected_die_side


print(single_dice_roll(6))
print(single_dice_roll(36))
```

`example output:`
```
6
10
```


```python
from random import choice

# 3. Return the operation directly

def single_dice_roll(number_sides=6):
    # here we're going to return that single number that was chosen
    return choice(range(1, number_sides+1))


print(single_dice_roll(6))
print(single_dice_roll(36))
```

`example output:`
```
4
33
```


### What if we want to roll multiple dice of the same number of sides?


```python
from random import choice

def multiple_dice_roll(number_dice=1, number_sides=6):
    sum_dice = 0

    for roll in range(number_dice):
        sum_dice += choice(range(1, number_sides+1))
    #     print(sum_dice)

    # print("----------------")
    return sum_dice

print(multiple_dice_roll(number_dice=5, number_sides=6))

```

`example output:`
```
21
```


### Let's make our multi dice roller a little cleaner
* by using a different form of loop, called a comprehension
* demonstrate that there are different syntaxes that do the same or similar things


```python
from random import choice

def multiple_dice_roll(number_dice=1, number_sides=6):
    return sum([choice(range(1, number_sides+1)) for roll in range(number_dice)])

print(multiple_dice_roll(number_dice=5, number_sides=6))
```

`example output:`
```
24
```


## Conclusion
* Programming can be simply defining a repeatable set of steps
* Here we created some simple dice rolling functions
    * Working code is more important than clean code.
    * in other words: It's ok to write code in a way you understand, and then refine it later if necessary


## In the Next Lesson...












---------------------------------------------------------------------------------


#  - First Steps: A Few Simple Programs

## Goals:
* Set up a REPL.it account to play with code
* Develop an initial understanding of functions
* Run a simple program


# What is REPL.it?
* a text editor with a built-in interpreter
    * text editor: for us, this is essentially a place to write code in a basic text format, without characters that Python won't recognize
    * interpreter: takes code and runs it, and can provide output to the programmer in real time


# Make an account on REPL.it
* go to repl.it and register an account, pretty straight forward


# Creating a new "repl"
* Click the "create" button, using the "+" button 
* Select "Python" and click Create Repl
    * you can accept the generated title or name the repl yourself


# Using the repl
* There are three sections
    * for now don't worry about the Files section, you will only be using the middle `main.py` section as well as the console
* You will write your code into `main.py` and click "Run" at the top when you want to see what your code does.



# A few simple programs
* A "program" for us right now, can be defined simply as a series of commands that we're keeping in a text file and running in an interpreter.


## Functions
* We're going to write code mostly within functions.
    * let's be a little hand-wavey about this
    * a **Function** can be thought of as a series of procedures that we can refer to using a name. 
        * A function can have values input into it, and it can **return** values
* These are very simple examples, to demonstrate what a function is


## Simple Program 1: put your name in a greeting

1. define your function

```python
def greet_with_name(your_name):
    return f'my name is {your_name}'
```

2. call your function

```python
print(greet_with_name("tov"))
```

* Notice here that our function named `greet_with_name` takes some input and puts that into a greeting, then returns the whole thing.
* We then `print` out what we made and it appears on the console



## Simple Program 2: add two numbers
* We could also just use the addition operator directly, as in `num_1 + num_2`

1. define your function

```python
def add_two_numbers(num_1, num_2):
    return num_1 + num_2
```

2. call your function

```python
print(add_two_numbers(5, 7))
print(add_two_numbers(9, 16))
print(add_two_numbers(3, 42))
print(add_two_numbers(99999999, 1))
```


## Simple Program 3: is this word in this sentence
* I'll be using a couple things we haven't learned yet, but Python is a very friendly language, and we'll learn about these things very soon.

1. define your function

```python
def word_in_sentence(word, sentence):
    if word in sentence:
        return f"YES! \"{word}\" is in \"{sentence}\""
    else:
        return f"No! \"{word}\" is NOT in \"{sentence}\""
```

2. call your function

```python
print(word_in_sentence("cat", "Is the cat inside?"))
print(word_in_sentence("cat", "Is the dog inside?"))
```

# Conclusion
* In this lesson we wrote a few very simple functions that returned results that we then printed to the console. These are just the beginning. We will often write code within functions, and then call or run those functions.
* There's a lot more to functions, and we'll dig into that as we go.
* Programming is a creative endeavor and it's important that you do more than just follow my lead and write the same code I do. Try to invent new things and see if Python does what you expect it to do.

## In the Next Lesson...

















-------------------------------------------------------------------------------


#  - Data Types: Numeric data types and operations

## Goals:
* Understand the concept of a data type
* Use the `type()` function to check data types
* Understand the numeric data types `int` and `float` and their basic operators
* Understand the modulo (`%`) and floor division (`//`) operators
* Casting between `int` and `float` data types
* Rounding numbers using `round()`

* ??Write functions that perform simple, repeatable mathematical operations


## What is a data type?
* a data type is simply the type of a given value
    * for example the number 4 is the `int` data type, which stands for "integer", which represents whole numbers 


## What are the numeric data types in Python?
* `int` represents whole numbers, like 1, 3, -54, 997, and so on
* `float` represents numbers that have decimal points, such as -4.2, 17845.0, etc
* `bool` represents only the values `True` or `False`
* `complex` represents values that are imaginary numbers (we won't go over this here, but it exists)

** We will cover only `int` and `float` in this lesson



### the `type()` function

* the `type()` function will tell you the type of a value
* run

```python
print(type(23))
```
`output`
```
<class 'int'>
```



### What is a `class`?
* This is a bigger question that we'll cover more later when we begin to write our own classes.
* For now, think of a class as a definition of a data type. 
    * The data types that are built in to Python are defined somewhere in the form of a class
    * That means that we can eventually start defining our own data types by writing classes




## Integers: `int`
* We can think of integers simply as whole numbers, positive or negative
* Any mathematical operation that we perform on whole numbers we can perform here.

### Adding (`+`), Subtracting (`-`), Multiplying (`*`), Dividing (`/`), Exponentiation (`**`)
* The order of operations follows PEMDAS
    * Parentheses, Exponents, Multiplication / Division, Addition / Subtraction


Adding
```python
print(3 + 8)
print(5 + 11)
print (7 + 9 + 3 + 2)
```

Subtracting
```python
print(23 - 5)
print(5 - 23)
print(5 - 23 + 7)
```
* note that addition and subtraction have equal precedence in the order of operations


Multiplying
```python
print(3 * 8)
print(5 * 20)
print(2 * 2 * 2 * 2 * 2 * 2 * 2 * 2)
```

Exponentiation
```python
print(2**8)
print(3**5)
print(144**(1/2)) # note that this operation will give a float value
```


### Division (`/`)
I separated division because the result of a division in Python will be a `float` value, and that's something that you'll want to remember

Numbers may divide evenly
```python
print(8 / 2)
```

Or may divide unevenly, in either case, resulting in a decimal value

```python
print(16 / 3)
```



## Special operators: Modulo (`%`) and Floor Division (`//`)
 
### Modulo (`%`) will give you the remainder of a division
* Wildly helpful, as it turns out
    * can check even-ness or odd-ness using `num % 2`
    * can check divisibility


```python
print(8 % 2)
print(16 % 3)
```

Notice that modulo in these two cases (with positive integers) will give a non-decimal result. However, if either of the numbers in the operation have a decimal value, then the result will have a decimal value. Basically, unless you know what you're doing applying modulo on decimal values, avoid doing so. Same for negative numbers. However, feel free to explore these ideas further, and I'll make a supplemental video on the topic at some point in the future.


Let's look at some further applications of modulo

```python
if num % 2 == 0: print('num is even')
if num % 2 == 1: print('num is odd')
if num % 4 == 0: print('num is divisible by 4')

print(21 % 4) # --> 1
print(20 % 4) # --> 0
print(5 % 20) # --> 5
print(6 % 20) # --> 6
```


#### Applying modulo to story problems
1. If 3 letter carriers must deliver the same exact number of letters, and there are 299 letters, how many letters will not be delivered? Write a Python expression that answers this question.
* TODO: put in solution that utilizes generalizable function

```python
print(299 % 3) # --> 2
```

2. If you have 5 bank tellers and 28 people waiting to be served, what is the least number of people who will not be served if it takes exactly 4 minutes to serve each person and the bank MUST close in 20 minutes? Write a Python expression that answers this question.
* TODO: put in solution that utilizes generalizable function

```python
print(28 - (20//4 * 5)) # --> 3
```




### Floor Division (`//`) will give you the result of division, rounded down to the nearest integer

```python
print(20 // 4)     # --> 5
print(100 // 102)  # --> 0
print(27 // 3)     # --> 9
print(72.6 // 3.3) # --> 21.0
print(72 // 3.3)   # --> 21.0
print(72.6 // 3)   # --> 24.0
```


## Order of Operations
* Keep in mind that Python will use our normal order of arithmetic operations, what we often call PEMDAS.
    * Parentheses, Exponents, Multiplication / Division, Addition / Subtraction

This means that these two operations, will be very different:

```python
print( 5 + 3 / 7 - 24 % 8**3 )

print( (5 + 3) / (7 - 24 % 8)**3 )
```

### **ERR on the side of using more parentheses!**
* you will often run into simple arithmetic bugs and using more parentheses, even when not necessary, can help prevent these from happening
* also, don't be afraid to use spaces to make your numeric operations easier to read




## Floats: `float`
* simply stated, floats are positive or negative numbers that have a decimal point.
* a `float` can be thought of as **continuous** while an `int` can be thought of as **discrete**, though in reality, all numbers are stored in a discrete way in a computer
    * Sometimes, we will consider two `float` values to be essentially equal if the difference is below some threshold.
    * **Underflow** occurs when trying to represent a number that is smaller than the computer can represent in binary.
        * Can lead to unexpected behavior

* All the same mathematical operations that are used for integers may be used for floats
    * `int` and `float` datatypes are encoded differently, but are able to share operators in Python



### Adding (`+`), Subtracting (`-`), Multiplying (`*`), Dividing (`/`), Exponentiation (`**`) with floats
* notice that the result of these basic mathematical operations will result in floats, even when the result could be a whole number
* likewise, a mathematical operation performed with a float and an integer will result in a `float`


```python
print(5.3 + 0.7)

print(6 - 0.3)

print(7 * 0.5)

print(6.0 / 3)
```


### Float Exponentiation
* as with the prior operations, if either of the numbers in the exponentiation is a float, the result will be a float


```python
print(5**3.0)
print(5.0**3)
```

#### Taking roots using exponentiation
* you can take roots using exponentiation, just be aware that the result will be a float, and there can be some **rounding error** in the result.
    * for example, if you take the cube root of 125, like so

```python
print(25 **(1/2)) # --> gives us 5.0

print(125**(1/3)) # --> gives us 4.9999...
```

you would expect to see a result of 5. However, you likely are seeing `4.999` with repeating 9's. 

Given how floats are stored in memory, they might not give an exact result.



### Float floor division 
* just as with other operations, but maybe surprisingly, using the floor division with two floats will result in a `float`.

```python
print(5.0 // 2) # --> 2.0

print(4.0 // 2) # --> 2.0
```

## Casting: using `int()` and `float()` to convert a number
* In Python programming, **casting** refers to taking one data type and converting it to another data type by using the function related to the target data type

### Let's see what happens when we use the `int()` and `float()` functions without putting anything into them

```python
print(int()) # --> 0
print(float()) # --> 0.0
```

Notice that these functions give an initial value of 0, in the `int` and `float` datatypes, respectively.

That said, if we feed a value into either of these functions, the function will convert that value into the target datatype:

```python
print(int(9.73541)) # --> 9

print(float(42)) # --> 42.0
```

Be aware that the `int()` function will not round the number. There is actually a `round()` function, in the event that you want to round the numeric value that you put into the function.

```python
print(round(9.73541))    # -->10
print(round(9.73541, 3)) # --> 9.735, where we've rounded to the 3rd decimal place 
```


## What is the result of calculating `1/10**1000000`? Explain this result
* TODO: fill this in
* `0.0`


## Examples translating mathematical statements to code
* print the result of multiplying by 7 the addition of 6 and 3
* print the product of 7 times 6, squared, with 23 subtracted from the result
* print the division of the result of 4 minus 2 times 2 into twenty


<br><br><br><br><br><br><br><br><br>

Solution:
* print the result of multiplying by 7 the addition of 6 and 3

```python
print(7 * (6 + 3)) # --> 63
```

* print the product of 7 times 6, squared, with 23 subtracted from the result

```python
print((7 * 6)**2 - 23)) # --> 1741
```

* print the division of the result of 4 minus 2 times 2 into twenty

```python
print((20 / (4 - 2 * 2)) # --> Will throw an error in this interpretation
# or
print((4 - 2) * (20 / 2)) # --> 20
```

# Conclusion
* In this lesson we 

## In the Next Lesson...



-------------------------------------------------------------------------------


#  - SUPPLEMENTAL: Understanding float and double encoding (32-bit and 64-bit)
(not in playlist, linked from the above lesson, in description)

## Goals:
* 


# Conclusion
* In this lesson we 

## In the Next Lesson...


-------------------------------------------------------------------------------


#  - SUPPLEMENTAL: Understanding Decimal and Negative Modulo
(not in playlist, linked from the above lesson, in description)

## Goals:



# Conclusion
* In this lesson we 

## In the Next Lesson...

------------------------------------------------------------------


#  - Defining Mathematical Functions and using Python as a Calculator


## Goals:
* Writing functions makes it easier to reproduce mathematical operations, without having to write everything out.
* For repetition, start using Python in your everyday life, as a calculator
* Start using comments to ignore bits of code
* Import mathematical functions from the `math` module
* Define more custom mathematical functions



## Why use Python as a calculator?

When first learning to program, it's important that you get a lot of repetition. It will be very helpful to use Python as a calculator whenever you can. Instead of grabbing a traditional calculator, simply use [repl.it](https://repl.it), or a python terminal to figure out answers to your mathematical questions.

An advantage of using a text editor and building your math operations in Python, is that you can keep a record of what you've tried. You can comment out some lines of code, and leave others, as we'll see below.


## `print()` vs `return`
* Notice that these functions will `return` values, and, in order to see those values in the output, we will need to `print()` what the function returns
* Try to solve these on your own before looking at the solution (if watching, pause, try, and go from there).


## A quick aside about Comments in code
* Comments are pieces of non-code text that a programmer might include in a program that they're writing in order to communicate to themself or other programmers.
* Two types of comments in Python, _inline_ comments, and _block_ comments
* Inline Comment:

```python
# this is an inline comment, where the hash symbol only applies to one line

"""
This is a block
comment, that can cover multiple
lines
"""

'''
This is also a block comment, just using
single quotes instead of double quotes
'''
```

* Generally, comments are intended to be used in instances where an explanation of the code would help a reader understand. 
    * The comment should not generally be a summary of the code's operation, although the comments in the next few lessons are for education, and will often summarize.
* Uses of comments:
    * Comments in general should provide insight into the programmer's choices
    * Comments can be used to "comment out" lines of code so that they don't execute, which can be helpful when troubleshooting bugs
    * A type of comment, called a DocString, can be included when defining functions, classes, and methods, so that code can be it's own reference material.
        * (We'll explore this later in the course)
    * Leaving `# TODO:` statements in the code, for things you want to add or change later




## Importing `math` functions and _constants_
* [See `math` module documentation](https://docs.python.org/3/library/math.html)
* a _constant_ is a fixed mathematical value, like pi, tau, or e
* importing all `math` functions
* Notice that we're using comments in this code, to describe for newbie programmers what specific lines are doing

```python
# imports all math functions, called using math.<function_name()>
import math

print(math.ceil(9.9))
print(math.sqrt(25))
print(math.pi)
```

`output`
```
10
5.0
3.141592653589793
```

* import specific `math` functions

```python
from math import ceil, sqrt, pi

# note we now omit the "math." part that we included above, as we can access the names directly
print(ceil(9.9))
print(sqrt(25))
print(pi)
```

`output`
```
10
5.0
3.141592653589793
```


You will often import the square root function `math.sqrt`, but there are quite a few other functions and constants in the `math` module. [See the `math` module documentation](https://docs.python.org/3/library/math.html). 

Keep in mind that when you program, you will often be looking thing up. You don't have to memorize, in fact, you probably shouldn't memorize. Instead, be ready to look things up, either in official documentation, or more often, on [Stack Overflow](https://stackoverflow.com/), by Googling, etc.

One nice trick is to keep a notes document and add things to it as you look them up. As you edit that document, remove the things you don't need to look up anymore, and you'll have an easy extension to your working memory. It's also a good opportunity to get used to [writing Markdown](TODO:link-to-beginning-markdown-video)




## Defining Custom Math Functions

A good way to practice writing functions, is by translating common math equations into Python functions.


### Circumference of a Circle

$$
C = 2 \pi r
$$

```python
from math import pi

def circumference_of_a_circle(radius):
    return 2 * pi * radius

print(circumference_of_a_circle(radius=2))
print(circumference_of_a_circle(radius=3))
print(circumference_of_a_circle(radius=4))
print(circumference_of_a_circle(radius=5))
```

`output:`
```
12.566370614359172
18.84955592153876
25.132741228718345
31.41592653589793
```


### Area of a Circle

$$
A = \pi r^2
$$

```python
from math import pi

def area_of_circle(radius):
    return pi * radius**2

print(area_of_circle(radius=2))
print(area_of_circle(radius=3))
print(area_of_circle(radius=4))
print(area_of_circle(radius=5))
```

`output:`
```
12.566370614359172
28.274333882308138
50.26548245743669
78.53981633974483
```


### Volume of a Sphere

$$
V = \frac{4}{3} \pi r^3
$$

```python
from math import pi

def volume_of_circle(radius):
    return (4/3) * pi * radius**3

print(volume_of_circle(radius=2))
print(volume_of_circle(radius=3))
print(volume_of_circle(radius=4))
print(volume_of_circle(radius=5))
```

`output:`
```
33.510321638291124
113.09733552923254
268.082573106329
523.5987755982989
```


### Area of a Rectangle

$$
A = w h
$$

* where $w$ is width, and $h$ is height

```python
def area_of_rectangle(width, height):
    return width * height


print(area_of_rectangle(1, 2))
print(area_of_rectangle(2, 3))
print(area_of_rectangle(3, 4))
print(area_of_rectangle(4, 5))
```

`output:`
```
2
6
12
20
```



### Area of a Square
* note that a square is a special case of a rectangle, and we can call back to the rectangle function to calculate this, although it's simpler to write a new function

$$
A = l^2
$$

* where $l$ is the length of one side of the square
* Notice that we have comments in this code to indicate when using a dependent function or an independent function

```python
# independent function
def area_of_square(length):
    return length**2

print(area_of_square(1))
print(area_of_square(2))
print(area_of_square(3))
print(area_of_square(4))


def area_of_rectangle(width, height):
    return width * height

# dependent function
def area_of_square(length):
    return area_of_rectangle(length, length)


print(area_of_square(1))
print(area_of_square(2))
print(area_of_square(3))
print(area_of_square(4))
```

`output:`
```
1
4
9
16
1
4
9
16
```


### Area of a Triangle
* We can also write a form of this function that is dependent on the `area_of_rectangle` function

$$
A = \frac{1}{2} b h
$$

```python
# independent function
def area_of_triangle(base, height):
    return (1/2) * base * height

print(area_of_triangle(1, 2))
print(area_of_triangle(2, 3))
print(area_of_triangle(3, 4))
print(area_of_triangle(4, 5))


# dependent function
def area_of_rectangle(width, height):
    return width * height

def area_of_triangle(base, height):
    return (1/2) * area_of_rectangle(base, height)


print(area_of_triangle(1, 2))
print(area_of_triangle(2, 3))
print(area_of_triangle(3, 4))
print(area_of_triangle(4, 5))
```

`output`
```
1.0
3.0
6.0
10.0
1.0
3.0
6.0
10.0
```



### Tip Calculator function
Write a function that will calculate the total amount of a dinner bill, given the total before tax, the tax rate, and percentage. Your function will accept these three values as arguments. It will then do the following:
* Apply the tax rate to the bill total
* Apply the tip percentage to the total amount
* Return the total amount of bill before and after tip.

Here’s an example of how you would call the function:

```python
bill_with_tax, bill_with_tax_and_tip = calc_total_bill(100, 0.10, 0.10)
bill_with_tax_and_tip

>>> 121.0
```


```python
def calc_total_bill(bill, tax, tip):
    bill_and_tax = bill * (1+tax)
    tax_and_tip = bill * (1+tax) * (1+tip)
    return bill_and_tax, tax_and_tip
```



# Conclusion
* The `int` and `float` data types are used to represent whole numbers and numbers with decimals, respectively. 
* Basic math operations, such as addition, subtraction, multiplication, division, and exponentiation, can be performed simply, and will follow the general PEMDAS order of operations
* Additionally, there are two special operators that you will often use when programming, modulo (`%`) and floor division (`//`)
* Many mathematical functions can be found in the built-in `math` module
* Mathematical operations that you will write repeatedly can be defined in functions.
* TODO: verify conclusion is complete


## Conclusion
* In this lesson we 

## In the Next Lesson...






------------------------------------------------------------------

#  - Declaring Variables, Incrementing Variables, Booleans, Checking Equality, and Applying logic


## Goals:
* Assigning values to variables
* Naming variables appropriately
* Incrementing numeric values in variables
* Boolean `bool` type, with values `True` and `False`
* "Truthiness"
* Comparison Operators (`==`, `>`, `>=`, `<`, `<=`, `!=`)
* Logical Operators (`not`, `and`, `or`)



## Variable assignment using the _assignment operator_ `=`
* You can think of variable assignment as giving a name to something so that it can be accessed later by different parts of your program.
    * You can use a variable to store any data type
    * Important for **reusability**
* Variables are assigned using the `=` operator.
    * variable = value
    *  `x = 4`
* Need to print to see the result of assigning a variable.
* Can assign two or more variables on the same line.
    * `x, y = 1, 2`
* Operations on a variable will be determined by the data type of the value stored.
* Variable help us keep track of values that change or values that are inputted 

* TODO: explanation and snippets for declaring variables
* TODO: Mention "gets" as how to read assignment



## Give it a good name
* You should strive to give your variables well-defined, succinct names
* Variable naming conventions are covered in [PEP 8](https://www.python.org/dev/peps/pep-0008/).
* Use **snake case** to name variables:
    * Replace spaces with _
    * `this_is_a_variable = 8`
* There are some reserved words that can’t be used as variable names.
    * [Python reserved words list](https://docs.python.org/3/reference/lexical_analysis.html#identifiers)



## Incrementing numeric variable values
* Operations that modify the current value stored in a variable 
* `+=`, `-=`, `*=`, `/=`, etc. 
* TODO: add incrementation code snippets



## Boolean `bool` data type
* TODO: explanation of `bool` type
    * result of comparison
    * related to the binary concept of 1, or 0




## Truthiness
* TODO: show inherently `True` and `False` values 
* What is the result of `bool(‘’)`?
    * `False`
* What is the result of `bool(‘’ + ‘Hi’)`?
    * `True`


## Boolean Operators

| Operator              | Meaning                 |
| ----------------------| ----------------------- |
| <center>`>`</center>  | Greater Than            |
| <center>`>=`</center> | Greater Than or Equal   |
| <center>`<`</center>  | Less Than               |
| <center>`<=`</center> | Less Than or Equal      |
| <center>`==`</center> | Equals or Is Equivalent |
| <center>`!=`</center> | Does not Equal          |


## Equals (`==`) and Not Equals (`!=`)
* TODO: demonstrate equals and not equals operations on variables
* TODO: Reiterate that we can compare `int` to `float` even though they are stored differently

```python
print(5 == 6)  # --> False
print(5 != 6)  #--> True
```


## Greater than `>`, less than `<`, Greater than or equals `>=`, Less than or equals `<=`
* TODO: demonstrate on variables

```python
print(5 > 4)   # --> True
print(5 >= 6)  # --> False
print(5 < 4)   # --> False
print(5 <= 6)  # --> True
```



## Logical operators
* TODO: introduce `not` keyword
    * show that `not True` => `False`, `not False` => `True`, and `not not False` => `False
* TODO: introduce `and`
* TODO: introduce `or`

```python
print(not True)       #--> False
print(not False)      #--> True
print(True and True)  #--> True
print(True and False) #--> False
print(True or False)  #--> True
```


## Constructing logic

|  Order of Operations    |
|-------------------------|
| <center> ~ </center>    |
| <center> & </center>    |
| <center> ^ </center>    |
| <center> | </center>    |
| <center> not </center>  |
| <center> and </center>  |
| <center> or </center>   |

* TODO: show examples of more complex logical statements
* TODO: include example of DeMorgan's in a function



What is the result of the following boolean expression?

```python
(not (not (True or False) and (True and True))) and True or True
```

* note that the `or True` on the end will evaluate the whole thing as `True`. We'll simplify the whole thing anyway
```python
(not (not (True or False) and (True and True))) and True or True
#          --simplify---
(not (not True and (True and True))) and True or True
#     --------
(not (False and (True and True))) and True or True
#                -------------
(not (False and True)) and True or True
#     --------------
(not False and True or True
#---------
True and True or True
#------------
True or True
#----------
True
```


### What do each of these return?
* `not 7 > 2`
    * `False`
* `3 >= 2 or 5 < 1`
    * `True`
* `not 8 `
    * `False`
* `bool(‘’) and 5 != 3`
    * `False`
* `bool(‘’) and 5 != 5`
    * `False`



## Other Operators
* Bitwise Operators (covered in `numpy` and `pandas`)
    * `~`, `&`, `|` are the matching bitwise operators for `not`, `and`, and `or`
    * Don’t use these or worry about them for now
    * They may not behave exactly as you expect
* Exclusive or (XOR)
    * `^` is the bitwise operator for **exclusive or**
    * For now, think of this as asking the question **“are these two things different?”**


# Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - SHORT: The "Walrus" operator


## Goals:



## Conclusion
* In this lesson we 

## In the Next Lesson...


------------------------------------------------------------------

#  - Scalar types are immutable, the `None` Type, Type Inference, Duck Typing, Checking and Comparing Data Types


## Goals:
* Understand the concept of a "scalar" type
* Intro to the concept of _mutability_ and _immutability_
* The `None` type
* Understand that Python will _infer_ the type of data
    * Understand the concept of "duck typing" in Python
* Checking variable types using `type()` and `isinstance()`



## "Scalar" types
* A scalar type holds one single value
* So far, we’ve mostly dealt with scalar types: `int`, `float`, `bool`
* Other scalar types are `string`, `None`, `complex`, `byte
* TODO: Contrast with "collection" types


## What does it mean for a type to be _immutable_?
* Modifying the value referred to by an immutable type variable value will change the location that the variable name points to in memory. You can test this using the `id()` function

```python
x = 4
print(id(x))

x -= 2
print(id(x))
```

* TODO: add more examples of immutability
* TODO: mention that there are also _mutable_ types, which we'll get to soon



## What is the `None` type?
# `None` Type 
* `None` is not the same as `0`.
* Rather, `None` is the absence of a value
* **Functions without an explicit `return` will `return` `None`**

* TODO: demonstrate the None type
* TODO: note that functions by default will return `None` when no return is explicitly defined
    * demonstrate this with a `print` vs `return` example


## Type _Inference_ 
* Simply stated, Python will look at a data value, and assign it a type that makes sense, without you needing to explicitly say, for example, that a number is an `int` or `float`
* TODO: snippet showing type inference for `int`, `float`, and `bool`
* TODO: snippet showing type inference for `str`
* The string `str` type is not comparable with numeric types, which makes sense, because how would we answer the question, "which is greater, "I'm a cat" or 20?"

```python
a = "I'm a cat"
b = 20

print(a < b)
```

`output:`
```
Traceback (most recent call last):
  File "main.py", line 4, in <module>
    print(a < b)
TypeError: '<' not supported between instances of 'str' and 'int'
```


## Duck Typing
* Python is a “duck typed” language
    * _"If it walks like a duck, and quacks like a duck, then it must be a duck."_
    * Effectively, this means that you can perform mathematical operations between similar types, such as ints and floats, because Python infers a general type for the operation.
        * For example, operations between ints and floats will result in floats
        * Division will result in a float
* TODO: Again show results for operations between numeric types that result in floats, include assignment to variables

```python
print(type(1)) # --> <class 'int'>
print(type(1.3)) # --> <class 'float'>
print(type(1 == 1.0)) # --> True
print(type(1 == 1.9)) # --> False> 
```

* TODO: Again show casting to specific result type



## Recall `type()` for checking the types of values
* Type comparison
    * `1.0 == 1` ?? ⇒ `True`
    * However, `type(1.0) == type(1)` ?? ⇒ `False`
* TODO: code examples of `type` run on variables
* TODO: code examples of checking `type` equality
    * `print(type(1.0) == type(1)) # --> False`


## `isinstance()` to check for specific types 
* Note that `isinstance` is generally preferred over `type`, even though they can be used in the same way
* TODO: code examples of `isinstance` run on variables
* TODO: code examples of checking `isinstance` equality





# Conclusion
* In this lesson we 

## In the Next Lesson...


------------------------------------------------------------------

#  - A Brief Introduction to Strings in Python


## Goals:
* Understand the basics of the string `str` type
* Understand basic string concatenation
* Interpolation using f-strings and `.format()` when using the `print()` function
* Capitalizing, Lower-casing, and Upper-casing
* Checking for substrings in strings using `in`
* Extracting substrings from strings using string indexing


## Strings
* A string `str` is an object that acts as a sequence of characters.
* Declare a `str` using quotes: single, double, and triple quotes
    * Mostly interchangeable. Single and double quotes only work with strings that span one line.
    * Strings that span multiple lines need to be declared using triple quotes.
* Note we will talk more extensively about the `string` type in later lectures


## String Concatenation using the `+` operator
* Can **concatenate** a `string` with another `string` using the `+` operator


## Interpolation using f-strings and `.format()`
* f-strings are an easy way to interpolate a value into a string
    * defined by putting an `f` in front of quotes: `f'some text'`
* `f` strings will dynamically insert variables into strings. The difference is that we just need to place the variable name in the curly braces.
    * Syntax: `f'Inserting {variable_to_insert} into this string'`

```python
state = 'Alaska'

print(f'{state} is one of the states in the US')
```

* `.format`
* TODO
* The `format` method will dynamically insert the variables passed in as parameters into the placeholders in a `string`
    * Syntax: `'Inserting {} into this string'.format(variable_to_insert)`


## Capitalizing, Lower-casing, and Upper-casing strings
* TODO

## Checking for substrings in strings using `in` and `not in`
* TODO

## Extracting substrings from strings using string indexing
* TODO



# Conclusion
* In this lesson we 

## In the Next Lesson...





------------------------------------------------------------------

#  - Beginning Control Flow with `if / elif / else`

##  Goals
* Understand the syntax of `if` statements
* Take input from a user, and choose different program paths based on that input


## `if / elif / else`
* TODO: clean this
* We use if statements if we want to evaluate code only under a certain condition
* Only when the statement following the if keyword evaluates to True will Python run the code in the body of that if block
* General Syntax:

```python
if some_condition == True:
    # execute this code
elif some_other_condition == True:
    # execute this code instead
else:
    # and if none of the above conditions are met, then execute this code block
```
* TODO: add in simple code snippets for these

* We can incorporate comparison operators and logical operators into our if statements

```python
x = 7
y = False

if x < 10 and not y:
    print('all is well')
elif x > 3 and y:
    print('danger')
else:
    print('nothing matters')
```

will output

```python
# --> all is well
```

* Another example
```python
if x + y == x or x + y == y:
    print('At least one number is zero')
elif x + y > x and x + y > y:
    print('Both numbers are positive')
else:
    print('At least one number is negative')
```


## Using `input()` to take input from a user in the terminal
* note that `input()` will give a string result, even if the value entered is a number
* Recall our `hello-world` function
```python
def get_name_from_user():
    return input("What is your name? ")

def hello_world():
    return f'Why hello there {get_name_from_user()}'

print(hello_world())
```


## Making choices based on user input
* Write a function that uses the `input()` function inside of it to take a user inputted number and check if that number is equal to `7`. If the number is equal to `7`, return `True`. If not, return `False`
* Hint: `input()` will return a string by default, so cast to an `int`:
   * `user_input = int(input(‘type number: ‘))`

```python
def check_for_seven():
    user_input = int(input('type a number: '))

    if user_input == 7:
        return True
    else:
        return False
```

* Let's get a number from a user, and describe that number

```python
def get_number_from_user():
    # notice we need to cast this to int, otherwise it will be a string
    return int(input("What is your favorite number?"))

def describe_number():
    num = get_number_from_user()

    if num % 2 == 0:
        print(f"{num} is even")
    else:
        print(f"{num} is odd")
    

    if num > 0:
        print(f"{num} is positive")
    elif num < 0:
        print(f"{num} is negative")
    else:
        print("You're not a zero, you're a hero!!")


    if num % 3 == 0 and num % 4 == 0:
        print(f"{num} is divisible by both 3 and 4")
    elif num % 3 == 0:
        print(f"{num} is divisible by 3")
    elif num % 4 == 0:
        print(f"{num} is divisible by 4")
    else:
        print(f"{num} is not divisible by 3 or 4")

    # note that we're not returning anything here, implicitly it is returning None

describe_number()
```


* let's do another example that analyses a user's input
    * Write a function that takes in a number between 0-999:
        * Print out whether the number is a single, double, or triple digit number. 
        * If the number is outside of that range, print a message saying that it is outside of the expected range. 


```python
def print_num_len(num):
    if num < 0 or num > 999:
        print(f'{num} outside of expected range')
    elif num / 10 < 1: 
        print(f'{num} is single digit')
    elif num / 100 < 1:
        print(f'{num} is double digit')
    else:
        print(f'{num} is triple digit')
```



# Conclusion
* In this lesson we 

## In the Next Lesson...







------------------------------------------------------------------

#  - Let's talk about Python Functions


##  Goals
* Understanding what a function is in Python
* Function _parameters_ and _arguments_
* Set _default arguments_ in a function
* `print()` vs `return`
* Understanding `global` vs Local Scope
* Star (`*args`) Arguments for passing in an arbitrary number of arguments
* `**kwargs` for passing an arbitrary number of positional arguments


## Understanding what a function is in Python
* We've been writing a lot of functions so far in this course, so let's describe them in more detail before we get much further.
* Functions can be thought of as ways to create repeatable procedures
    * Name the function, give it parameters (optional), write your code
* Things we need to consider when making a functions:
    * How to name the function
    * What the function expects to pass into it - arguments
    * What the function does
    * What the function returns: a value or `None`?


## Functions Basic Structure

```python
def my_func(arg1):
    # some block of code here
    return arg1 # Returns the value in arg1 when function is called
```



## Function _parameters_ and _arguments_
* TODO:


### Function **Parameters**
* Function parameters:
    * Function inputs that are inside the parentheses of the function header
    * Operate similar to variables but they only exist within the function

```python
def some_func(im_a_function_parameter): 
   return bool(im_a_function_parameter) 
```

### If not specified using the `return` keyword, a function will return `None`


### Function **Arguments**

* Pass in “arguments” to the parameters when the function is called.

```python
def add_one_to_num(num):
    return num + 1

x = 7

print(add_one_to_num(x)) # outputs 8 to console
```


### Setting Default Arguments in a function
* Default Arguments can be defined for function parameters. They are created in the function definition

```python
def add_two_numbers(num_1=1, num_2=2):
    return num_1 + num_2

print(add_two_numbers()) # outputs 3 to the console
```




## `print()` vs `return`
* `print()` and `return` ARE DIFFERENT!!
* `print()` : function takes the value passed into it and writes that value to the console.
* `return` : Keyword used to return an object from a function

```python
def some_func(x):
    print(x)

# is fundamentally different from
def another_func(x):
    return x
```


### `print`
* function takes the value passed into it and writes that value to the console.
* `print()` is in your core toolset for checking what you expect is happening in your code.
* **the `print()` function is fundamentally different from the `return` keyword!**


### `return`
* TODO



## Understanding `global` vs Local Scope
* Global Variables 
    * Variables defined in the main program
* Local Variables
    * Variables defined within the scope of a function
* You can access a variable declared in the global scope of the function within the local scope of a function
* If you want to change a global variable within the scope of a function, use `global var_name`

* TODO: demonstrate when a variable is inaccessible from outside a given function's local scope

```python

```



## Star (`*args`) Arguments for passing in an arbitrary number of arguments
* TODO
* `*args` allow for an arbitrary length tuple to be passed into the function as an argument.

```python
def star_args(*args):
    print(type(args))
    for item in args:
        print(item)
    return None
```





## `**kwargs` for passing an arbitrary number of positional arguments
* TODO

# Conclusion
* In this lesson we 

## In the Next Lesson...




------------------------------------------------------------------

#  - Introducing Lists in Python

##  Goals
* What is a `list` 
* Range
* List indexing


## What is a `list` 
* TODO
* A list is a **collection** of arbitrary objects
* Lists are **ordered** and **mutable**
* Declare empty lists using `[]` or `list()`

```python
lst_1 = []
lst_2 = list()
```

* Declare a list with values using [1, 2, 3]

```python
lst_3 = [1, 2, 3]
```

* Lists can hold both **scalar** types and collections

```python
nested_list = [[2, 3, 4], [2, 1, 5]]
```

* TODO: write a function that takes 4 arguments and returns them packed into a list


## Using `range` to construct a range of numbers
* TODO
* The `range` function helps us create an object that can be converted into a `list` of integers.
* Syntax:
    * `range(start, stop, step)`
    * Start is inclusive, stop is not
* `range` is an object that can help us to iterate over a series of numbers.
* `range` can provide indices for items in a `list` or in a pair of lists

```python
one_to_99 = list(range(1,99+1))
```




## List indexing
* TODO
* We use square brackets `[idx]` to access elements in a `list`
* Python uses **zero-based indexing**. Therefore, we count starting from 0.
    * `lst[0]` will return the first element of the list
* List indexing also allows us to reassign the value at that index
* Lists can be unpacked into variables.



`num_list = list(range(4, 16))`

* How do you index `num_list` to get `6`? How about `15`?
    * `print(num_list[2])`
    * `print(num_list[11])`


### More indexing examples
* TODO: cleanup
```python
x = [1, 2, 3, 4, 5, 6, 7, 8, 9, [“hello”, 85, True], 0]
```

* How would you index to get the value `8`
    * `print(x[7])`
* How would you slice to get the `list`: `[5, 3, 1]`
    * `print(x[4::-2])`
* How would you replace the value `4` with the value `10` using indexing?
    * `x[3] = 10`
* How would you slice into the `list` to get: `["hello", 85]`
    * `print(x[9][:2])`
* How would you add the value `42` to the `list`?
    * `x.append(42)`



# Conclusion
* In this lesson we 

## In the Next Lesson...




------------------------------------------------------------------

#  - List Membership, Slicing, and Nested Lists

##  Goals
* List Membership
* List Slicing
* Nested Lists



## List Membership
* TODO
* Use the in keyword to check whether an element is in a list
    * `5 in [1, 2, 3, 4]` will be `False`
* You can conversely use not in to check if an element is not a member of the list
    * `5 not in [1, 2, 3, 4]` will be `True`




## List Slicing
* TODO
* Use list slicing if you want to access a portion of a list
    * Notation is similar to indexing, e.g. `[1:3]`
    * Syntax: `list[start:stop]`
        * The slice starts at the start value and goes up until the stop value
        * The slice will not inclued the stop value
* Like the range function, we can specify a step
    * Syntax: `list[start:stop:step]`


`num_list = list(range(4, 16))`
* How do you slice `num_list` to get this sublist: `[10, 11, 12, 13, 14, 15]`
    * `print(num_list[6:13])`
* How do you slice `num_list` to get this sublist: `[4, 6, 8, 10, 12, 14]`
    * `print(num_list[::2])`
* Challenge: How do you slice `num_list` to get this sublist: `[8, 7, 6, 5, 4]`
    * `print(num_list[4::-1])`




## Nested Lists
* TODO
* A list that contains another list is known as a nested list
    * Example: `lst = [‘a’, ‘b’, [1, 2, 3]]`
* To access an element in a nested list, you will need two indices
    * `lst[2][0]` will access the value `1`  
* To access more than one element in a nested list, use a slice:	
    * `lst[2][:2]` will produce the slice `[1, 2]`



# Conclusion
* In this lesson we 

## In the Next Lesson...





------------------------------------------------------------------

#  - List Mutability, Copying, Appending, and Unpacking

##  Goals
* List Mutability
* Copy a List
* Append to a List
* Unpacking a list


## List Mutability
* TODO
* Lists are mutable
    * The contents in a `list` can change while its `id()` stays the same.
    * Two lists that contain the same values will have different ids. 


Examine list1 and list2 after running these code snippets and explain why each code snippet gives different values


### snip 1
```python
list1 = [1, 2, 3]
list2 = list1
list1.append(4)
```
### snip 2
```python
list1 = [1, 2, 3]
list2 = list1[:]
list1.append(4)
```
* In the first example, both lists are updated, as they are the same object referred to by different names. In the second example, only the copy is updated with the new value








## Copy a List
* TODO
* Create a copy of a list with the `.copy()` method
    * Syntax: `lst_2 = lst.copy()`
* `list` slicing can also be used to make a copy
    * Syntax: `lst2 = lst[:]`
* It is good practice to not modify function arguments. If a function argument is a `list`, create a copy before changing that `list` in any way. 




## Append to a List
* TODO
# `append()` to a `list`
* The `.append()` method places a new value at the end of the `list` 
    * Syntax: `lst.append(new_item)`	
* Can append a `list` to another `list` in order to create a nested `list`.




## Unpacking a list
* TODO
* We can unpack the elements of a `list` so that we are storing these elements in a variable:
    * `fruit1, fruit2, fruit3 = [‘grapes’, ‘blueberries’, ‘apples’]`
* Unpacking a `list` is untenable for a very long `list`.




# Conclusion
* In this lesson we 

## In the Next Lesson...




------------------------------------------------------------------

#  - Introduction to For Loops and traversing a `list`

##  Goals
* `for` loops
* Traversing a `list`
* Traversing a `range` of numbers



## `for` loops
* For loops iterate through each element of a `list`
    * Syntax: 

```python    
for element in list:
	print(element)
```



## Traversing a `list`
* TODO
* What actually happens when we go through each iteration of a loop?
* Given the following `list` of letters, create a function that goes through each letter and prints the letter if it is a vowel.
    * It will be helpful to write a helper function that returns True if a character is a vowel and call it within this function
    * Create a plan before coding


```python
char_list = ['o', 'r', 'c', 'h', 'i', 'd']

def is_vowel(let):
    if let in ['a', 'e', 'i', 'o', 'u']:
        return True
    else:
        return False

def print_vowels(lst):
    for char in lst:
        if is_vowel(char):
            print(char)

print_vowels(char_list)
```




## Traversing a `range` of numbers
* Another way to use a `for` loop is to iterate through `range(len(list))` in order to access all the indices, rather than the elements themselves. 




## Traversing a `str`


## Conclusion
* In this lesson we 

## In the Next Lesson...




------------------------------------------------------------------

#  - Accumulators and boolean flags, loops as filters


## Goals
* accumulators
* boolean flags
* `list` accumulators
* String accumulators
* loops as filters




## accumulators
* TODO
* An accumulator can be thought of as a running total that is held in a variable	
* Accumulator Pattern: 
    * Initialize the accumulator variable
    * Repeat:
        * Modify the accumulator variable
    * When the above loop terminates, the accumulator will have the correct value. 



### A simple `int` sum accumulator
* TODO
* We can calculate a sum by using an integer type accumulator
summ = 0

```python
for num in nums:
	sum += num
```

* We can also calculate the sum when our list is comprised of floats. 
* The final accumulator will be a float. 


### A simple sum accumulator example: Summing the evens in a list
* Write a function to sum all even numbers in a `list`

```python
def sum_evens(num_list):
    accum = 0

    for num in num_list:
        if num % 2 == 0:
            accum += num
    return accum
```


### Writing the factorial accumulator
* Write a function to calculate the result of n!
* Note that `factorial()` is a function available in the `math` module. However, it's a good simple algorithm to learn early on.

$$
4! = 4 * 3 * 2 * 1
$$

$$
3! = 3*2*1
$$

$$
0! = 1
$$

* Think about edge cases 

```python
def factorial(num):
    prod = 1
    if num == 0:
        return prod
    if num < 0:
        print('Negative factorial is undefined')

    for i in range(num+1):
        prod *= i

    return prod
```

 



Write a function called `accum_nums` that takes in an integer `n` as an argument it should perform the tasks below for a range of numbers from `1` through `n` (int accumulator starts at 1)
* If the number is divisible by 3, add 3 to the accumulator
* If the number is divisible by 5, divide accumulator by 5
* If number is divisible by 4, multiply the accumulator by 4
* If number is divisible by 3, 4, and 5 do nothing
* If number is divisible by 3 and 4, subtract 12 from accumulator
* If number is divisible by 3 and 5, floor divide accumulator by 15
* If number is divisible by 4 and 5, modulo accumulator by 20



```python
def accum_nums(n):
    acc = 1
    for num in range(1, n+1):
        if num % 4 == 0 and num % 5 == 0 and num % 3 == 0:
            continue
        if num % 4 == 0 and num % 3 == 0:
            acc -= 12
        if num % 3 == 0 and num % 5 == 0:
            acc //= 15
        if num % 4 == 0 and num % 5 == 0:
            acc %= 20
        if num % 3 == 0:
           acc += 3
        if num % 4 == 0:
            acc *= 4
        if num % 5 == 0:
            acc /=5
    return acc
```








## boolean flags
* TODO
* Occasionally, you will need to use an accumulator that is set to a boolean value. 
* If some condition is met in the for loop, the boolean assigned to the accumulator will change to the opposite value. Otherwise, it will stay the same.
* These boolean flags can also be used as exit conditions in a loop.
* Syntax:   

```python
accumulator = False
for element in some_list:
    # some code
    if some_condition:
        accumulator = True
```


### The `is_prime()` function ...
* Let’s code it using a boolean flag

```python
def is_prime(num):
    prime = True
    if num == 2 or num == 3:
        return True

    for divisor in range(2, num):
        if num % divisor == 0:
        prime = False
    
    return prime

for i in range(2, 100):
    print(i, is_prime(i))
```




## `list` accumulators
* TODO
* Sometimes, you will need an accumulator that is an empty list.
* As the for loop gets evaluated, the accumulator will be appended with new values. 
* Syntax: 

```python
accumulator = [ ]
for element in some_list:
    # some code
    accumulator.append(some_value)
```


* Given two arbitrary lists, write a function that finds the common elements between them. Store these common elements in a `list`, and return that `list`
    * Bonus 1: return the items sorted in the returned `list`
    * Bonus 2: make sure there are no duplicates in the returned `list`

```python
def get_common_elements(lst1, lst2):
    output = []

    for item in lst1:
        if item in lst2:
            if item not in output:
                output.append(item)
    
    return sorted(output)

lst_a = [4,9,6,5,7,8,6,2]
lst_b = [1,2,3,4,5,6,7]

print(get_common_elements(lst_a, lst_b))
```




Write a function called `words_start_with()` with two parameters, a list of letters and a string. The function should return a new list filled with words from the string that start with the letters in the list of letters.
Test with this string:

```python
str1 = "It's a beautiful day in the neighborhood, A beautiful day for a neighbor, could you be mine? Would you be mine?"
```


```python
def words_start_with(letters, string):
    lst = []
    for word in string.split():
        if word[0].lower() in letters:
            lst.append(word)
    return lst
```




Write a function called `examine_lst()` that takes a list of various values as an argument, then returns a new list of those values processed by these rules:
* Accumulate elements that are not integers
    * If an element is a float, change it to a string
    * If an element is a string, get the length of that string
* Test String:

```python
l1 = [192, 504, 23.11, 3.14, 'table', 'chair', 55, 1039.1, 0, 0.0, '0.0', 'python']
```


```python
def examine_lst(l):
    out_l = []
    for i in l:
        if type(i) == float:
            out_l.append(str(i))
        elif type(i) == str:
            out_l.append(len(i))
	    elif type(i) != int:
            out_l.append(i)
    return out_l
```





## String accumulators
* We can concatenate a string by using a `string` type accumulator
* We can concatenate the string by letter, by word, or by some other separator within our string


```python
str1 = ''
for s in string:
    str1 += s
```



Write a function called `build_non_vowel_str()` that takes in a string and returns a string accumulator that accumulates all non-vowels.

Pass in this string:

```python
string = "It’s a beautiful day in the neighborhood, A beautiful day for a neighbor, could you be mine? Would you be mine?"
```


```python
def non_val(s):
	new_s = ''
	for char in s:
		if char in ['a', 'e', 'i', 'o', 'u', 'A', 'E', 'I', 'O', 'U']:
			continue
		else:
			new_s += char
    return new_s
```


Write a function called `collect_evens()` that takes a list of integers. The function should return a string that accumulates the even numbers into a string.
* Example: `collect_evens([1, 2, 3, 4])` -> `'24'`

```python
def collect_evens(lst):
	s = ''
	for i in l:
		if i % 2 == 0:
			s += str(i)
	return s
```




## loops as filters
* TODO
* We can filter list elements that meet a condition using accumulators.
* As the for loop is evaluated, values that meet the condition will be appended to a new empty list. 
* Syntax: 

```python
some_list = [stuff, more stuff]
accumulator = [ ]
for element in some_list:
    if some_condition:
        accumulator.append(element)
```




## Conclusion
* In this lesson we 

## In the Next Lesson...




------------------------------------------------------------------

#  - Break, Continue, Pass


## Goals
* break
* continue
* pass



## `break`
* TODO:
* Use `break` in `for` loops to exit the loop when some condition has been met
* Syntax:

```python
for element in some_list:
if some_condition:
	break
```

* Use `break` in `while` loops to avoid an infinite loop


### Using `break` in `is_prime()`
* Use break to exit the loop

```python
def is_prime(num):
    prime = True
    for i in range(2, num):
        if num % i == 0:
            prime = False
            break # this will end early
    return prime
```



## `continue`
* TODO:
* Use `continue` in `for` loops in order to skip code and continue to the next iteration of the loop when some condition is met
* Syntax:

```python
for element in some_list:
    if some_condition:
	    continue
    # some code
```







## `pass`
* TODO:
* Use pass as a placeholder for future code
* Syntax:

```python
for element in some_list:
    pass

def function_name():
	pass
```



## Conclusion
* In this lesson we 

## In the Next Lesson...




------------------------------------------------------------------

#  - Lists: append, extend, remove, and pop

## Goals
* appending
* extending
* removing
* pop



## appending
* TODO: this is covered earlier, but should touch on it again here really quick
* The `append` method places a new value at the end of the `list`.
    * Syntax: `list.append(new_item)`
* Can `append` a `list` to another `list` in order to create a nested `list`.



## extending
* TODO
* The `extend` method combines two lists
    * Syntax: `list1.extend(list2)`
    * In the above example, the `list2` elements will be inserted into `list1`



## removing
* TODO
* Use the `remove` method to remove an element from a `list`
    * Syntax: `list1.remove(some_item)`
    * Only removes the first instance of that element
* Use `del` to remove a specific index of element, or slice of elements, in a `list`:
    * `del list[index]`
    * `del list[start:stop]`



## pop
* TODO
* The `pop` method removes the last item from a `list` in place and returns the value of that last item
    * Syntax: `list_name.pop()`
* The value of the last item can be stored by assigning the method call to a variable
    * `last_element = list_name.pop()`
* What will be stored in the variables `lst` and `last_element` after executing the following code?
    * `lst = [1, 3, 5, 7]`
    * `last_element = lst.pop()`


## Conclusion
* In this lesson we 

## In the Next Lesson...




------------------------------------------------------------------

#  - Lists: 

## Goals
* len
* list traversal by index, using `enumerate`



## len
* TODO
* `len()` return the length of the `list` passed in
    * Syntax: `len(list_name)`
* What would be the result of `len([1, 2, [1, 2]])`


## list traversal by index, using `enumerate`
* TODO
* Sometimes you will need to write a `for` loop that can keep track of items in a `list` and their corresponding indices.
* Syntax:

```python
for idx, num in enumerate(my_lst):
    some code
```

* `enumerate` needs two variables: the index gets assigned to the first variable and the item from the `list` gets assigned to the second

* Create a function that will iterate over a `list` printing out each value of the `list` squared and the indexed position of each item starting at an index of `1` instead of `0`.

```python
sample_data = [2, 4, 6, 8, 10, 12, 14]
```

```python
def squared_with_indices(num_list):
    for idx, num in enumerate(num_list, 1):
        print(num**2, idx)

squared_with_indices(range(1, 20))
```





## Conclusion
* In this lesson we 

## In the Next Lesson...




------------------------------------------------------------------

#  - Lists: 

## Goals
* sort vs sorted
* reverse vs reversed




## sort vs sorted
* TODO
* The `sort` and `reverse` methods are slightly different from the `sorted` and `reversed` functions
* The `sort` method will sort all the values in a `list` in ascending order and change the `list` in place. `sorted` will return a `list` with elements sorted but does not modify the original `list`.
    * Syntaxes:
        * `lst.sort()`
        * `sorted(lst)`




Coding a Median function using `sorted()`
* the middle value of a numeric data set

|Symbol                 |           Meaning               |
|-------------------------------|---------------------------------|
| <center>$med(A)$</center>        | Where A is the collection on which to take the median    |
| <center>$\tilde x$</center>| "x-tilde" is also used to represent median|


* Calculating Median
1. Sort the List
2. Find the middle value(s)
    * if list is odd, just select the middle value
    * if list is even, take mean of two middle values

* example:

```python
odd_list = [13, 18, 13, 14, 13, 16, 14, 21, 13]
even_list = [15, 14, 10, 8, 12, 8, 16, 13]
```

* Code the `median()` function. Make sure to account for even and odd length lists.


```python
def median(lst):
    lst_sorted = sorted(lst)

    # if odd
    if len(lst) % 2 == 1:
        mid = int(len(lst) / 2)
        return lst_sorted[mid]
    else:
        upper_mid_idx = int(len(lst)/2)
        return mean([lst_sorted[upper_mid_idx-1], lst_sorted[upper_mid_idx]])
```


## reverse vs reversed
* TODO
* The `reverse` method will reverse the list in place. `reversed` will return an iterable object that must be cast to `list` to be indexed and used as a `list`. In fact, list slicing is preferable to `reversed` when wanting to get a reversed list.
    * Syntaxes:
        * `lst.reverse()`
        * `reversed(lst) # returns an iterable object`
        * `lst[::-1]`
* What would be the result of `list(reversed([1, 5, 6, 4, 2]))`


## Conclusion
* In this lesson we 

## In the Next Lesson...




------------------------------------------------------------------

#  - Lists: 

## Goals
* `sum`
* `max` and `min`
* `count`



## sum
* TODO
* `sum()` will calculate the sum of all the elements of the list that is passed in.
    * Syntax: `sum(list_name)`
    * Only works with lists that contain only integers and floats


Code the `mean()` function
* sum of the numeric elements, divided by the number of elements, expressed as:
* Trimmed Mean
    * Can be used to combat large devations and outliers
    * “trim” some percent off of  max and min of data list:
    * Advantage - can help combat outliers that might influence our mean
    * Disadvantage - we are removing portions of our data which might be very important

$$
\frac{1}{n} \sum_{i=1}^n a_i
$$
* BONUS: Include a `trim` parameter that removes the greatest and least `n` values

* Test with this data:

```python
a = [1, 5, 7, 10, 15, 23, 35, 67, 220, 2000]
```



```python
def mean(lst, trim_by=0):
    lst_ = lst.copy()

    if trim_by > 0:
        lst_ = sorted(lst_)[trim_by:-trim_by]

    return sum(lst_) / len(lst_)
```




## max and min
* TODO
* `max()` returns the highest numeric value in a `list`
    * Syntax: `max(list_name)`
* `min()` returns the lowest numeric value in a `list`
    * Syntax: `min(list_name)`


## count
* TODO
* The `count` method will return a count the occurences of an item in a `list`.
* Syntax: `list.count()`



Mode
* Unlike the median and mean, the mode can be applied to categorical data.
    * Special Case: The median can be applied to categorical data which is ordinal in nature
* The mode is not very useful for continuous data. 
* Rather than trying to represent the “center” of a dataset or distribution, the mode seeks to find the element with the greatest frequency.
* Can consider first mode, second mode, and so on in describing a data set


Code the mode() function.


```python
'''
Mode
'''
def mode(lst):
    most_occurring = lst[0]

    for item in lst[1:]:
        if lst.count(item) > lst.count(most_occurring):
            most_occurring = item

    return most_occurring


mode_lst = ['kangaroo', 'muskrat', 'platypus', 'muskrat', 'squid', 'squirrel', 'muskrat']

# print(mode(mode_lst))
```


## Conclusion
* In this lesson we 

## In the Next Lesson...








------------------------------------------------------------------

#  - Lists: 

## Goals
* any & all
* parallel lists
* `zip()`
* unpacking lists



## any and all
* TODO
* A value where `bool(value) == True` can be considered ‘truthy’
* `any()` returns `True` if any of the values in a `list` are ‘truthy’
    * Syntax: a`ny(list_name)`
* `all()` returns `True` if all of the values in a `list` are ‘truthy’
    * Syntax: `all(list_name)`
* What is the result of `any([0, 2, 5, 6])`? What is the result of `all(['', 'a', 'c', 'p'])`







## all
* TODO


## parallel lists
* TODO
* Two lists that have equal length and contain associated values at each index are parallel.
* The same index can be used in each of the parallel lists to access the related data.




## `zip()`
You know how to iterate over a single data structure, but what if you have parallel lists? How can we iterate over these at the same time?
Syntax:

```python
for i, j in zip(lst1, lst2):
	#some code here
```


Write a function that prompts the user to input numbers separated by commas. Your script will then take these inputted numbers and store them as a list of tuples, two at a time. Use the zip() function to do this.  If the user inputs an odd number of numbers, then only make a list of the largest number of pairs of two that are possible.


Write a function that takes a string of numbers separated by commas. Your script will then take these numbers and store them as a list of tuples, two at a time. Use the zip() function to do this.  If the user inputs an odd number of numbers, then only make a list of the largest number of pairs of two that are possible.

Example: If you inputted the numbers:\
    `'1, 2, 3, 4, 5, 6'`\
your function should return\
    `[(1, 2), (3, 4), (5, 6)]`\
If you inputted the numbers\
    `'1, 2, 3, 4, 5'`\
your function should return\
    `[(1, 2), (3, 4)]`




```python
def build_tups():
    inp = input('Enter numbers, separated by commas: ')
    lst1 = []
    lst2 = []

    nums_str = inp.split(', ')

    for i in range(0, len(nums_str), 2):
        lst1.append(int(nums_str[i]))
        if i+1 < len(nums_str):
            lst2.append(int(nums_str[i+1]))

    return list(zip(lst1, lst2))

print(build_tups())
```






## unpacking lists
* TODO



### unpacking a nested `list`
* In the case of nested lists, we can use an accumulator to unpack the nested items into a new `list`.
* In the new `list`, the nesting will be “undone.”



## Conclusion
* In this lesson we 

## In the Next Lesson...






------------------------------------------------------------------

#  - `while` loops 

## Goals
* Understanding `while` loops
* infinite loop
* conditional loops
* open ended problems
* `for` vs `while` loops






## Understanding `while` loops
* TODO
* Use `while` loops when the number of iterations needed to complete a loop is not known
* Syntax:

```python
while some_condition:
    some code
```

* Typically, `while` loops have some counter or flag as well.



## infinite loop
* TODO
* What happens if we run the code below?
* Syntax:

```python
counter = 1
while counter < 10:
    print(‘testing’)
```

* Avoid writing infinite loops



### Consider using a `for` in place of a `while`
* A `for` loop can be set with an arbitrarily high ranged number and an escape condition
* Creates code safe from infinite loops

```python
for _ in range(10000000):
    # do something
    if condition_met:
        break
```


## conditional loops
* TODO
* Mostly `while` loops get initialized with some sort of conditional statement. The `while` loop will execute until the statement is no longer `True`
* Syntax:

```python
counter = 0
while some_condition:
    # some code
    # change counter
```


### Extracting a list of divisors
* TODO
* Write a function that computes and returns a `list` of all of the divisors of some positive number. Use a `while` loop. Things to think about:
    * How do you determine if a single number is a divisor of another?
    * What is your stopping condition?
    * BONUS: rewrite this with a `for` loop

```python
def get_divisors(number):
    divisors = []
    divisor = 1

    while divisor <= number:
        if number % divisor == 0:
            divisors.append(divisor)
        divisor += 1

    return divisors

print(get_divisors(144))
```

* `for` loop solution

```python
def get_divisors(number):
    divisors = []

    for divisor in range(1, number+1):
        if number % divisor == 0:
            divisors.append(divisor)

    return divisors

print(get_divisors(144))
```



## open ended problems
* TODO
* An open-ended problem is one where we do not know how many iterations we will need in order to solve the problem
* For example:
    * Converging on $\pi$ through a random sampling process, you'll want an exit condition for when you reach a certain level of surety
    * Run state for an application, where "Quit" would be the only instance where the containing loop would exit.



## `for` vs `while` loops
* TODO
* In general, always use `for` loops to avoid infinite loops
    * Will always terminate at the end of an iterable when traversing elements in that iterable
    * Useful when you know how many iterations are needed
* However, there are some problems that should be solved using `while` loops
    * Open-ended problems
    * Menus
    * Run States




## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - Creating a Menu using a `while` loop

## Goals
* Creating a simple menu


## Creating a simple menu
* TODO
```python
selections = []
another_order = True

while another_order == True:
    menu_string = '''Select from this list:
    1 : bread
    2 : butter
    3 : potatoes
    4 : broccoli'''

    print(menu_string)

    inp = int(input('please make a selection, 1-4: '))

    if inp in [1,2,3,4]:
        selections.append(inp)
    else:
        print('-- your selection was not understood --')
        continue

    inp2 = input('would you like to place another order? (y/n)')

    if inp2 == 'y':
        continue
    else:
        another_order = False


print(f'Your order list: {selections}')
```






## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - Strings: Operators, Casting, Joining, and Enumerate

## Goals
* The string datatype
* Basic string Operators
* Casting to and from a string
* Join a `list` to create a string
* Using `enumerate` on strings





## The `string` datatype
* Strings are simply a collection of characters
* However, in Python, a `string` is a scalar type and is immutable
* Strings are declared with single tick or ,double tick, quotes in groups of 1 or 3 in the beginning and end.
    * Mostly interchangeable. Single and double quotes only work with strings that span one line. 
    * Strings that span multiple lines need to be declared using triple quotes.


## Basic `string` Operators
* We can use the addition operator to concatenate strings.
    * `'My first string ' + 'My second string'` => `'My first stringMy second string'`
* The multiplication operator will repeat the string `n` times.
    * `'Repeating string' * 3` => `'Repeating stringRepeating stringRepeating string'`


## Casting to and from a `string`
* Just about any data type can be cast to a `string`.
    * Use the `string` casting function: `str()`
* Not every `string` can be cast to another data type.
    * `int('a')` will not work
* String concatenation will only work between strings
    * Need to cast any numeric variables to a `string` before concatenating.


## Join a `list` to create a `string`
* Use the `join` `string` method to create a single `string` that contains all the elements of a `list`.
    * `''.join(list)`
* All the elements of the `list` must be strings for the `join` method to work
    * You can use the `map` function to quickly cast all the elements of a `list` to strings
    * `list(map(str, list))`


## Using `enumerate` on strings
* The `enumerate` function can be used on strings:

```python
for idx, ch in enumerate(string):
    print(idx, ch)
```





## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - Strings: 

## Goals
* `string` Slicing
* using `.replace()` to replace substrings within a string
* Processing strings within a list




## `string` Slicing
* Use slice indexing (similar to a list) to access characters or subsequences of characters
* `string[index]`
* `string[start:end]`
* `string[start:end:skip]`


## `replace`
* The `replace` method is used to replace every occurence of a specified substring in the original substring with another substring
    * Syntax: `string.replace(old_substring, new_substring, 1)`
* The third argument here will limit the amount of times the `replace` method will be applied to only once.

```python
string = 'I love to look at the moon'

string = string.replace('o', 'puppy', 2)
```


## Processing strings within a list
Write a function that takes a `list` like the following `list` of column names and change any spaces in the column names to underscores. Return a modified `list` with the updated names.

```python
column_names = ['gender', 'longest absence from school', 'is enrolled', 'enlist', 'unemployed', 'filed for bankruptcy', 'school', 'peace corps']
```



```python
column_names = ['gender', 'longest absence from school', 'is enrolled', 'enlist', 'unemployed', 'filed for bankruptcy', 'school', 'peace corps']

def add_underscores(feature_list):
    new_list = feature_list.copy()
    for idx, column in enumerate(new_list):
        if ' ' in column:
            new_list[idx] = column.replace(' ', '_')

    return new_list

```



## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - Strings: 

## Goals
* Applying the `list()` function to strings
* Applying the `split()` method to strings to create word lists



## Applying the `list()` function to strings
* TODO
* A `string` can be cast to a `list` using the `list` function
    * `list(string)`
* The `list()` function will separate each character in the `string` into a new element in the returned list.


## Applying the `split()` method to strings to create word lists
* TODO
* Quick aside: Strings are immutable so methods will not change the `string` in place like with lists.
* This method splits a `string` at each occurrence of a specified delimiter and will return a list with each split substring.
    * `string.split(delimiter)`
* The delimiter will not be included in the returned `list`




## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - Strings: 

## Goals
* `lower()`, `upper()`, `swapcase()`, and `capitalize()`
* Creating a simple letter counter using parallel lists
* The `count()` method



## `lower()`, `upper()`, `swapcase()`, and `capitalize()`
* The `lower` method will return a `string` where all the letters are lowercase
    * Syntax: `string.lower()`
* The `upper` method will return a `string` where all the letters are uppercase
    * Syntax: `string.upper()`
* The `swapcase` method will return a `string` where all the letter’s cases are swapped
    * Syntax: `string.swapcase()`
* The `capitalize` method will return a `string` where the first letter of the `string` will be capitalized and the rest will be lower case.
    * Syntax: `string.capitalize()`



## Creating a simple letter counter using parallel lists
Write a function that takes in a string. Return two parallel lists: one that contains the unique characters in the string and another that has the number of times that character appears in the original string.


```python
s = 'This is a string, we want you to count how many times each unique character appears in this string!'

def get_letter_count(string):
    letters = []
    counts = []

    for let1 in string:
        index = 0
        if let1 not in letters:
            letters.append(let1)
            counts.append(0)
            index = len(letters) - 1
        else:
            for idx, let2 in enumerate(letters):
                if let1 == let2:
                    index = idx
                    break
        counts[index] += 1
    return letters, counts

letters, counts = get_letter_count(s)

for i in range(len(letters)):
    print(f'{letters[i]}: {counts[i]}')
```

or

```python
s = 'This is a string, we want you to count how many times each unique character appears in this string!'

def get_letter_count(string):
    letters = []
    counts = []

    for let in string:
        if let not in letters:
            letters.append(let)
            counts.append(1)
        else:
            counts[letters.index(let)] += 1

    return letters, counts

letters, counts = get_letter_count(s)

for i in range(len(letters)):
    print(f'{letters[i]}: {counts[i]}')
```


## The `count()` method
* The `count` method is used to count every occurrence of a specified substring in the original string
    * Syntax: `string.count('a')`

### Applying `count()` to the letter counter

```python
def get_letter_count(string):
    letters = []
    counts = []

    for let in string:
        if let not in letters:
            letters.append(let)
            counts.append(string.count(let))
        else:
            continue

    return letters, counts
```





## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - Strings: More Practice

## Goals
* Removing _stopwords_ and making a word list
* Solving the anagrams problem



## Removing _stopwords_ and making a word list
Create a function that takes in a string. This function should split the string into a list of lowercase words that make up that string. Return a list of unique ‘cleaned’ words.
* Challenge: strip any punctuation (for now, strip commas and periods)
* Challenge: remove the common english words from the list below you are returning


```python
def clean_string_lst(txt_in):
    punct_lst = [",", ".", ";", ":", "!", "?", "'", '"'],
    remove_words = ["i", "me", "my", "myself", "we", "our", "ours", "ourselves", "you", "your", "yours", "yourself", "yourselves", "he", "him", "his", "himself", "she", "her", "hers", "herself", "it", "its", "itself", "they", "them", "their", "theirs", "themselves", "what", "which", "who", "whom", "this", "that", "these", "those", "am", "is", "are", "on", "off", "over", "under", "again", "further", "then", "once", "here", "there", "when", "where", "why", "how", "all", "any", "both", "each", "few", "more", "most", "other", "some", "such", "no", "nor", "not", "only", "own", "same", "so", "than", "too", "very", "can", "will", "just", "don", "should", "now"]

    for punct in punct_lst:
        if punct in txt_in:
            txt_in = txt_in.replace(punct, "")

    lst = []
    for word in txt_in.lower().split():
        if word not in lst + remove_words:
            lst.append(word)

    return " ".join(lst)


my_txt = "Hello there! How are you? Why don’t you take a seat over there? Once we went to the store and we found ourselves in a strange place. We ran into two people. They were very interesting to talk to. Each of them had an interesting accent and we wondered where they were from."
print( clean_string_lst(my_txt) )
```




## Solving the Anagrams problem

Let's create a function that takes in a list of words and returns a new list of words that are anagrams of each other:
Example:
This list:\
`['dog', 'god', 'cat', 'act', 'tack', 'star', 'rat', 'rats']`

Will return:\
`['dog', 'god', 'cat', 'act', 'star', 'rats']`


Step 1: Think about the problem, how do we approach this? What are we comparing and how to we compare it?

We are comparing each item in the list to every other item in the list EXCEPT itself!

But what does this look like?

We will need two for loops!s



Step 2: Before we get into our iteration structure, let's think about what the comparisons that we need to make are

Let's take the words 'dog' and 'god' for example, are these anagrams of each other?

So how can we compare these two words??

`sorted('dog') == sorted('god')`

Why doesn't this work?
`set('dog') == set('god')`
Think about
`set('dog') == set('good')`




Step 2: Let’s think about our accumulator, what are we accumulating into?

`anagram_lst = []`

Step 3: What does our control flow look like, just use i and j for to represent our words

`if sorted(i) == sorted(j):`


Step 4: How do we add our accumulation into this control flow?

```python
if sorted(i) == sorted(j):
    anagram_lst.append(????)
```



Step 5: What are we appending to our accumulator?

```python
if sorted(i) == sorted(j):
    anagram_lst.append(i)
```
Step 6: Let’s think about our edge cases here. What might those be?

>Think about if you are comparing each item in the list
to each item in the list again


Step 6 continued: so how do we take care of those edge cases in our control flow?
```python
if i == j:
    continue
elif sorted(i) == sorted(j):
    anagram_lst.append(i)

# Or

if sorted(i) == sorted(j) and i != j:
    anagram_lst.append(i)
```



Step 7: How do we write code to compare everything in the list to itself? How many loops might we need?

```python
for i in lst:
    for j in lst:
```


Step 8: Let’s put the code we have come up with so far together and wrap it in a function called `anagrams()`
```python
def anagrams(lst):
anagram_lst = []
for i in lst:
        for j in lst:
if sorted(i) == sorted(j) and i != j:
                anagram_lst.append(i)
    return anagram_lst

Try running the code with the list:
l = ['dog', 'god', 'cat', 'act', 'tack', 'star', 'rat', 'rats',
    'arts', 'start', 'good']
```


What’s wrong with our output?? How do we change our code to
get exactly what we want?

```python
def anagrams(lst):
anagram_lst = []
for i in lst:
        for j in lst:
if sorted(i) == sorted(j) and i != j:
                anagram_lst.append(i)
    return list(set(anagram_lst))

# OR

def anagrams(lst):
anagram_lst = set()
for i in lst:
        for j in lst:
if sorted(i) == sorted(j) and i != j:
                anagram_lst.add(i)
    return list(anagram_lst)
```




## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - The Random module

## Goals
* The importance of randomness in problem solving
* Using `random.choice()` to randomly select from a list
* Getting random integers using `random.randint()`
* Getting random floats using `random.random()`


## The importance of randomness in problem solving
* TODO



## Using `random.choice()` to randomly select from a list
* TODO

A sampling example using Python
* What can you do to better approach the population parameter?

```python
# from random import choice

def get_samps(sample_range, num_samples=5):
    
    samples = []

    for _ in range(num_samples):
        samples.append(choice(sample_range))
    
    return samples

num_samples = 5
sample_range = list(range(0, 99+1))
print(f'mu: {mean(sample_range)}')
# print(f'x_bar: {mean(get_samps(sample_range, num_samples=5))}')

means = []
for _ in range(100000):
    means.append(mean(get_samps(sample_range, num_samples)))

print(f'mean of means: {mean(means)}')
```




Write a function called `series_of_flips`.
* define one parameter, `n`, which represents the number of coin flips
* return a list of length `n` containing `n` random coin flips


```python
from random import choice

def coin_flip():
    flip = ['H', 'T']
    return choice(flip)

def series_of_flips(n):
    flips = []
    for _ in range(n):
        flips.append(coin_flip())
    return flips
```





## Getting random integers using `random.randint()`
* TODO


## Getting random floats using `random.random()`
* TODO

## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - Dictionaries Overview

## Goals
* Understanding dictionaries in Python
* Accessing and Updating Key Value Pairs
* Basic dictionary methods
* Membership in dictionaries
* Deleting Key/Value Pairs
* Using the `.get()` method to check keys


## Understanding dictionaries in Python
* Dictionaries contain key/value pairs in a mutable, unordered collection.
* Keys must be immutable and unique.
* Dictionaries are declared:
    * Using curly braces `{}`
    * `dict()` constructor
* Syntax: `{key1 : value1, key2: value2, key3 : value3}`


## Accessing and Updating Key Value Pairs
* Access values by using the key as an index:
    * `d[key]`
    * This statement will throw an error if the key is not in the dictionary.
* Keys can be added to dictionaries by:
    * `d[new_key] = new_value`
    * Note that if the key already exists in the dictionary, this syntax will reassign the value to this new_value



Create a text content analyzer. This is a tool used by writers to find statistics such as word and sentence count on essays or articles they are writing.

Write a Python program that analyzes string and compiles statistics on it. Your sentence can end in a `.`, `!` or `?`, do not include punctuation in your words

The program should PRINT using string formatting:
1. The total word count
2. The count of unique words
3. The number of sentences
4. The average sentence length in words (whole number)
5. A list of words used, in order of descending frequency

The program should also `return` all the information in a dictionary
To get your string to check is on the next slide

Use this text:

```python
Mochi is a Maltese. He weighs only 4 lbs even though he is already 6 years old!!! He likes to eat blueberries. Mochi is sleeping. Is Mochi cute? Everyone thinks Mochi is cute!! Couple more lines for testing stdin. Is Disney Tsum Tsum a fun game?! Disney Tsum Tsum is very fun! Mochi is sleeping. Mochi loves Disney Tsum Tsum. Mochi is sleeping again.
```


```python
def word_counter(text_list):
    d = dict()
    out = []

    for word in text_list:
        if word not in d:
            d[word] = 0
        d[word] += 1

    for word, count in d.items():
        out.append((count, word))

    return [word for count, word in sorted(out, reverse=True)]

def text_content_analyzer(text):
    d = {
        'total_word_count': 0,
        'unique_word_count': 0,
        'sentence_count': 0,
        'avg_sentence_len': 0,
        'word_list_desc_freq': []
    }

    text_list = text.replace('.', '').replace('?', '').replace('!', '').lower().split(' ')
    sentences = text.replace('?', '.').replace('!', '.').lower().split('. ')
    sentences = [sentence.replace('.', ' ') for sentence in sentences]

    d['total_word_count'] = len(text_list)
    print(f'Total Word Count: {d['total_word_count']}')

    d['unique_word_count'] = len(list(set(text_list)))
    print(f'Unique Word Count: {d['unique_word_count']}')

    d['sentence_count'] = len(sentences)
    print(f'Sentence Count: {d['sentence_count']}')

    d['avg_sentence_len'] = sum([len(sentences) for sentence in sentences]) / len(sentences)
    print(f'Average Sentence Length: {d['avg_sentence_len']}')

    d['word_list_desc_freq'] = word_counter(text_list)
    print(f'Words in Desc Frequency: {d['word_list_desc_freq']}')

    return d
```


## Basic dictionary methods
* The keys method will return a list of the keys in a dictionary
    * `dct.keys()`
* The values method will return a list of the values in a dictionary
    * `dct.values()`
* The items method will return a list of tuples that contain the key/ value pairs
    * `dct.items()`


## Membership in dictionaries
* Membership for dictionaries
    * `k in dct`
    * `k in dct.keys()`
    * `v in dct.values()`


## Deleting Key/Value Pairs
* In order to remove key/value pairs, you can use the pop method or the del keyword
    * `d.pop('some_key')`
    * `del d['some_key']`
* Create a copy of the original dictionary before changing it by adding and deleting key/value pairs
    * `dictionary.copy()`


## Using the `.get()` method to check keys
* To check and see if a specific key is in a dictionary, you can use the get method
    * Syntax: `dct.get(key, default=None)`

```python
states_caps_dict = {'Georgia': 'Atlanta', 'Colorado': 'Denver', 'Indiana': 'Indianapolis'}
d.get(‘Washington’, ‘Capital not found’)
```




## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - Dictionary Traversal

## Goals
* Traversing a Dictionary
* Copying a Dictionary



## Traversing a Dictionary
* Creating a for loop allows us to iterate through a dictionary’s keys

```python
for key in dictionary:
    print(key)
```

* Combining a for loop with the items method allows us to iterate through both the keys and the values of a dictionary:

```python
for key, value in dictionary.items():
    print(key, value)
```


## Copying a Dictionary
To make a copy of a dictionary you need to use the `.copy()` method
* Syntax: `dct.copy()`
* Err on the side of making copies of dictionaries




Write a function that prompts the user to input numbers separated by dashes ( - ). Your script will take those numbers, and print a dictionary where the keys are the inputted numbers, and the values are the squares of those numbers.

Example: If you inputted the numbers `‘1 - 5 - 8 - 10’`, your script should print `{8: 64, 1: 1, 10: 100, 5: 25}` (remember that dictionaries are unordered, which is why the script might print out the key-value pairs in a different order than the user inputted the numbers).



```python
def square_dict():
    inp = input('Enter numbers separated by dashes: ')
    inp_list = inp.split(' - ')
    d = {}
    for num in inp_list:
        d[int(num)] = int(num)**2
    return d
```








Write a function that takes in a string. Return a dictionary where the keys represent unique characters in the string and the values represent the number of times that character appears in the original string.
s = 'This is a string, we want you to count how many times each unique character appears in this string!'

Docstring and starter code:

```python
def num_chars(s):
    '''
    function that takes in a string and parses through
    identifying how many characters are in each word,
    assuming a whitespace is what separates your words
    parameters:
        s: str - a string

    returns:
        A dictionary, where the keys are the words and the
        values are the number of characters in each word
    '''
    pass
```


```python
def clean_string(string):
    new_string = ''
    alpha = 'abcdefghijklmnopqrstuvwxyz'

    for letter in string.lower():
        if letter in alpha or letter = ' ':
            new_string += letter
    return new_string

def word_letter_count(string):
    d = dict()
    cleaned = clean_string(string)
    word_list = cleaned.split(' ')

    for word in word_list:
        d[word] = len(word)

    return d
```






## Conclusion
* In this lesson we 

## In the Next Lesson...




------------------------------------------------------------------

#  - Collecting with Dictionaries

## Goals
* Dictionaries make excellent collectors




## Dictionaries make excellent collectors
* Sometimes, you will need an accumulator that is a dictionary.
* The accumulator either create a new key value pair or it will add something to the value of an already existing key value pair.
* Syntax for a dictionary counter:

```python
accumulator = {}
for element in some_list:
	if element in accumulator.keys():
		accumulator[element] += 1
	else:
		accumulator[element] = 1
```


## Example: Analyzing vowels, non-vowels, and non-alpha characters
* For any given string, return a dictionary that gives us the number of vowels, the number of non vowels, the number of non-alpha characters.

**Step 1:**
We need to first create a dictionary that we can store all our information in.

```python
d = {'vowels': 0, 'consonants': 0, 'nonalpha': 0}      
```

We can fill our dictionary like this because we know exactly what the question is asking and because we want counts, we can use integer accumulators for our values using addition.

**Step 2:**

```python
d = {'vowels': 0, 'consonants': 0, 'nonalpha': 0}     
```

We now need to iterate over our string and identify each of the three types of characters we are interested in.

How can we identify vowels in a string?

```python
d = {'vowels': 0, 'consonants': 0, 'nonalpha': 0}     
```

We now need to iterate over our string and identify each of the three types of characters we are interested in.

How can we identify vowels in a string?

```python
if char.lower() in ['a', 'e', 'i', 'o', 'u']:
    # do something
```


**Step 2:**

```python
d = {'vowels': 0, 'consonants': 0, 'nonalpha': 0}     
```

We now need to iterate over our string and identify each of the three types of characters we are interested in.

How can we identify non-alphas in a string?


**Step 2:**

```python
d = {'vowels': 0, 'consonants': 0, 'nonalpha': 0}     
```

We now need to iterate over our string and identify each of the three types of characters we are interested in.

How can we identify non-alphas in a string?

```python
elif not char.isalpha():
    # do something
```


**Step 2:**

```python
d = {'vowels': 0, 'consonants': 0, 'nonalpha': 0}     
```

We now need to iterate over our string and identify each of the three types of characters we are interested in.

Based on this, we can use just a regular else statement to cover all other characters



**Step 2:**

```python
d = {'vowels': 0, 'consonants': 0, 'nonalpha': 0}     
```

Let’s put it all together - you now fill in the blanks of how to use our dictionary to accumulate here

```python
if char in ['a', 'e', 'i', 'o', 'u']:
	pass
elif not char.isalpha():
	pass
else:
	pass
```


**Step 2:**

```python
d = {'vowels': 0, 'consonants': 0, 'nonalpha': 0}     
```

Let’s put it all together - you now fill in the blanks of how to use our dictionary to accumulate here

```python
if char in ['a', 'e', 'i', 'o', 'u']:
	d['vowels'] += 1
elif not char.isalpha():
	d['nonalpha'] += 1
else:
	d['consonants'] += 1
```




## Example: Collecting dice rolls
Write a function that take in an integer and will roll a 6-sided dice randomly for that number of times and will update the proportions of each number occurring and update the counts also
* Have your function return:
    * A dictionary of counts
    * A dictionary of dice proportions



What is the first thing we need to do?
Assume we have already

```python
import random
```

What do we need to create?





What is the first thing we need to do?
Assume we have already

```python
import random
```

What do we need to create?

```python
counts = {1: 0, 2: 0, 3: 0, 4: 0, 5: 0, 6: 0}
probs = {1: 0, 2: 0, 3: 0, 4: 0, 5: 0, 6: 0}
total_rolls = 0
```



What is the first thing we need to do?
Assume we have already

```python
import random
```

Now we can iterate over our integer we called in our function and call `random.randint(1,6)` which will return a number randomly 1-6

Based on what that roll is we can update our count dictionary and probability dictionary





What is the first thing we need to do?
Assume we have already

```python
import random
```

Now we can iterate over our integer we called in our function and call `random.randint(1,6)` which will return a number randomly 1-6

Based on what that roll is we can update our count dictionary and probability dictionary

```python
roll = random.randint(1, 6)
counts[roll] += 1
```




What is the first thing we need to do?
Assume we have already

```python
import random
```

Now we can iterate over our integer we called in our function and call `random.randint(1,6)` which will return a number randomly 1-6

Based on what that roll is we can update our count dictionary and probability dictionary.

How do we update the probability dictionary?




Well we know we need to update every value in our probs dictionary, what does that lead you to want to use when we think about iterating over a dictionary?




Well we know we need to update every value in our probs dictionary, what does that lead you to want to use when we think about iterating over a dictionary?

```python
for k, v in probs.items():
```

So now how do we update our probs where the numerator will be updated for the value that the dice rolled and the denominators will be updated for all of our key:value pairs?



Well we know we need to update every value in our probs dictionary, what does that lead you to want to use when we think about iterating over a dictionary?

```python
for k, v in probs.items():
	probs[k] = counts[k]/total_rolls
```

We have parallel dictionaries (like parallel lists) so our keys can be used to access values from both dictionaries!



#### Let’s say we rolled a `5` after rolling a `1`

```python
roll = random.randint(1, 6)
       counts[roll] += 1
       total_rolls += 1
counts = {1: 1, 2: 0, 3: 0, 4: 0, 5: 1, 6: 0}
total_rolls += 1
for k, v in probs.items():
	probs[k] = counts[k]/total_rolls
probs = {1: 1/2, 2: 0/2, 3: 0/2, 4: 0/2, 5: 1/2, 6: 0/2}
```



Now let’s put it all together in a function!

```python
def roll_dice(n_rolls):
   counts = {1: 0, 2: 0, 3: 0, 4: 0, 5: 0, 6: 0}
   probs = {1: 0, 2: 0, 3: 0, 4: 0, 5: 0, 6: 0}
   total_rolls = 0

   for i in range(1, n_rolls+1):
       roll = random.randint(1, 6)
       counts[roll] += 1
       total_rolls += 1
       for k, v in probs.items():
           probs[k] = counts[k]/total_rolls
   return counts, probs
```








## Conclusion
* In this lesson we 

## In the Next Lesson...


------------------------------------------------------------------

#  - `defaultdict` and `Counter` are excellent "convenience" dictionaries

## Goals
* The `defaultdict`datatype provides default values
* The `Counter` datatype is good for counting



## The `defaultdict`datatype provides default values
* TODO


## The `Counter` datatype is good for counting
* TODO


## Conclusion
* In this lesson we 

## In the Next Lesson...


------------------------------------------------------------------

#  - Sets

## Goals
* Understanding the `set` datatype
* Using the list/set trick to remove duplicates
* Set Union and Intersection
* Set Difference



## Understanding the `set` datatype
* Sets are unordered, mutable collections
* Sets will only contain unique elements
* Sets can be declared:
    * Using the set constructor `set()`
* Be careful when declaring empty sets. `{}` defaults to dictionaries.


## Using the list/set trick to remove duplicates
* Sets only hold unique elements.
    * This property is useful for removing duplicates from lists and tuples
    * Do this by casting the `list` or `tuple` to a `set`
* The `set` datatype does not allow duplicates and thus provides a simple way to remove duplicates from a list
* Might not maintain order from the original `list`


```python
lst = ['dog', 'cat', 'cat', 'bird']

lst = list(set(lst))
```


Write a function called `dedupe_in_order` that takes a `list` that may contain duplicates as input and returns a list without duplicates.
* Maintain the order of the elements in the list (do not use the `list/set` trick)


```python
def dedupe_in_order(lst):
    deduped = []

    for element in lst:
        if element not in deduped:
            deduped.append(element)

    return deduped
```



## Set Union and Intersection
* The union and intersection methods in sets are similar to their mathematical analogues.
* The union is a set of all elements in two sets
    * Syntax: `set1.union(set2)`
* The intersection is a set of all the elements that two sets have in common
Syntax: `set1.intersection(set2)`


## Set Difference
* The difference of two sets A - B contains all the elements of set A that are not contained in set B
* Syntax: `set1.difference(set2)`
* `set1.difference(set2)` is different from  `set2.difference(set1)`

```python
l1 = [1, 4, 7, 0, 2, 5, 8]
l2 = [1, 2, 3, 4, 9]
```

* What does the intersection of these two lists return?
* What does the the union of these two lists return?
* What does the difference of `l1 - l2` return?
* What about `l2 - l1`?






```python
str1 = set('Explicit is better than implicit. Simple is better than complex.'.lower().replace('.', '').split(' '))
str2 = set('Complex is better than complicated. Flat is better than nested. Sparse is better than dense.'.lower().replace('.', '').split(' '))
```

* What is the intersection of str1 and str2?
* What is the union of str1 and str2?
* What is the difference of str1 - str2?


```python
{'is', 'better', 'than'}
```

* What is the union of str1 and str2?

```python
{'better', 'implicit', 'complex', 'nested', 'dense', 'beautiful', 'complicated', 'complex', 'explicit', 'than', 'sparse', 'is', 'simple', 'flat', 'ugly'}
```

* What is the difference of str1 - str2?

```python
{'implicit', 'explicit', 'beautiful', 'complex', 'simple', 'ugly'}
```

* What is the difference of str2 - str1?

```python
{'dense', 'sparse', 'complex', 'nested', 'complicated', 'flat'}
```




## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - Tuples

## Goals
* Understanding the `tuple` data type
* Declaring Tuples
* Tuples are Immutable

## Understanding the `tuple` data type
* Tuples are ordered collections
* Tuples are very similar to list with two key differences:
    * Tuples are immutable.
    * Tuples are declared using parenthesis.
* We can index and slice tuples because they are ordered
* Tuples have two methods associated with them: count and index
* Functions return tuples when returning more than one item


## Declaring Tuples
* Tuples can be declared in three ways:
    * `tup = (1, 2, 3)`
    * `tup = tuple([1, 2, 3])`
    * `tup = 1, 2, 3`
* For single elements tuples:
    * `tup = (1,)`
    * `tup = tuple([1])`
    * `tup = 1,`


## Tuples are Immutable
* Once a tuple is declared, it generally can’t be changed in anyway
    * However, if an element of a tuple is mutable, the element can be changed
* Tuples hold references to all the objects they contain, rather than the objects themselves.




Write a function that has two arguments that are both tuples. Return a single tuple that is the combination of the two original tuples that skips every other element in reverse.
* Say `tuple1 = (12, 14, 16, 18)` and `tuple2 = (3, 5, 7, 9)`:
* The result would be `(9, 5, 18, 14)`

```python
def function_name(tuple1, tuple2):
   pass
```


## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - Comprehensions

## Goals
* Understanding Comprehensions
* List Comprehensions
* List Comprehension w/ if statement
* List Comprehension w/ if else statement
* `dict` Comprehension
* `set` Comprehension


## Understanding Comprehensions
```python
[f(x) for x in sequence]

[f(x) for x in sequence if condition]

[f(x) if condition else g(x) for x in sequence]

{key:value for x in sequence}
```



## List Comprehensions

```python
new_lst = []
for i in old_lst:
    new_lst.append(i**2)

new_lst = [ i ** 2 for i in old_lst ]
```

1. Write a list comprehension of this list to get the len of each item, if an item doesn't have a len, make sure to change that item to a string before you take len.
    * `L1 = ['hello', 'goodbye', [1,2,3], 44]`

```python
L1 = ['hello', 'goodbye', [1,2,3], 44]
l1 = [len(item) if not isinstance(item, (int, float, complex, bool)) else len(str(item)) for item in L1]
```


Create a function that will check to see if a book is in a library and if it isn’t, then update your library with the book and let the user know it was a new book, else tell the user that the book was not new.  (Remember capitalization matters) Return your library as a list
    a. Try this if your library was a list - use list methods
    b. Try this if your library was a set - use set methods

```python
def book_update(new_book, library):
	pass
```

```python
library = ['Pedagogy of the Oppressed', 'Consciencism', 'Neo-Colonialism', 'Pathologies of Power', 'White Malice', 'The Jakarta Method', 'An Indigenous Peoples\' History of the United States', 'Braiding Sweetgrass', 'Journal of an Ordinary Grief']
```

Check to see if your library has these books:

```python
'journal of an ordinary grief', 'Consciencism', 'The Jakarta method', 'Make Rojava Green Again'
```


```python
def book_update(new_book, library):
    if new_book.lower() in [book.lower() for book in library]:
        print(f'Your book, {new_book}, is in the library')
        return library
    else:
        print(f'Your book, {new_book}, is new!')
        if isinstance(library, list):
            new_lib = library[:]
            new_lib.append(new_book)
            return new_lib
        elif isinstance(library, set):
            new_lib = library.copy()
            new_lib.add(new_book)
            return list(new_lib)
```








## List Comprehension w/ if statement

```python
new_lst = []
for i in old_lst:
	if i > 10:
        new_lst.append(i**2)

new_lst = [i ** 2 for i in old_lst if i > 10]
```




## List Comprehension w/ if else statement

```python
new_lst = []
for i in old_lst:
	if i > 10:
        new_lst.append(i**2)
    else:
	    new_lst.append(i//2)

new_lst = [i ** 2 if i > 10 else i//2 for i in old_lst]
```

2. Write a list comprehension that takes in a list of positive integers and adds 100 to a single digit number else it will subtract 100 from the number.
    * `L2  = [1, 5, 8, 100, 43, 254, 1000, 3, 0, 88888]`

```python
L2  = [1, 5, 8, 100, 43, 254, 1000, 3, 0, 88888]
l2 = [n + 100 if abs(n / 10) < 1 else n - 100 for n in L2>]
```



## `dict` Comprehension

```python
new_dict = {}
for i in old_lst:
	new_dict[i] = i**2

new_dict = {i:i**2 for i in old_lst}
```

3. Write a dictionary comprehension of a dictionary, making the values the keys and the keys the values
    * `D1 = {'Apple':5, 'Pear': 10, 'Banana':2, 'Orange': 1}`

```python
D1 = {'Apple':5, 'Pear': 10, 'Banana':2, 'Orange': 1}
d1 = {v: k for k, v in D1.items()}
```

4. Write a dictionary comprehension of a dictionary, adding '_test' to the keys and finding the remainder of the value when divided by 13
    * `D2 = {'a': 540, 'b': 222, 'c':88, 'd':1000,'e':13}`

```python
D2 = {'a': 540, 'b': 222, 'c':88, 'd':1000,'e':13}
d2 = {k+'_test': v%13 for k, v in D2.items()}
```



## `set` Comprehension




## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - Thinking Algorithmically: GCD and LCM

## Goals
* Understanding the concept of an _algorithm_
* Greatest Common Divisor
* Least Common Multiple
*



## Understanding the concept of an _algorithm_


## Greatest Common Divisor
* include `math.gcd` 

## Least Common Multiple
* include `math.lcm`







## Conclusion
* In this lesson we 

## In the Next Lesson...


------------------------------------------------------------------

#  - Thinking Algorithmically: Counting and Permutations

## Goals
* Demonstrate and explain the concept of a permutation
* Code the `permutations(n,k)` function
* Discovering permutations through counting
* Coding Permutations through a reductive approach
* Coding Permutations using [Heap's Algorithm](https://en.wikipedia.org/wiki/Heap%27s_algorithm)





## Demonstrate and explain the concept of a permutation 
* $nPk = \frac{n!}{(n-k)!}$
* A **permutation** can be thought of as an arrangement of a number of items
* $nPk$
    * where $n$ is the number of possible items
    * $k$ is how many of those items to arrange
* Note: **ORDER MATTERS**



Consider selecting 3 kittens from a box, without replacement:
* In the first selection, there are 3 kitten choices
* In the second selection, there are 2 kitten choices
* In the thrid selection, there is only 1 kitten choice

Possible Sequences:

| Selection One | Selection Two | Selection Three|
|---------------|---------------|----------------|
|  <center>1</center> | <center>2</center> | <center>3</center>|
|  <center>1</center> | <center>3</center> | <center>2</center>|
|  <center>2</center> | <center>1</center> | <center>3</center>|
|  <center>2</center> | <center>3</center> | <center>1</center>|
|  <center>3</center> | <center>1</center> | <center>2</center>|
|  <center>3</center> | <center>2</center> | <center>1</center>|




## Code the `permutations(n,k)` function
* Consider that this function is based on the `factorial` function, so we'll write that again first
* This function will only answer the question "How many permutations are there of k of these n objects?"

```python
def factorial(num):
    prod = 1
    for n in range(2, num+1):
        prod *= n
    return prod


def permutations(n, k):
    return int(factorial(n) / factorial(n-k))
```

Slightly more optimized:

```python
def permutations(n, k):
    perm = 1
    for i in range(n, n-k, -1):
        perm *= i
    return perm
```



## Discovering permutations through counting
$nPk = \frac{n!}{(n-k)!}$

If we consider $n$ to be the base of a counting system, then we can determine all permutations $k$ by a counting/reduction approach.

1. Count in base $n$ system
* ex: $n=3$

000 010 020 100 110 120 200 210 220
001 011 021 101 111 121 201 211 221
002 012 022 102 112 122 202 212 222
                            
2. **Reduce** counts that have duplicate items

000 010 020 100 110 **120** 200 **210** 220
001 011 **021** 101 111 121 **201** 211 221
002 **012** 022 **102** 112 122 202 212 222

3. Consider $k$ items

ex: $k=3$

|012 | 021 | 102 | 120 | 201 | 210| 
|----|-----|-----|-----|-----|-----|

ex: $k=2$
| 12 | 21 | 02 | 20| 01|  10|
|-----|-----|-----|-----|-----|-----|

ex: $k=1$ 
| 2 | 1 | 0 |
|-----|-----|-----|




## Coding Permutations through a reductive approach
1. Count in Base $n$ system
2. Reduce space by removing outcomes with duplicate items

Five pets and 5 beds. What are all the ways that you can
arrange those 5 pets in 5 beds?

```python
base_5 = ['bat', 'cat', 'frog', 'eel', 'hamster']

animals_counting = []

for an1 in base_5:
    for an2 in base_5:
        for an3 in base_5:
            for an4 in base_5:
                for an5 in base_5:
                    animals_counting.append([an1, an2, an3, an4, an5])

# for an_number in animals_counting:
#     print(an_number)

animal_perms = []

for an_number in animals_counting:
    perm = True

    for an in an_number:
        if an_number.count(an) > 1:
            perm = False
            break
    if perm == True:
        animal_perms.append(an_number)

# for an_number in animal_perms:
#     print(an_number)
```


## Coding Permutations using [Heap's Algorithm](https://en.wikipedia.org/wiki/Heap%27s_algorithm)
* Relies on swapping

Non-Recursive Algorithm from [Wikipedia](https://en.wikipedia.org/wiki/Heap%27s_algorithm):

```
procedure generate(n : integer, A : array of any):
    //c is an encoding of the stack state. 
    //c[k] encodes the for-loop counter for when generate(k - 1, A) is called
    c : array of int

    for i := 0; i < n; i += 1 do
        c[i] := 0
    end for

    output(A)
    
    //i acts similarly to the stack pointer
    i := 0;
    while i < n do
        if  c[i] < i then
            if i is even then
                swap(A[0], A[i])
            else
                swap(A[c[i]], A[i])
            end if
            output(A)
            //Swap has occurred ending the for-loop. Simulate the increment of the for-loop counter
            c[i] += 1
            //Simulate recursive call reaching the base case by bringing the pointer to the base case analog in the array
            i := 0
        else
            //Calling generate(i+1, A) has ended as the for-loop terminated. Reset the state and simulate popping the stack by incrementing the pointer.
            c[i] := 0
            i += 1
        end if
    end while
```

We'll write this version close to the algorithm on wikipedia


```python
def swap(lst, idx_1, idx_2):
    lst_ = lst.copy()
    temp = lst_[idx_2]
    lst_[idx_2] = lst_[idx_1]
    lst_[idx_1] = temp
    return lst_


def heaps_non_recursive(lst, k):
    # avoid modifying parameter
    lst_copy = lst.copy()

    # holds stack state
    c = [0] * len(lst)

    # collect permutations, collect initial perm
    perms = [lst_copy[:k]]

    i = 0 # acts like a stack pointer
    while i < len(lst_copy):
        if c[i] < i:
            if i % 2 == 0:
                lst_copy = swap(lst_copy, 0, i)
            else:
                lst_copy = swap(lst_copy, c[i], i)
            
            if lst_copy[:k] not in perms:
                perms.append(lst_copy[:k])

            # incr the counter
            c[i] += 1

            # reset i
            i = 0
        else:
            # reset state of count state at i
            c[i] = 0
            i += 1

    return perms
```



## Conclusion
* In this lesson we 

## In the Next Lesson...


------------------------------------------------------------------

#  - Thinking Algorithmically: Combinations

## Goals
* Understand combinations
* Code the Combinations function
* Discovering combinations through counting
* Discovering Combinations through random sampling
* Implementing the `itertools` combinations algorithm



## Understand combinations
* $nCk = \frac{n!}{((n-k)! k!)}$
**ORDER DOESN'T MATTER**
Combinations can be thought of as a reduction of the Permutations space, as order doesn't matter.

**Cardinal Example of a Combinations Prob**: 
How many different 5 card hands in a game of poker?
It doesn't matter how you arrange the cards in your hand


## Code the Combinations function

$$
nCk = \frac{n!}{((n-k)! k!)}
$$

```python
def combinations(n, k):
    return int(factorial(n) / (factorial(n-k) * factorial(k)))

# Slightly more optimal:
def combinations(n, k):
    perm = 1
    for i in range(n, n-k, -1):
        perm *= i
    return int(perm / factorial(k))
```

## Discovering combinations through counting
1. Make a counter list, treating the elements as the base in a number system
2. Create a sublist of the counter list that is the Permutations
3. Sort the elements of the sublist
4. Remove any duplicate sublists


Ex:

Out of a set of 11 basketball players, only
5 can be on the court at a time. What are all
the combinations possible for that basketball team.

```python
num_combs = combinations(11, 5)

def basketball_combs():
    eleven_nums = range(1, 11+1)

    # every arrangement of 5
    possible_five = []

    for i in eleven_nums:
        for j in eleven_nums:
            for k in eleven_nums:
                for l in eleven_nums:
                    for m in eleven_nums:
                        possible_five.append([i,j,k,l,m])

    # for five in possible_five:
    #     print(five)

    perms = []

    for five in possible_five:
        if len(list(set(five))) == 5:
            perms.append(five)

    # for five in perms:
    #     print(five)

    combs = []

    for five in perms:
        sorted_five = sorted(five)

        if sorted_five not in combs:
            combs.append(sorted_five)
    
    return combs

# for five in basketball_combs():
#     print(five)
```


## Discovering Combinations through random sampling
#### An expensive Sampling Approach

We can sample 5 players from our list of 11,
can continue to build combinations until we reach
11C5 combinations

```python
from random import choice

def basketball_combs_samp(team_size=11, num_players=5):
    combs = []

    player_range = range(1, team_size+1)

    while len(combs) < combinations(team_size, num_players):
        player_comb = []

        while len(player_comb) < num_players:
            player_num = choice(player_range)

            if player_num not in player_comb:
                player_comb.append(player_num)

        player_comb = sorted(player_comb)

        if player_comb not in combs:
            print(player_comb)
            combs.append(player_comb)
    return combs


team_size = 11
num_players = 5

print(len(basketball_combs_samp(team_size, num_players)))
print(combinations(team_size, num_players))
```



## Implementing the `itertools` combinations algorithm
* Describe the `itertools` module

* Notice the `yield` keyword, which allows for the creation of a [generator](https://wiki.python.org/moin/Generators) object. 

```python
def combs_alg_from_itertools(lst, k):
    # get a frozen version of the input, 
    lst_frozen = tuple(lst)
    n = len(lst_frozen)
    
    combs = []

    # fault control
    if k > n:
        return


    indices = list(range(k))
    yield tuple(lst_frozen[i] for i in indices)
    while True:
        for i in reversed(range(k)):
            if indices[i] != i + n - k:
                break
        else:
            return
        indices[i] += 1
        for j in range(i+1, k):
            indices[j] = indices[j-1] + 1
        yield tuple(lst_frozen[i] for i in indices)
```


## Conclusion
* In this lesson we 

## In the Next Lesson...


------------------------------------------------------------------

#  - Generator functions and `yield`

## Goals
* 


## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - `map`, `filter`, `reduce`

## Goals
* 


## Conclusion
* In this lesson we 

## In the Next Lesson...




------------------------------------------------------------------

#  - Installing Python locally using Anaconda

## Goals
* Understand Anaconda as a "package manager"
* Install Anaconda on Windows
* Install Anaconda on Mac OSX
* Install Anaconda in Linux
* Create an Anaconda environment
* Install packages: `numpy`, `pandas`, and Jupyter notebooks


## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - Using text editors to edit Python code

## Goals
* Install VSCode
* Write Python in VSCode and run that code in the terminal
* Install Jupyter using Anaconda (if you haven't already)
* Write code using Jupyter notebooks in the browser



## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - Basic File Input Output and using `try / except`

## Goals
* Using `with` and `open` to read in a text file
* Understanding `try / except` in Python
* Writing a simple logging script, using `datetime` and file i/o




## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - Simple Project: Write a Simple CBT Script that saves to a journal

## Goals
* Adapt a basic Cognitive Behavioral Therapy protocol into a Python script




## Conclusion
* In this lesson we 

## In the Next Lesson...


------------------------------------------------------------------

#  - Using `pathlib` to traverse folders and files

## Goals
* Understand the usage of `pathlib`
* Use `pathlib` to list and rename all image files in a directory of mixed files




## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - A crash course in `numpy`

## Goals
* Introducing `numpy` arrays
* Creating arrays from lists
* Simple mathematical operations on `numpy` arrays
* `numpy` mathematical methods




## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - Fun with Bitfields, using `numpy` arrays and Bitwise operations to create Bitfield Animations

## Goals
* Bitwise operators (expand into individual operators)
* Understanding the concept of a bitfield
* Creating a bitfield images using `numpy` and `skimage`
* Stitching images together into a video using `cv2`




```python
import cv2
import numpy as np
import glob

img_files = []
for filename in glob.glob("/bitfield-images/*.png"):
    img = cv2.imread(filename)
    height, width, layers = img.shape
    size = (width, height)
    img_files.append(img)

out = cv2.VideoWriter('bitfield.avi', cv2.VideoWriter_fourcc(*'DIVX', 15, size))

for i in range(len(img_array)):
    out.write(img_files[i])

out.release
```


## Conclusion
* In this lesson we 

## In the Next Lesson...


------------------------------------------------------------------

#  - Manipulating Images using Sci-Kit Image

## Goals
* A quick introduction to Sci-Kit Image
* Understand images as multi-dimensional arrays
* Survey image filters in Sci-Kit Image




## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - Introduction to Pandas for Data Analysis

## Goals
* Understand Pandas dataframes as a tool for analysing tabular data
* Creating and populating dataframes
* Importing data into Pandas
* Simple statistics with Pandas



## Conclusion
* In this lesson we 

## In the Next Lesson...


------------------------------------------------------------------

#  - Pandas Filtering and Group By Operations

## Goals
* 



## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - Pandas and Matplotlib for Data Visualization

## Goals
* 



## Conclusion
* In this lesson we 

## In the Next Lesson...




------------------------------------------------------------------

#  - Utilizing `lambda` Expressions

## Goals
* Using `lambda` expressions as a general pattern
* Utilizing `lambda` expressions on Pandas dataframes



## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - Performing SQL operations using `duckdb` and Python

## Goals
* 



## Conclusion
* In this lesson we 

## In the Next Lesson...




------------------------------------------------------------------

#  - Simple Analytic Modeling

## Goals
* 



## A Simple, General Analytic Approach
Considering a stochastic process, model or create a sample space and analyze:
1. Synthesize outcomes, model a phenomenon, look at data
2. Observe or interpret values
3. Answer questions



## Analysis through Counting
This can often be thought of as an "exhaustive" approach, for discrete outcomes, or a "bins" approach for continuous outcomes.


# Counting Example:
In a particular table top game, when in a battle, a player first rolls a 36-sided die, then pulls a card from a standard deck of cards. Finally, the player flips a coin three times.


### 1. Synthesize Outcomes by counting

```python
rolls = range(1, 36+1)

suits = ['Spades', 'Clubs', 'Diamonds', 'Hearts']
card_nums = ['Two', 'Three', 'Four', 'Five', 'Six', 'Seven', 'Eight', 'Nine', 'Ten', 'Ace', 'Jack', 'Queen', 'King']

cards = []

for suit in suits:
    for card in card_nums:
        cards.append(f'{card} of {suit}')

# for card in cards:
#     print(card)

# print(len(cards))

coin_flips = []
for flip1 in ['T', 'H']:
    for flip2 in ['T', 'H']:
        for flip3 in ['T', 'H']:
            coin_flips.append([flip1, flip2, flip3])


S = []
for roll in rolls:
    for card in cards:
        for flip in coin_flips:
            S.append([roll, card, flip])

```


### 2. Observe/Interpret values in a list

```python

for outcome in S:
    print(outcome)

print(len(S))
```




## 3. Answer Questions

Suppose that the 36-sided die represents the range of an attack. To hit an opponent, that opponent must be in range, for example, a roll of 29 will potentially hit another player 29 or less spaces away. The card represents the amount of damage that the attack will commit. In order to actually inflict damage, two of the three coin flips must be Heads.

**What is the probability of hitting an opponent that is 18 spaces away?**
* Write a code snippet that will provide the probability rounded to 3 places




```python
hits = []
range_to_hit = 18

for outcome in S:
    if outcome[0] >= range_to_hit and outcome[2].count('H') == 2:
        hits.append(outcome)

print(f'proba: {round(len(hits) / len(S), 3)}')
```



## Random Sampling Example
* Can be used to approach a theoretical distribution and estimate parameters of that distribution

Consider invitations sent for a party (as if). 20 invitations are sent out. Each guest can possibly bring up to ten guests (with equal probability of between not going and 10 guests). No matter what, at least one person (you) will be at the party. 



## 1. Synthesize outcomes, model a phenomenon, look at data

```python
from random import choice

def num_attendees():
    num_peeps = 1

    for _ in range(20):
        num_peeps += choice(range(0, 11+1))

    return num_peeps
```



## 2. Observe or interpret values
* can pack into dictionary

```python

outcomes = dict()

for _ in range(100000):
    attending = num_attendees()

    if attending not in outcomes:
        outcomes[attending] = 0
    outcomes[attending] += 1

for k, v in sorted(outcomes.items()):
    print(f'{k}: {v}')
```

Notice that we are very unlikely to get less than 40 guests, and it is near impossible to get no guests in this scenario.



## 3. Answer questions

Given a sample of outcomes, provide code to deliver an estimated probability that between 80 and 90 people will attend the party. Round the result to 3 decimal places.




```python
eighty_to_ninety = 0
total = sum(outcomes.values())

for attendees in range(80, 90+1):
    eighty_to_ninety += outcomes[attendees]

print(f'{round(eighty_to_ninety/total,3)}')
```




# Closed Formula Example

Consider a collection of spherical containers used to hold super gumballs of radius 1 inch. These containers range from 4 inch in radius up to 100 inches in radius. Consider a rough count of gumballs per sphere.

Spherical Volume:

$$
V = \frac{4}{3}\pi r^3
$$



## 1. Synthesize outcomes, model a phenomenon, look at data
$$
V = \frac{4}{3}\pi r^3
$$

```python
from math import pi

def spherical_volume(r):
    return (4/3) * pi * r**3
```



## 2. Observe or interpret values
* Packing rough gumball count of spheres related to 

```python
def gumball_capacity():
    d = dict()

    for r in range(4, 100+1):
        d[r] = int(spherical_volume(r) / spherical_volume(1))
    return d

for r, v in gumball_capacity().items():
    print(f'{r}: {v}')
```

Note that the number of gumballs that can be held in a sphere increases dramatically with the increase in volume of the sphere.




## 3. Answer questions

Write a function called `get_sphere()` that takes in a number of gumballs and returns the radius of sphere necessary to accommodate that inventory.




```python
def get_sphere(gumball_inventory):
    d = gumball_capacity()

    for k, v in d.items():
        if v > gumball_inventory:
            return k
    
    return 'No appropriate sphere available'
```



## Conclusion
* In this lesson we 

## In the Next Lesson...


------------------------------------------------------------------

#  - PROJECT: [describing Emergences of Euler's Number $e$](https://www.youtube.com/watch?v=Mw52nDwPh8k&list=PL5T50pwCrPUrIxYqP8jC8ctUUItW6csXG)

## Goals
* 



## Conclusion
* In this lesson we 

## In the Next Lesson...



------------------------------------------------------------------

#  - PROJECT: Creating a Python Script that splits a long lecture on relative silences

## Goals
* 



## Conclusion
* In this lesson we 

## In the Next Lesson...