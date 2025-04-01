  

How to install git bash in windows, nothing just download this and install this in your windows

What are shells and Command interfaces like Prompt and what is Its use

In Linux—> Bash —> we can command

[https://youtu.be/FpljIU9Z-f8?si=85fCg6JZHLmVLbdD](https://youtu.be/FpljIU9Z-f8?si=85fCg6JZHLmVLbdD)

What is A Kernel ??

[https://youtu.be/mycVSMyShk8?si=CDc4FamHqDDO7-HX](https://youtu.be/mycVSMyShk8?si=CDc4FamHqDDO7-HX)

  

What are the tasks of GUI?

[![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSKNravtFqrJVak-Gq66aKkG-y9gxEuF9VA4Y4vZmNF&s)](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSKNravtFqrJVak-Gq66aKkG-y9gxEuF9VA4Y4vZmNF&s)

The GUI **allows the user to operate the system through icons, drop-down menus, windows and a clicking device**.  
The GUI avoids the user having to memorize and use complex functions,  
commands and options, thereby simplifying and enhancing the user  
experience.  

**In esc mode when using python through vim👇👇 Remember only in Vim mode while insert through i**

:set number — To get the numbered lines for the code

:set nonumber — to remove numbered programing lines

:syntax on — To bring in the colours in Code

:syntax off — To Uncolour the code and make it in simple text.

What Is VIM

Vim is a text editor for Unix that comes with Linux, BSD, and macOS. It is known to be fast and powerful, partly because it is a small program that can run in a terminal (although it has a graphical interface). It is mainly because it can be managed entirely without menus or a mouse with a keyboard.

In all POSIX systems, Vim is the default fallback editor. Vim is sure to be open, whether you have just installed the operating system, or you have booted into a minimal system repair environment, or you are unable to access any other editor. While you can switch out other tiny editors on your systems, such as GNU Nano or Jove, it's Vim that's all but guaranteed to be on every other system in the world.

![[/Untitled 2.png|Untitled 2.png]]

  

[[Functions And its Use]]

[[Shortcuts for Bash]]

  

This is a lot of shortcuts too -

![[Untitled.pdf]]

What is a GUI

A graphical user interface (GUI) is **a desktop interface that allows you to communicate with computers**.

  

What are packages in Pyhton

Packages are an essential building block in programming. Without packages, we’d spend lots of time writing code that’s already been written. Imagine having to write code from scratch every time you wanted to parse a file in a particular format. You’d never get anything done! That’s why we always want to use packages.

  

What is UNIX

Introduction to Unix  
 The operating system we will use is Linux  
 Linux is a variant of Unix  
 It is a general-purpose, time-sharing operating system  
 Unix philosophy:  
 Write programs that do one thing and do it well  
 Write programs that work together  
 Write programs that handle text streams as a universal interface  
 UNIX began in 1969  
“If you want to be successful working with data, you want to work in an environment that encourages  
you to devise your own solutions. You want to work on Unix” (Janert, 2010)  

  

  

What is Linux

Linux  
 A variant of Unix  
 Open source and free operating system  
 Began in 1991 as a fun project by Linus Torvalds  
 Provides a kernel (base operating system) with GNU OS utilities  
 Ported to run on almost anything  
 Used by:  
 most web servers  
 almost all supercomputers  
 more than 95% of the servers and desktops at large animation and visual effects companies  
 basis for Android, ChromeOS  

  

What is a Prompt

In programming languages, a prompt usually refers to **a message or text displayed to the user to solicit input or provide instructions**.

![[Screenshot_(12).png]]

  

![[Screenshot_(14).png]]

## Variables in Python  
 Used to store values to use elsewhere in a program  
 The variables in the example were:  
 concession – “Y” or “N”  
 multi – “Y” or “N”  
 fare – a number with 2 decimal places  
 We don’t need to tell Python which type – it works it out for itself (unlike Java and others)  
 Python created concession and multi as strings and fare as a float  
 Note: They are not restricted to Y/N or to 2 decimal places  

### Assignment  
 Assignment lets us put a value into a variable  
 The value helps Python understand what type it should be:  
 name = “Fundamentals of Programming”  
… is a string  
 result1 = 42  
… is an int  
 result2 = 42.0  
… is a float  
 concession = True  
… is a boolean  
 Can do more than one on a line: a, b = 2, 3  
 To output the type of a variable/value can use the type(name)function  

## Types for variables  
 Numeric  
 int – positive, negative and zero. Size limited by computer  
 int_num = 42  
 float – positive, negative and zero. Force float type by adding .0  
 float_num = 42.0  
 complex – float with real and imaginary part.  
 complex_num = 1 + 3j  

  

## Truth values: booleans  
 Boolean variables are very common and useful  
 True or False – special objects in Python that behave like types in other languages  
 Also equal to False:  
 0, 0.0, 0j – zero numeric values  
 “” or ‘’ – empty string  
 () or [] or {} – empty sequences or mappings  
 None – the null value  
 Everything else evaluates to True ("not False"):  
 42, 11, -5, 3.1415, “Hello”…  

  

## Expressions  
 Expressions let us use variables and values for calculations  
 If there is a mixture of types in the calculation, Python will adjust the type, or give an error:  

  
 fullname = “John” + “Cleese”  
“JohnCleese”  
 final = exam_0.4 + test_0.2 + assign*0.4  
Final will be a float, even if exam, test and assign are ints  
 fullname = “Eric” + “Idle” + 3  
TypeError  

  

![[Screenshot_(18).png]]

What is the use of type() function in Python program?

Answer. Python ==type()== is a built-in function that is used to **return the type of data stored in the objects or variables in the program**

See the Program and output 👇

![[Python FOP/assets/Python FOP/Screenshot_(19).png]]

![[Screenshot_(21).png]]

![[Screenshot_(20).png]]

  

## Control structures: if, else, elif  
 Truth values / boolean expressions can be used to control the flow of a program:  
if (concession == "Y"):  
fare = 1.20  
elif (multi == "Y"):  
fare = 5.00  
else:  
fare = 3.00  

  
 Note: the code within the if/elif/else block needs to be indented with 4 spaces  
 Multiple elif’s can be used in sequence  

  

![[Python FOP/assets/Python FOP/Screenshot_(22).png]]

  

Range Function—>

  

### Python range() Explained with ExamplesUpdated on: March 17, 2022 | [55 Comments](https://pynative.com/python-range-function/#llc_comments)

Python `range()` function generates the **immutable sequence of numbers** starting from the given start integer to the stop integer. The `range()` is a built-in function that returns a range object that consists series of integer numbers, which we can iterate using a `for` loop.

In Python, Using a [for loop](https://pynative.com/python-for-loop/) with `range()`, we can repeat an action a specific number of times. For example, let’s see how to use the `range()` function of **Python 3** to produce the first six numbers.

**Example**

`# Generate numbers between 0 to 6 for i in range(6): print(i)`

**Output**

```Plain
0
1
2
3
4
5
```

  

`--> range(start, stop[, step])`

It takes three arguments. Out of the three, two are optional. The `start` and `step` are optional arguments and the `stop` is the mandatory argument.

### Parameters

- `start`: (Lower limit) It is the starting position of the sequence. The **default value is 0** if not specified. For example, `range(0, 10)`. Here, `start=0` and `stop = 10`
- `stop`: (Upper limit) generate numbers up to this number, i.e., An integer  
    number specifying at which position to stop (upper limit). The  
    `range()` **never includes the stop number in its result**
- `step`: Specify the increment value. Each next number in the sequence is  
    generated by adding the step value to a preceding number. The **default value is 1** if not specified. It is nothing but a difference between each number in the result. For example, `range(0, 6, 1)`. Here, `step = 1`.

  

Just to Know

- In Python 2, we have `range()` and `xrange()` functions to produce a sequence of numbers.
- In Python 3 `xrange()` is renamed to `range()` and original `range()` function was removed. We will discuss it in the later section of the article.

  

Python offers a powerful feature called **f-strings** (formatted string literals) to simplify string formatting and interpolation. **f-strings** is introduced in Python 3.6 it provides a concise and intuitive way to embed expressions and variables directly into strings. The idea behind f-strings is to make string interpolation simpler.   
  
  

`# Python3 program introducing f-string`

`val` `=` `'Geeks'`

`print``(f``"{val}for{val} is a portal for {val}."``)`

`name` `=` `'Tushar'`

`age` `=` `23`

`print``(f``"Hello, My name is {name} and I'm {age} years old."``)`

---

```Plain
GeeksforGeeks is a portal for Geeks.
Hello, My name is Tushar and I'm 23 years old.
```

[[Tips For Programming]]

[[Lecture 2_ Strings and List]]

[[Lecture 3 arrays and Plotting]]

[[Python FOP/VS Code Shortcuts]]

[[Lecture 4]]

[[Python FOP/Lecture 5/Lecture 5|Lecture 5]]

[[Python FOP/Lecture 6|Lecture 6]]

[[Lecture 7 Relationships in Object - Orientation !!]]

[[Dictionaries in python]]