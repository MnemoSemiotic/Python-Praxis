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
    * Existentially, helps you to become a better problem-solver in a safe (sandboxed) way


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
    * Write a bunch of functions, that are often concerned with "counting"
    * Classes, class structure, and methods
    * Basics in Numpy and Pandas, with applications on images and data
        * these will be extended in their own courses, as well, so just enough to be dangerous
    * A basic example of machine learning and how to think about this example more generally
    * Develop a simple application
* The general format overall will be looking at a problem, solving it, then explaining all the components of the solution. 


## Big Picture
* Intent is to include this course in a series, with courses that explore 
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

## Making a Simple Dice Roller

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
* Understand the numeric data types `int` and `float` and their basic operators
* Write functions that perform simple, repeatable mathematical operations


## What is a data type?
* a data type is simply the type of a given value
    * for example the number 4 is the `int` data type, which stands for "integer", which represents whole numbers 


## What are the numeric data types?
* `int` represents whole numbers, like 1, 3, -54, 997, and so on
* `float` represents numbers that have decimal points
* `bool` represents only the values `True` or `False`
* `complex` represents values that are imaginary numbers (we won't go over this here, but just understand it exists)

** We will cover only `int` and `float` in this lesson





### the `type()` function

* the `type()` function will tell you the type of a value
* run

```python
print(type(23))
```

will show a result of `<class 'int'>`


### What is a class?
* This is a bigger question that we'll cover later when begin to write our own classes.
* For now, think of a class as a definition of a data type. 
    * The data types that are built in to Python are defined somewhere in the form of a class.
    * That means that we can eventually start defining our own data types by writing classes




## Integers: `int`
* We can think integers simply as whole numbers.
* Any mathematical operation that we perform on whole numbers we can perform here.

### Adding (`+`), Subtracting (`-`), Multiplying (`*`), Dividing (`/`), Exponentiation (`**`)

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

Or may divide unevenly, yielding a decimal value

```python
print(16 / 3)
```



## Special operators: Modulo (`%`) and Floor Division (`//`)
 
### Modulo (`%`) will give you the remainder of a division

```python
print(8 % 2)
print(16 % 3)
```

Notice that modulo in these two cases (with integers) will give a non-decimal result



### Floor Division (`//`) will give you the result of division, rounded down to the nearest integer

```python
print(8 // 2)
print(16 // 3)
```

## Order of Operations
* Keep in mind that Python will use our normal order of arithmetic operations, what we often call PEMDAS.
    * Parentheses, Exponents, Multiplication/Division, Addition/Subtraction

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
* All the same mathematical operations that are used for integers may be used for floats

### Adding (`+`), Subtracting (`-`), Multiplying (`*`), Dividing (`/`), Exponentiation (`**`) with floats
* notice that the result of these basic mathematical operations will result in floats, even when the result should be a whole number
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

Given how floats are stored in memory, they may not be an exact result.


### Float floor division 
* just as with other operations, using the floor division with two floats will result in a `float`.

```python
print(5.0 // 2) # --> 2.0

print(4.0 // 2) # --> 2.0
```

## Casting: using `int()` and `float()` to convert a number
* In Python programming, **casting** refers to taking one data type and converting it to another data type by using the function related to the target data type.

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




## Defining Mathematical Functions using Python
* writing functions makes it easier to reproduce mathematical operations, without having to write everything out.
* notice that these functions will `return` values, and, in order to see those values in the output, we will need to print what the function returns
* Try to solve these on your own before looking at the solution (if watching, pause, try, and go from there).


### Circumference of a Circle

$$
C = 2 \pi r
$$

```python
def circumference_of_a_circle(radius):
    return 2 * 3.14159 * radius

print(circumference_of_a_circle(radius=2))
print(circumference_of_a_circle(radius=3))
print(circumference_of_a_circle(radius=4))
print(circumference_of_a_circle(radius=5))
```

### Area of a Circle

$$
A = \pi r^2
$$

```python
def area_of_circle(radius):
    return 3.14159 * radius**2

print(area_of_circle(radius=2))
print(area_of_circle(radius=3))
print(area_of_circle(radius=4))
print(area_of_circle(radius=5))
```

### Volume of a Sphere

$$
V = \frac{4}{3} \pi r^3
$$

```python
def volume_of_circle(radius):
    return (4/3) * 3.14159 * radius**3

print(volume_of_circle(radius=2))
print(volume_of_circle(radius=3))
print(volume_of_circle(radius=4))
print(volume_of_circle(radius=5))
```

### Area of a Triangle

$$
A = \frac{1}{2} b h
$$

```python
def area_of_triangle(base, height):
    return (1/2) * base * height

print(area_of_triangle(1, 2))
print(area_of_triangle(2, 3))
print(area_of_triangle(3, 4))
print(area_of_triangle(4, 5))
```

# Conclusion
* The `int` and `float` data types are used to represent whole numbers and numbers with decimals, respectively. 
* Basic math operations, such as addition, subtraction, multiplication, division, and exponentiation, can be performed simply, and will follow the general PEMDAS order of operations
* Additionally, there are two special operations that you will often use when programming, the modulo (`%`) and floor division (`//`) operations.
* Mathematical operations that you will write repeatedly can be defined in functions.

## In the Next Lesson:
* Using Python as a calculator



------------------------------------------------------------------


# 004 - Mathematical Functions: Using Python as a Calculator
## Goals:
* Start using Python in your everyday life, as a calculator
* Start using comments to ignore bits of code
* Importing mathematical functions from the `math` module
* Define more custom mathematical functions

## Why use Python as a calcluator?

When first learning to program, it's important that you get a lot of repetition. It will be very helpful to use Python as a calculator whenever you can. Instead of grabbing a traditional calculator, simply use [repl.it](https://repl.it), or a python terminal to figure out answers to your mathematical questions.

An advantage of using a text editor and building your math operations in Python, is that you can keep a record of what you've tried. You can comment out some lines of code, and leave others, as we'll see below.


# Conclusion
* 

## In the Next Lesson:
* 

