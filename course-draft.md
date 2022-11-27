# 000 - Introduction - What to expect from Python Praxis

## Goals:
* Accessible, Queer and "Leftist" series of courses in Data Analysis and Science
    * Why such a course is helpful or necessary
* Establish a culture where programming is a form of literacy, and is accessible to all who want to develop that literacy
* Scope of Python Praxis
* Big Picture

## Who am I
* 

## Why a "Leftist, Queer" series of technical courses?
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
* I'll do my best to tie things into the real world, bc what I've seen and experience as "successful" learning, has been the result of meaningful application, not theory
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

# 001 - A Demo: Rolling the Dice

## Goals:
* Give a simple introduction to programming
* Don't worry if you don't understand this lesson now, all concepts will be broken down in subsequent lessons
* Introduction to an immediately available Python environment using [repl.it](https://repl.it)


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


# Conclusion
* Programming can be simply defining a repeatable set of steps
* Here we created some simple dice rolling functions
    * Working code is more important than clean code.
    * in other words: It's ok to write code in a way you understand, and then refine it later if necessary


## In the Next Lesson...












---------------------------------------------------------------------------------


# 002 - First Steps: A Few Simple Programs

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


# 003 - Data Types: Numeric data types and operations

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


------------------------------------------------------------------


# 004 - Defining Mathematical Functions and using Python as a Calculator


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



# Conclusion
* The `int` and `float` data types are used to represent whole numbers and numbers with decimals, respectively. 
* Basic math operations, such as addition, subtraction, multiplication, division, and exponentiation, can be performed simply, and will follow the general PEMDAS order of operations
* Additionally, there are two special operators that you will often use when programming, modulo (`%`) and floor division (`//`)
* Many mathematical functions can be found in the built-in `math` module
* Mathematical operations that you will write repeatedly can be defined in functions.
* TODO: verify conclusion is complete


## In the Next Lesson...






------------------------------------------------------------------

# 005 - Declaring Variables, Incrementing Variables, Booleans, Checking Equality, and Applying logic


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

# 006 - Scalar types are immutable, the `None` Type, Type Inference, Duck Typing, Checking and Comparing Data Types


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

# 007 - A Brief Introduction to Strings in Python


## Goals:
* Understand the basics of the string `str` type
* Understand basic string concatenation
* Interpolation using f-strings and `.format()` when using the `print()` function
* Capitalizing, Lower-casing, and Upper-casing
* Checking for substrings in strings using `in`
* Extracting substrings from strings using string indexing


## Strings
* A string `str` is an object that acts as a sequence of characters.
* Declare a `string` using quotes 
* Note we will talk more extensively about the `string` type in later lectures


## String Concatenation using the `+` operator
* Can **concatenate** a `string` with another `string` using the `+` operator


## Interpolation using f-strings and `.format()`
* f-strings are an easy way to interpolate a value into a string
    * defined by putting an `f` in front of quotes: `f'some text'`

```python
state = 'Alaska'

print(f'{state} is one of the states in the US')
```

* `.format`
* TODO


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

# 008 - Beginning Control Flow with `if / elif / else`

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

# 009 - Let's talk about Python Functions


##  Goals
* Understanding what a function is in Python
* Function _parameters_ and _arguments_
* Set _default arguments_ in a function
* `print()` vs `return`
* Understanding `global` vs Local Scope


## What are functions in Python?
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



# Conclusion
* In this lesson we 

## In the Next Lesson...




------------------------------------------------------------------

# 010 - Introducing Lists in Python

##  Goals




# Conclusion
* In this lesson we 

## In the Next Lesson...




------------------------------------------------------------------

# 011 - Introducing Lists in Python

##  Goals