# Essential Python — Intermediate Applications (Instructor Edition)

---

# Pre Start
- Open Slidee and choose slide deck for: **Introduction Course Day 2**

`SLIDE 1`

# Trainer Start
Hello everyone, welcome back! 

I hope you've had a good few days since our last session. A few days can be quite a long time when learning something how to handle a programming language.

We looked at:
- variables
- some of the most common datatypes in Python:
  - strings
  - ints and floats
  - lists
  - dictionaries

Then handling that data through different processes:
- control flow, our if / else statements
- loops
- functions

As well as all the other fun stuff like **f strings** and our **logical operators**

We're going to be building on what we covered last time so we will recap some of the concepts we looked at last session.

Then we'll get to look a little deeper at some of the fun things we can do in Python

`SLIDE 2`

That'll be, taking a look at:
- Using Python to actually create files, storing data and reading from that file
- A closer look at functions and how they're able to take a range of arguments
- Then we'll expand the scope of our code and write Python over multiple files
- The big one however is classes and OOP which will help us create and handle uniform data at scale. 

I know working with a new language which is unfamiliar can feel quite overwhelming, but the same as last time, we're going to go incrementally, and build up the complexity. 


---

## Accessing GitHub Codespaces

1. Let's begin by creating a new place to write our Python code. We're going to use GitHub Codespaces again, so give that a Google. 
 
2. Once you've clicked through to the site, again, let's just click **Get started for free**

3. Then we'll target a **blank template** again

Last time out, we created a file, **main.ipynb**, that gave us access to those little cells we executed. 

That's actually going to be a limitation for what we want to do today - we're going to need a complete file for executing and connecting larger scripts together. 

4. If you could please click the **“new file”** icon. Then create our file **main**, but this time, just the extension **.py**.

So I'm creating a new file, **main.py**

*CREAT FILE main.py*

Let's start again by creating a simple **print statement** and logging "Hello World"

**main.py**
```python
print("Hello World")
```

We're moving up in the world, without the cells we created last session we actually have to execute our file a different way. 

At the bottom of my screen, you can see a **terminal** or a **command line interface**. 

This is how people who work with software regularly execute code and navigate through their computer. 

- If you want to browse files on your computer you can use the **command line interface** or **cli** to do so
- If you want to read from files or write into a file, we can use the **cli**
- Essentially any operation you can do with a mouse, you can also do with the **cli** and a lot more.

When I was studying, an old trainer of mine, they used to behave almost like a Miss Trunchbull or any strict teacher and tell people off it they were caught using the mouse. 

I'm not going to be so forceful but practically there's one command we'll need to learn. 

If I type into the terminal: `python main.py` 

The computer will essentially take the Python downloaded onto the computer and run it against the file **main.py**

If we can all do that now just to make sure it's working. 

- *RUN* `python main.py` 

Hopefully we can see "Hello World" outputted to the terminal. 

We'll be using this throughout the rest of the morning and once we've run this command a few times, the terminal output will start to look a little messy. 

If I type 'clear' and press enter, it'll delete all the previous output. 

I'll just show you now. 

- *RUN* `clear`

The last tip I'll give you is we'll be using these commands a fair bit. On my keyboard, if I use the directional arrows 'up' and 'down', we can iterate through our previous commands, which can just save ourselves, a little bit of time. 

*SHOW ITERATION THROUGH PREVIOUS COMMANDS*



## ✏️ Topic 1 — Identifiers & Naming Conventions

Let's start properly with something we've potentially taken for granted. 

As with any software project, we want to establish good practice and make collaborating with others as easy as possible.


Variables are one of the foundational elements we looked at last session. Despite the foundational level, those variables or buckets are how we name data in Python. 

Python depends on those variables to handle information — whether it's data, functions or classes. We'll consistently assign values to them. 

Some of you may have noticed a convention I've been using so far, when writing variable names. 


It's called **snake_case** and it takes that name because the underscores are supposed to look like a snake.

No need to code along for this bit. 

*COPY & PASTE CODE*

**main.py**
```python
name = "Emile"
full_name = "Emile Sherrott"
extended_full_name = "Emile Stephen Sherrott"
```

All words are lower case and seperated by an underscore.

Consistent naming improves **readability**, **debugging**, **team communication**. 

If we were programming together as part of a team, maybe creating some software which allowed a user to see their bills. Let's say you needed to know what variable I used to store the data. I could say "customer billing info".

You don't need to ask several follow up questions to make sure you're capitalising the right letters or leaving spaces in the name. You'll know it'll look like this:

**main.py**
```python
name = "Emile"
full_name = "Emile Sherrott"
extended_full_name = "Emile Stephen Sherrott"
customer_billing_info
```

All lower case, underscores connecting the different words. 

These conventions and best practices in Python are summarised in a proposal called **PEP 8**

It's an acronym for **Python's Enhanced Proposal 8** which stipulates naming conventions, indentation, other things like that.

All these things are designed to ensure our code plays well with industry-standard tools, like **linters**


Very quickly, **linters** are pieces of software that check code for style, formatting and errors in regardings to PEP 8 conventions and those guides about good code. 

I'm sure your colleagues at VMO2 who use Python, daily, as part of their job, have a linter and it's ensuring that their code behaves as Python intended. 

No need again to code this out with me but I'm going to create some code which doesn't adhere to the standards of Python

**main.py**
```python
import datetime

newVariable = "Hello World"

if newVariable == "Hello World":
print("Python code is working")
```

Looking at my code right now, I can't tell if there's any issues and there's no obvious errors.

Because I understand a little bit of Python, the first thing I can identify, is that the code block underneath the **if statement** isn't indented correctly.  

The IDE or text editor isn't showing the mistake for me, maybe it is for some of you, but either way, we can also ask a **linter** to make sure things are going alright. 

I'm going to install a **linter** onto the computer. 

- *RUN*: `python -m pip install pylint`

Again, you don't need to code along with me for this but I've just executed a command to install some external software into the computer. It's called **pylint**, a fairly well used Python linter.

Now that I have access to a linter, what I'll do is run the **linter** against my file, to check, how do things look. 


- *RUN*: `pylint main.py`

So it's tested the code and it's failed.

```text
main.py:6:1: E0001: Parsing failed: 'expected an indented block after 'if' statement on line 5 (main, line 6)' (syntax-error)
```

Let's break down the error

#### **main.py:6:1**
So looking at the error, firstly it tells us where the error is. In the file **main.py**, on line **6** and the first character in that line. 

####
**E0001** 
Is an internal code for the error

Then we get the error message: **expected an indented block after 'if' statement on line 5**
 
Errors do fill people with dread and I see a lot of people in my line of work, who'd rather not confront the error but they're helpful - once you've taken the time to read them. 

There's a joke in tech which is semi-related to this, that "2 hours of debugging saves 10 minutes of reading documentation"

It speaks to a tendency of people who suffer with issues in their code, rather than reading a document which tells you how to implement something correctly the first time, you dive in and struggle with lots of issues.

Anyway, I've identifed one issue, let me fix it. 

**main.py**
```python
import datetime

newVariable = "Hello World"

if newVariable == "Hello World":
    # UPDATED CODE
    print("Code is working")
```

**ASK**
Anything we can see which you think isn't great? Based on what we discussed earlier and perhaps some other things?

I'll run my linter again. 

- *RUN*: `pylint main.py`

So there's lots of issues now. 

Interestingly the code is working

*RUN* `python main.py`

The problem the linter has, it's not stylised the way Python wants to be written and the code isn't very readable for a Python interpreter or developer. 

The first issue we can identify is: **Unused import datetime**, simply put we're importing something we're not using.

It's not efficient, so let's remove that

**main.py**
```python
newVariable = "Hello World"

if newVariable == "Hello World":
    print("Code is working")
```

OK, the next one I'll tackle is **Missing module docstring**. We briefly touched on DocStrings at the end of last session. 

What this is saying, in good Python code each file or module will have a Docstring explaining the purpose of the file to make collaboration easier. That's easy enough to fix. 

Three quotation marks to create a DocString

**main.py**
```python
# UPDATED CODE
"""Python training file"""

newVariable = "Hello World"

if newVariable == "Hello World":
    print("Code is working")
```

The final two issues aren't things we've spoken about before.

In programming there's a concept called **constants** which applies to variables and essentially if a variable doesn't ever change, then what you'd want to do is let other developers know that, by writing each character in **UPPER_CASE** seperated by an underscore. 

It serves as a visual indication not to reassign a value to this variable. 

The linter thinks newVariable is a constant, because it never changes value in this code.

So the linter, as far as it's aware, is giving us an appropriate message. 

I'll lean into it

**main.py**
```python
"""Python training file"""

# UPDATED CODE
GREETING_VAR = "Hello World"

# UPDATED CODE
if GREETING_VAR == "Hello World":
    print("Code is working")
```

The final error is fairly strange for those new to tech and even some people more experienced. 

Python wants us to have a empty line at the end of our files, the reason is a little dated but we can read from files using different methods.

I spoke about using the **CLI** earlier for lots of different operations. 

A common one, is reading the contents of a file without opening it. 

I can run: `cat main.py`, **cat** is short for concatenate and it'll display what's in a file. 

- *RUN* `cat main.py`

Do you notice now, that my **CLI** is connected directly to the end of my print statement. It doesn't fall onto a new line. 

If I add in an additional line at the end of my code, it'll be cleaner. 

- *RUN* `clear`
- *ADD EMPTY LINE AT THE BOTTOM*
- *RUN* `cat main.py`

You'd definitely have my sympathies if this is not something you think to do but again all these things are designed to make Python code the most readable it can be. 

I'll run my linter one more time. 

- *RUN* `pylint main.py`

Aside from indenting our code block, nothing we've done has actually allowed the code the run any better, but all of the changes are designed to make Python code more readable for large teams of developers. 

Practically people will have these linters running before they save code to spot any possible issues. 


### Naming Done Right

Let's remind ourselves how functions work, which is where we left off from the last session. 

Functions are designed to emcompass functionality for a collective set of actions.

We start with the **def** keyword to let Python know we're creating a function, followed by the function name and parenthesies.

**main.py**
```python
def calculatue_speed_difference()
```

So this function I hope can take two different internet speeds and tell me the difference between the two. 

Perhaps the type of function which could be used to help customers make a decisions whether to upgrade or not. 

For this to work I'm going to need to provide this function with two values. 
- A users current internet speed
- The new potential speed

We do this with parameters, the values we write inside the parentheses which are then used inside the code block.

I'll also add in a colon at the end to define the the beginning of that code block

**main.py**
```python
# UPDATED CODE
def calculatue_speed_difference(current_speed, new_speed):
```

I'll be good for the timebeing and give the function a DocString

**main.py**
```python
def calculate_speed_difference(current_speed, new_speed):
    """Return how much faster the new speed is compared to the current one"""
```

Then finally I just need the Python logic to achieve the task I want. 

The difference in speed is simply going to be the value of the current speed, being subtracted from the value of the new speed. 

I'll assign that value to a variable and then return that variable to the function

**main.py**
```python
def calculate_speed_difference(current_speed, new_speed):
    """Return how much faster the new speed is compated to the current one"""
    difference = new_speed - current_speed
    return difference
```

The last thing I'll do is simply call the function 

**main.py**
```python
def calculate_speed_difference(current_speed, new_speed):
    """Return how much faster the new speed is compated to the current one"""
    difference = new_speed - current_speed
    return difference

my_speed_difference = calculate_speed_difference(350, 500)
print(f"Your new speed is {my_speed_difference}Mbs faster")
```

- *RUN* `python main.py`

In this instance, 350 takes on the parameter of current_speed in the function and 500 takes on the parameter of new_speed

We make the calculation and return the difference to the function, then assign it to the variable before printing it. 

This is a good opportunity to add a second function.

One issue which could potentially arise is if someone was downgrading their service, maybe a to a cheaper option. 

Our print statement is containing that word **faster** which could be problematic. 

We need to go through a small process of making our code more resilient. 

Let's add another function to actualy give a message.

First thing I'll do is remove the code outside of the code block

**main.py**
```python
def calculate_speed_difference(current_speed, new_speed):
    """Return how much faster the new speed is compated to the current one"""
    difference = new_speed - current_speed
    return difference
```

Then define our new function, I'm going to leave space for one parameter, the 'difference' in speed. 

**main.py**
```python
def calculate_speed_difference(current_speed, new_speed):
    """Return how much faster the new speed is compated to the current one"""
    difference = new_speed - current_speed
    return difference

def return_message(speed_difference):
```

I think an if/else statement is probably a good choice. 

If the value of difference is greater than zero, return a message with increase. Otherwise or 'else' return a message with decrease. 

**main.py**
```python
def calculate_speed_difference(current_speed, new_speed):
    """Return how much faster the new speed is compated to the current one"""
    difference = new_speed - current_speed
    return difference

def return_message(speed_difference):
    if speed_difference > 0:
        return f"Your speed increase will be {speed_difference}Mbs"
    else:
        return f"Your speed decrease will be {speed_difference}Mbs"
```

We could do this all in one function, it may actually be logical to do so as both functions relate to the same thing. 

What I want to show you though is our ability to call one function, from inside the body of another function. 

Instead of returning the difference from 'calculate_speed_difference', instead I'm going to remove that line and pass the 'difference' variable into the 'return_message' function.

**main.py**
```python
def calculate_speed_difference(current_speed, new_speed):
    """Return how much faster the new speed is compated to the current one"""
    difference = new_speed - current_speed
    # UPDATED CODE
    return_message(difference)

def return_message(speed_difference):
    if speed_difference > 0:
        return f"Your speed increase will be {speed_difference}Mbs"
    else:
        return f"Your speed decrease will be {speed_difference}Mbs"
```

Finally I'm just going to assign that returned string from the 'return message' function to a variable. 

Then return that. 

**main.py**
```python
def calculate_speed_difference(current_speed, new_speed):
    """Return how much faster the new speed is compated to the current one"""
    difference = new_speed - current_speed
    # UPDATED CODE
    message = return_message(difference)
    # NEW CODE
    return message

def return_message(speed_difference):
    if speed_difference > 0:
        return f"Your speed increase will be {speed_difference}Mbs"
    else:
        return f"Your speed decrease will be {speed_difference}Mbs"
```

Things are very interwoven right now. Data is being exchanged and manipulated everywhere we look. 

I'm going to call our function and I want you to practice just reading the code and the flow of data. 

**main.py**
```python
def calculate_speed_difference(current_speed, new_speed):
    """Return how much faster the new speed is compated to the current one"""
    difference = new_speed - current_speed
    message = return_message(difference)
    return message

def return_message(speed_difference):
    if speed_difference > 0:
        return f"Your speed increase will be {speed_difference}Mbs"
    else:
        return f"Your speed decrease will be {speed_difference}Mbs"

print(calculate_speed_difference(350, 500))
```

*RUN CODE*

**ASK**
Does anyone fancy, walking me through how this function works?

**IF NOT ANSWER**
- Firstly we call the calculate speed difference
  - 'current_speed' takes the value 350
  - 'new_speed' takes the value 500
 - Then we make a subtraction of those two values and store the int into a variable called difference
   - The value held in this run is '150'
 - That value is then passed to the 'return_message' function under the parameter of 'speed_difference'
 - We go into some control flow, dependant on if the 'speed_difference' parameter, we return one of two f-strings
 - That's returned back to the calling function and then assigned to the 'message' variable
 - Which we finally return back to the parent calling function, within our print statement. 


 There's actually one big issue with our code right now. 

 **ASK**
 Can anyone see it?

 **ANSWER**
 If someone's downgrading their service, we'll return a double negative

 **main.py**
```python
def calculate_speed_difference(current_speed, new_speed):
    """Return how much faster the new speed is compated to the current one"""
    difference = new_speed - current_speed
    message = return_message(difference)
    return message

def return_message(speed_difference):
    if speed_difference > 0:
        return f"Your speed increase will be {speed_difference}Mbs"
    else:
        return f"Your speed decrease will be {speed_difference}Mbs"

# UPDATED CODE
print(calculate_speed_difference(500, 350))
```

*RUN* `python main.py`

Fortunately there's a simple fix, a built in method called 'abs' which returns an absolute value.

The absolute value is basically the distance that number is from zero, practically it flips a number from negative to positive. 

 **main.py**
```python
def calculate_speed_difference(current_speed, new_speed):
    """Return how much faster the new speed is compated to the current one"""
    difference = new_speed - current_speed
    message = return_message(difference)
    return message

def return_message(speed_difference):
    if speed_difference > 0:
        return f"Your speed increase will be {speed_difference}Mbs"
    else:
        # UPDATED CODE
        return f"Your speed decrease will be {abs(speed_difference)}Mbs"

print(calculate_speed_difference(500, 350))
```

### Default parameters

For the next part of the session we're going to extend our functions by using something called **default parameters**

They're used primarily when we're building a function and there's possibility for missing data or when that function is called regularly with common values. 

Take our imaginary customer which may interact with this function.

As a company, it may be that a new internet cables is being installed in a region and everyone has the opportunity to upgrade to 1000 megabytes per second.  

So we expect that most of the time that this function runs, the new speed argument of the function is going to be 1000. 

We don't want to hard code it though, we still want the function to work with other possible new internet speeds too. 

Adding a default parameter is easy as placing an equals sign **=** next to the parameter and writing in the default value. 


**main.py**
```python
# UPDATED CODE
def calculate_speed_difference(current_speed, new_speed=1000):
    """Return how much faster the new speed is compated to the current one"""
    difference = new_speed - current_speed
    message = return_message(difference)
    return message

def return_message(speed_difference):
    if speed_difference > 0:
        return f"Your speed increase will be {speed_difference}Mbs"
    else:
        # UPDATED CODE
        return f"Your speed decrease will be {abs(speed_difference)}Mbs"
```

Now all I'll do is call the function twice, one when I want an upgrade to 500Mbs and the second where I don't pass a value at all.

**main.py**
```python
def calculate_speed_difference(current_speed, new_speed=1000):
    """Return how much faster the new speed is compated to the current one"""
    difference = new_speed - current_speed
    message = return_message(difference)
    return message

def return_message(speed_difference):
    if speed_difference > 0:
        return f"Your speed increase will be {speed_difference}Mbs"
    else:
        # UPDATED CODE
        return f"Your speed decrease will be {abs(speed_difference)}Mbs"

# NEW CODE
print("Two arguments passed:", calculate_speed_difference(350, 500))
print("Default argument used:", calculate_speed_difference(350))
```

*RUN CODE*

Everytime this function runs and we only pass in one value, the parameter for new_speed by default takes the value of 1000. 

There's lots of different use cases for this.

We could create a fairly simple programme which runs on our website to greet a customer. If they have a profile and we've got data about their name, we can use that. Otherwise we'll provide a more generic greeting.  

I'll copy some code through. 

**main.py**
```python
customer = {
    "name": "Emile",
    "devices": ["Router", "Mobile", "TV"]
}

def greet(name="Guest"):
    """Greet the user by name, defaulting to 'Guest' if no name is provided."""
    print(f"Hello, {name}!")

greet()
greet(customer["name"])
```

*RUN CODE*

What I've got is customer data, stored in a dictionary at the top. 

The first time I call this funciton, no argument is passed and we can see in the output, we utilise the default value. 

As part of the second function call at the bottom, I use the square bracket notation to pass in the customers name. That returns the string "Hello Emile"


If you have multiple parameters, it's important to define any **default parameters** at the end, not at the start. 

### Task 5 Mins

I want you to spend a 5 minutes trying to write your own function with a default parameter. 

The function will be called **calculate bill** where you can pass in the cost of your restuarant bill where a discretionary charge of 12.5% is added to the total. 

Some people prefer not to pay service charge and other people may be happy to pay more. 

There should be two parameters:
1. The bill total
2. The service_charge which has a default float value of 12.5

**SOLUTION**
**main.py**
```python
def calculate_bill(total, service_charge = 12.5):
    return total + ((total / 100) * service_charge)

print(calculate_bill(100))
print(calculate_bill(100, 10))
```

*BREAK*

### ⚙️ Topic 2— Reusable Functions & Mutable Parameters

We're going to stick with functions for another little while. 

I'm going to delete what I have on screen but I'll share a file with all the code snippets we've used throughout the day. 

Before we continue with functions though I need to speak about the concept of **mutability**

Certain data types we can define as being **mutable**, which means the data can change after they've been defined. 

No need to follow along

**main.py**
```python
name = "Emile"
print(name[0])
```
**ASK**
Does anyone want to take a guess what this will return?

**ANSWER** 
'E'

*RUN* `python main.py`

It's fine for us to access the first character in this name variable but if I try and change that character, it'll throw an error.

**main.py**
```python
name = "Emile"

name[0] = "S"
print(name)
```

*RUN* `python main.py*

We can see the error, 'string objects don't support item assignment' 

If I wanted to programmatically change my name to "Smile", I'd have to delete the data and recreate it afresh

**main.py**
```python
name = "Emile"

name = "Smile"

print(name)
```

*RUN* `python main.py`

Strings are immutable, if we want to change the data, under-the-hood we have to destroy and redefine it, other datatypes are also immutable:
- ints
- floats
- booleans
- tuples (which similar to lists but immutable)

Mutable data types which we can change include:
- lists
- dictionaries
- sets (similar to lists but only had unique data)

You're probably right to wonder how this relates to functions

The problem is when we have a function where a **mutable object** like a **list** or **dictionary** is defined, because they're mutable datatypes we may unintentionally reuse the same **list** or **dictionary** when we want to create a new one. 

Let me show you a simple function

*COPY CODE*

**main.py**
```python
def add_device(device, devices=[]):
    devices.append(device)
    return devices
```

1. Our first paramter is required, it's the device we intend to add to the user's account
2. Then we have an optional parameter, which if it's not passed, we use a default value of an empty list

A reasonable way to imagine using this function is to create a list of devices for different customers.

**main.py**
```python
def add_device(device, devices=[]):
    devices.append(device)
    return devices

# NEW CODE
emiles_devices = add_device("Mobile")
simons_devices = add_device("TV")

print(emiles_devices)
print(simons_devices)
```

My hope would be that there's two seperate lists, my list with one item, 'Mobile' and another list with one item 'TV'

*RUN* `python main.py`

Both lists are the same. 

What's happening is, when the function is defined, before we ever call it, Python creates the default list whether it's needed or not.
1. The first call for Emile, we don't pass in an argument under the 'devices' parameter, the default list value is used. And we add **Mobile** to it
2. The second call for Simon, the function still receives only the a value on the 'device' parameter and the function uses same default list value from the first call and we add **TV** to the same list.

Each call which doesn't pass in a second argument for **devices**, will use the default one when we defined the function. 

Because **lists** are mutable and we can update the same data, it uses the same one for both.

A similar thing would happen if we added a default value of other mutable objects like a dictionary. 



If we want to correct this behaviour, we'd have to change where that list is defined, not when we initially write the function parameters like we have here, but after the function is actually called. 

Instead of using a default parameter of the empty list, we should use a default value of 'None' instead.

**main.py**
```python
# UPDATED CODE
def add_device(device, devices=None):
    devices.append(device)
    return devices

# NEW CODE
emiles_devices = add_device("Mobile")
simons_devices = add_device("TV")

print(emiles_devices)
print(simons_devices)
```

None represents no value

Then we need some control flow to basically identify where a list has been provided or not under the 'devices' parameter. 

**main.py**
```python
def add_device(device, devices=None):
    # NEW CODE
    if devices is None:
        devices = []
    devices.append(device)
    return devices

emiles_devices = add_device("Mobile")
simons_devices = add_device("TV")

print(emiles_devices)
print(simons_devices)
```

Now it should behave itself. It's inside the function body where we have the opportunity to create a new list. 

Not when we define the function originally. 

If no value is passed on the 'devices' parameter, we create a new one. 

Because the line `devices.append(device)` isn't inside the **if statements** code block, we append the value passed in on the `device` parameter either way.

*RUN* `python main.py`


This gives us some flexibility to target a user with prexisting devices or a completely new user. 

Now I'll actually pass an an argument for 'devices', I'm going to use our function to extended the devices I have

**main.py**
```python
def add_device(device, devices=None):
    if devices is None:
        devices = []
    devices.append(device)
    return devices

emiles_devices = add_device("Mobile")
simons_devices = add_device("TV")

print(emiles_devices)
print(simons_devices)

# NEW CODE
emiles_devices = add_device("Router", emiles_devices)
print(emiles_devices)
```

*RUN CODE*

*PAUSE FOR QUESTIONS*

---

*BREAK* 

## 🧩 Topic 3 — Variadic Functions

We'll finish off this section of functions by looking at a new type of function 


Variadic functions accept a **variable number of arguments**, enabling some really cool flexibility. 

There's two terms we commonly use to define the different types of arguments we can use with variadic functions. 

`*args` for positional arguments and `**kwargs` for keyword arguments.

We'd use both of these when you don’t know in advance how many values will be passed.

Conceptually that may not mean too much right now, but let's suppose I'm a radio enginner for VMO2, I'm doing a job on site and logging the equipment found and I don't know what I'll find. 

It could be one piece of equipment or five, we don't want to write five different functions, each with a different number of parameters.

So in that instance having a function which offers the flexibility of receiving an unknown number of arguments is vital. 

To define a parameter which can receive multiple values we pass an asterix `*` before the parameter. 

Write this one out with me

**main.py**
```python
def log_equipment(*items):
    print("Equipment found:", items)

log_equipment("Radio Unit", "Antenna", "Battery Backup")
```

We've defined one parameter, but passing in 3 arguements. 

*RUN* `python main.py`

We can see the output, it reads, *Equipment found* and then wraps our three strings in what's called a **tuple**.

Tuples are similar to lists, they have an order, we can access those values by their position like lists. 

The main difference is tuples don't change after they've been created - they're **immutable**.

If a **list** is like a shopping list which we can change and update whilst we're in a store. **Tuples** are like the receipt once you've purchased your groceries. The receipt won't change after. 

But in our example of the radio engineer, it doesn't matter how many items we find, we can work with them. Because it's a tuple, we can iterate over them.


Suppose our radio engineers are specifically interested in finding any batteries due to the need to safely dipose of them. 

Because are tuples are similar to lists, we can loop over the collection, if we find any batteries, we do something with it. 

**main.py**
```python
def log_equipment(*items):
    print("Equipment found:", items)
    # NEW CODE
    for item in items:
        if item == "Battery Backup":
            battery_found()

log_equipment("Radio Unit", "Antenna", "Battery Backup")
```

Loop over the tuple and if one of the items is a Battery, run another function. 

Now I just need to define a function for what that means

**main.ipynb**
```python
def log_equipment(*items):
    print("Equipment found:", items)
    for item in items:
        if item == "Battery Backup":
            battery_found()

# NEW CODE
def battery_found():
    print("**** Battery found, process for safe disposal ****")

log_equipment("Radio Unit", "Antenna", "Battery Backup")
```

*RUN* `python main.py`

That's a look at **args**


****kwargs** are slightly different, they allow us to pass in an unknwon number of **named values**. 

That sounds a little confusing, in our **args example** we saw the data existing inside the function as a tuple. 

**Radio Unit** or an **Antenna** inside the tuple, isn't considered to have a name. Technically we'd say they have a position.

We've seen how we can extract data from lists, square bracket with a 0 to pull the first element. The same with tuples. 

Despite the value being a string, it's not actually a name. 

The best way to know the difference, is do we access the data, by position or name


On the other hand if we think back to **dictionaries** we use the key name to extract the value

`SLIDE 3`


Each of these key/pair values is a string which we can read, but they're known as named values because the way we can access them is because of their corresponding keys or **names**

So we have the ability to pass an unknwon number of these named values as **kwargs**:
- On the parameter we use two asterixes instead of one
- Then as we pass them in as arguements we'll need to use is an **equals (=) sign**

**main.py**
```python
# UPDATED CODE
def log_equipment(*items, **details):
    print("Equipment found:", items)
    for item in items:
        if item == "Battery Backup":
            battery_found()
    # NEW CODE
    if details:
        print(details)

# UPDATED CODE
log_equipment("Radio Unit", "Antenna", "Battery Backup", site="O2 Academy Brixton", region="South London")
```

*RUN* `python main.py`

If **args** are outputted as a **tuple**, we can see because of the **curly braces** that **kwargs** get outputted as **dictionaries**.

I'll show you some code you can lift and use in any programs you care the write, I'll loop over a **dictionaries** and pull the information on the keys and values.

**main.py**
```python
def log_equipment(*items, **details):
    print("Equipment found:", items)
    for item in items:
        if item == "Battery Backup":
            battery_found()
    
    if details:
        # NEW CODE
        for key, value in details.items():
            print(f"{key} - {value}")

def battery_found():
    print("**** Battery found, process for safe disposal ****")

log_equipment("Radio Unit", "Antenna", "Battery Backup", site="O2 Academy Brixton", region="South London")
```

I wont over explain this, but there's a built in method called 'items()' which attaches onto a dictionary and returns a list, each list element, contains a tuple with two items:
- the key
- and the value

Then we loop over that list and print the key and value from within the f-string

That is the last of the functions we'll look at. 

*BREAK*



## 📂 Topic 4 — Working with Files

Let's move onto something a little more execiting. 

All of our computers have memory, or specifically RAM.

Let me copy some code over. 


**main.py**
```python
data = {"customer": "Alex", "speed": 500, "plan": "Fibre Max"}
print("Something happening")
print("Something happening")
print(data)
```
- RAM stores data between information between being created and utilised
- If the programme ends here, RAM forgets that data, it no longer exists

*RUN CODE*

I've defined the data on line one, between that I run two print statements before I finally log the data. 

Inbetween the data being defined and logged, the computer holds the dictionary in memory. 

Once the program ends the computer forgets the data. 

That's fine, we wouldn't want it any other way because our computers would get bogged down quite heavily. 

Some data we can't forget though, if we're pulling in information from a radio tower, we can't lose it once the program ends if it needs further assessment. 


Creating files allows for data to **persist** — logs, configurations, or sensor readings, whatever it may be can remain after the programme's shutdown.  

Python, fortunately, is pretty good at this, we can use built-in functionality to access a computers file system, reading files, or creating them. 

Let's programmatically create some files

One problem we have, Python, as we know is a programming language, it's not a format to save data in. 

There's a data format called JSON which stands for JavaScript Object Notation. 

When servers around the world send and receive data, most commonly, it's sent as JSON because it doesn't take much bandwidth. Fortunatelty for us, the data format looks almost identical to a dictionary in Python. 

So I'll write a little code which firstly just imports the json module and we'll create a small dictionary for some customer data. 

**main.py**
```python
import json  

data = {
    "customer": "Alex",
    "speed": 500,
    "plan": "Fibre Max"
}
```
I keep saying Python provides lots of built in functionality. It's a really good programming language for this.

Let's use it

**main.py**
```python
import json  

data = {
    "customer": "Alex",
    "speed": 500,
    "plan": "Fibre Max"
    }

# NEW CODE
with open()
```

- 'with open' opens or creates a file
- Specifically the 'with' part, is a built in key word that automatically closes any file used within the operation to avoid loss of data 
- Open, opens the file so we can perform actions on it

We need to give some information about what we actually want from this keyword and fuction.
- I want to give my file a name
- I want to write our data to the file


**main.py**
```python
import json  

data = {
    "customer": "Alex",
    "speed": 500,
    "plan": "Fibre Max"
}

# UPDATED CODE
with open("customer.json", "w", encoding="utf-8") as f:
```

- The first argument is a string of the file name
- The second argument is the action and "w" is for writing

`encoding="utf-8"` is interesting, as humans, we read things as text, computers on the other hand deal with 0's and 1's. UTF-8 is a way to encode text which encompasses most of the characters we deal with, including non-Latin characters like what you'd see in Russian or Greek alphabets.

Other encoding formats exist but don't span the range of characters out there that 'utf-8' does. 

The `as f:` part is essentially renaming this file as 'f' and the beginning of the code block.

Now I've got my data, I've created a file which I can write to, all that's left is writing the data to it. 

**main.py**
```python
import json

data = {
    "customer": "Alex",
    "speed": 500,
    "plan": "Fibre Max"
    }

with open("customer.json", "w", encoding="utf-8") as f:
    # NEW CODE
    json.dump(data, f, indent=4)
```

I hope you may start being able to predict what the different arguments mean
- Firstly `json.dump()` converts Python to JSON - technically that's called 'parsing' 
Then the arguments tell us about what we're doing with that data
- The first argument is what we're converting to JSON, that's our dictionary, held in the data variable
- `f` is where we're sending it, our file
- `index=4` is to indent the different layers of JSON to make it more readable

This should be enough to get us off the ground

*MAKE SURE FILE WINDOW IS OPEN*
*RUN* `python main.py`

Hopefully we've all been able to create a new file. 

Writing is only one half of the relationship, often we'll want to read as well.

The functionality will look similar but instead of writing we'll be reading

**main.py**
```python
import json

data = {
    "customer": "Alex",
    "speed": 500,
    "plan": "Fibre Max"
    }

with open("customer.json", "w", encoding="utf-8") as f:
    json.dump(data, f, indent=4)

# NEW CODE
with open("customer.json", "r", encoding="utf-8") as f:
    loaded_data = json.load(f)

print("Loaded:", loaded_data)
```
*RUN* `python main.py`

- 'json.dump' converts Python to JSON
- 'json.load` converts or 'deserializes' JSON back into Python

### Working with CSV Files

I'm going to bring some code over and show you how we can do some actionable things with a CSV file, which hopefully is quite close to home.

No need to code along, I've got a challenge for you, following this which will require you to try writing some Python. 

- Firstly I'll add some mock csv data I've created, into a new file, called 'vmo2-tickets.csv'

```csv
ticket_id,created_date,customer_id,service,issue_type,severity,status,assigned_team
VMO2-1002,2026-01-03,CUST-55210,Mobile,Slow Data,Minor,Closed,Radio Access
VMO2-1003,2026-01-04,CUST-99102,TV,Channel Missing,Major,In Progress,TV Platform
VMO2-1004,2026-01-04,CUST-44773,Broadband,Intermittent Drop,Major,Closed,Network Ops
VMO2-1005,2026-01-05,CUST-22019,Mobile,Voicemail Issue,Minor,Closed,Core Voice
VMO2-1006,2026-01-05,CUST-77331,Broadband,Router Failure,Severe,In Progress,CPE Support
VMO2-1007,2026-01-06,CUST-66542,TV,Playback Error,Minor,Closed,TV Platform
VMO2-1008,2026-01-06,CUST-11883,Mobile,No Signal,Severe,Open,Radio Access
VMO2-1009,2026-01-07,CUST-90444,Broadband,Slow Speed,Minor,Closed,Network Ops
VMO2-1010,2026-01-07,CUST-33991,Mobile,SMS Failure,Major,In Progress,Core Messaging
VMO2-1011,2026-01-08,CUST-77220,TV,App Crash,Minor,Closed,TV Platform
VMO2-1012,2026-01-08,CUST-55678,Broadband,No Connectivity,Severe,Open,Network Ops
VMO2-1013,2026-01-09,CUST-12003,Mobile,Roaming Issue,Major,Closed,Core Voice
VMO2-1014,2026-01-09,CUST-88177,Broadband,Packet Loss,Major,In Progress,Network Ops
VMO2-1015,2026-01-10,CUST-44321,TV,Audio Sync,Minor,Closed,TV Platform
VMO2-1016,2026-01-10,CUST-66754,Mobile,No Signal,Severe,Open,Radio Access
VMO2-1017,2026-01-11,CUST-99821,Broadband,Slow Speed,Minor,Closed,Network Ops
VMO2-1018,2026-01-11,CUST-33456,TV,Channel Missing,Major,In Progress,TV Platform
VMO2-1019,2026-01-12,CUST-77109,Mobile,VoLTE Issue,Major,Closed,Core Voice
VMO2-1020,2026-01-12,CUST-55233,Broadband,Router Failure,Severe,In Progress,CPE Support
VMO2-1021,2026-01-13,CUST-88901,TV,Playback Error,Minor,Closed,TV Platform
VMO2-1022,2026-01-13,CUST-44309,Mobile,Slow Data,Minor,Closed,Radio Access
VMO2-1024,2026-01-14,CUST-77654,TV,App Crash,Minor,Closed,TV Platform
VMO2-1025,2026-01-15,CUST-11802,Mobile,SMS Failure,Major,In Progress,Core Messaging
VMO2-1026,2026-01-15,CUST-90412,Broadband,Packet Loss,Major,Closed,Network Ops
VMO2-1027,2026-01-16,CUST-66345,TV,Audio Sync,Minor,Closed,TV Platform
VMO2-1028,2026-01-16,CUST-55128,Mobile,Roaming Issue,Major,Open,Core Voice
VMO2-1029,2026-01-17,CUST-77288,Broadband,Intermittent Drop,Major,In Progress,Network Ops
VMO2-1030,2026-01-17,CUST-33904,TV,Playback Error,Minor,Closed,TV Platform
VMO2-1033,2026-01-19,CUST-77211,Broadband,Backhaul Congestion,Severe,Open,Network Ops
VMO2-1034,2026-01-19,CUST-11992,Mobile,No Signal,Major,Closed,Radio Access
VMO2-1035,2026-01-20,CUST-55310,TV,Channel Missing,Minor,Closed,TV Platform
VMO2-1036,2026-01-20,CUST-88409,Broadband,DNS Failure,Severe,In Progress,Network Ops
VMO2-1037,2026-01-21,CUST-66123,Mobile,Slow Data,Minor,Closed,Radio Access
VMO2-1039,2026-01-22,CUST-77880,TV,Playback Error,Minor,Closed,TV Platform
VMO2-1040,2026-01-22,CUST-99001,Broadband,Core Link Failure,Severe,In Progress,Network Ops
```

**CSV** stands for Comma Seperated Values, at the top we can see our colum headers, seperated by commas and then several rows of information underneath. 

- We have information about a
  - ticket id
  - created date
  - customer id
  - service
  - issue
  - serverity
  - status
  - assigned team

This could very well be a shared dataset and I'm going to assume I'm part of the Network Ops team.

As part of that team, I need to identify the most pressing tickets and relay that information, so we can try and resolve them quickly. 

Let's start off by accessing the CSV file

**main.py**
```python
import csv

with open("vmo2-tickets.csv", "r", encoding="utf-8") as f:
    tickets = list(csv.DictReader(f))

for ticket in tickets:
    print(ticket)
```

Same syntax as before, but we're using a different module and method. Instead of `json.dump()` we use **csv.DictReader** which returns each row of data as dictionary. 

And every value within that dictionary as a string

I ultimatley want to loop over that data which is why I take that information and convert it to a list, before assinging it to the 'tickets' variable. 

Lastly, I loop over the list and print each ticket. 

*RUN* `python main.py`

So, we:
- Access our data
- Convert it to Python
- Do the operation we need

This is consitent if you're using JSON data, CSV data or XML data, which I won't have time to show you today. 

If we wanted to, once we've converted this data from CSV to Python, we could go ahead and convert it to JSON and store it in a JSON file. 

What I want to do instead though, is find all the tickets which relate to my team and which are severe.

*OPEN vmo2-tickets.csv*

If we inspect the data, each row is a seperate ticket, some are **minor**, others **major** and some **severe**.

In my hypothetical situation as well, I assume I'll want to do this fairly regularly, so I'll create a function. I'll try to be a good colleague too, so I'll program it so my friends in the 'Radio Access' team or any other team can us it as well. 

I'll remove the **loop** then create a function called 'find_tickets' which can recieve three arguments:
- csv data as a list
- the team
- the severity

**main.py**
```python
import csv

with open("vmo2-tickets.csv", encoding="utf-8") as f:
    tickets = list(csv.DictReader(f))

# NEW CODE
def find_tickets(items, team, severity):
```

Let me quickly log the values the function recieves and also reintroduce my loop.

**main.py**
```python
import csv

with open("vmo2-tickets.csv", encoding="utf-8") as f:
    tickets = list(csv.DictReader(f))

# NEW CODE
def find_tickets(items, team, severity):
    print(team)
    print(severity)
    for item in items:
        print(item)

find_tickets(tickets, "Network Ops", "Severe")
```

*RUN* `python main.py`

I'm calling the function just to see how we're currently handling the data. 

We're looping through each row and we can see the keys, this is where the first session we did together, really comes into play. 

We've converted the data into a Python dictionary, so I know I can use my square bracket notation to see the values on the keys. 

I want to use that within some control flow, specifically to extract each ticket that has information which relates to my team and the severity I care about



**main.py**
```python
import csv

with open("vmo2-tickets.csv", encoding="utf-8") as f:
    tickets = list(csv.DictReader(f))

def find_tickets(items, team, severity):
    for item in items:
        # NEW CODE
        if item["assigned_team"] == team and item["severity"] == severity:
            print(item)

find_tickets(tickets, "Network Ops", "Severe")
```

I'm excited, this function should hopefully when called at the bottom only target severe tickets relate to my team and filter them out from all the others so I can focus on what's important. 

- Again we pull in information from a file
- Parse or convert it into Python
- Store it in a variable
- Use different techniques from Python to interact with it

*RUN* `python main.py`

The code is written once, but now accessible to any team member looking to execute it as often as they like. 

This doesn't mean to serve as a warning but be aware that reading from files is safer than writting to a file so if you have any live data, firstly I'd recommend backing it up and start by reading from it before creating files and get the file owners permission. 

I'll quickly show you code to write to a file as well. 

*COPY CODE*

**main.py**
```python
import csv

with open("new_vmo2_customers.csv", "w", encoding="utf-8") as f:
    writer = csv.writer(f)
    writer.writerow(["customer_name", "customer_postcode", "customer_package"])
    writer.writerows([
        ["Olivia Turner", "SW1A 1AA", "Volt M200 Fibre"],
        ["James Patel", "M1 1AE", "Volt M350 Fibre"],
        ["Amelia Hughes", "B1 1BB", "Volt Gig1 Fibre"],
        ["Noah Thompson", "LS1 4AP", "Volt M125 Fibre"],
        ["Isla Campbell", "G1 2FF", "Volt M500 Fibre"],
        ["Jack Robinson", "BS1 5AH", "Volt M350 Fibre"],
        ["Ava Edwards", "CF10 1EP", "Volt M200 Fibre"],
        ["Harry Walker", "NE1 3PJ", "Volt Gig1 Fibre"],
        ["Emily Green", "L1 8JQ", "Volt M125 Fibre"],
        ["George Hall", "EH2 2YB", "Volt M500 Fibre"],
        ["Sophia Lewis", "NG1 6DQ", "Volt M350 Fibre"],
        ["Charlie Young", "OX1 1AA", "Volt M200 Fibre"],
        ["Mia King", "PL1 2AA", "Volt M125 Fibre"],
        ["Freddie Wright", "YO1 7HB", "Volt Gig1 Fibre"],
        ["Grace Scott", "BT1 5GS", "Volt M350 Fibre"],
        ["Leo Adams", "AB10 1XG", "Volt M500 Fibre"],
        ["Lily Baker", "CV1 2GT", "Volt M200 Fibre"],
        ["Oscar Nelson", "LE1 5TR", "Volt M350 Fibre"],
        ["Evie Carter", "MK9 3EP", "Volt Gig1 Fibre"],
        ["Theo Mitchell", "WD17 1EU", "Volt M125 Fibre"],
    ])
```

The main noticeable differences are:
- The built in function on the csv module is called 'writer' which we assign to variable of the same name
- Then we have a method called 'write row' which recieves a list of data. 
- To input information at mass, we pass in a list of lists.
  - Notice that each nested list has three items to correspond with the headers we pass in at the top
  - *SHOW PARENT LIST AND CHILD LISTS ON SCREEN*


*RUN CODE*

### Task

I want you to try and work with some similar CSV data and use Python to pull out something useful

In this hypothetical

VMO2 are doing a sweeping upgrades across their services in Blackpool, I'd love it if you could try to write a function which can create a list of all the active customers in Blackpool who we'll need to call.

The data is ready for you on the GitHub Gist, feel free to copy that over into a new **csv** file. 

There's also a solution underneath which I'd encourage you to read as well if you're struggling. 

I'll take everyone through it in 5 / 10 minutes either way. 

But to repeat, process the CSV file and then filter the data to extract the active customers from Blackpool

**vmo2-customers.csv**
```csv
customer_id,customer_name,segment,region,join_date,product_bundle,tenure_months,customer_status,contact_number
CUST-20001,Aaron Taylor,Consumer,Bristol,2019-10-01,Mobile Only,23,Active,447700900001
CUST-20002,Hannah Morris,SMB,Manchester,2023-08-16,Broadband Only,10,Active,447700900002
CUST-20003,Lily Garcia,Consumer,London,2023-04-18,Mobile Only,97,Active,447700900003
CUST-20004,Matthew Wright,Consumer,Leicester,2020-02-14,Business Broadband,6,Inactive,447700900004
CUST-20005,Jack Collins,Consumer,Bristol,2018-09-29,Mobile Only,103,Active,447700900005
CUST-20006,Noah Hernandez,Consumer,Glasgow,2023-10-09,TV + Broadband,109,Active,447700900006
CUST-20007,Amelia Carter,Consumer,Liverpool,2017-11-19,TV Only,43,Inactive,447700900007
CUST-20008,Sofia Young,Consumer,Reading,2017-10-12,Volt Bundle,90,Active,447700900008
CUST-20009,Oscar Davies,SMB,Manchester,2021-04-06,TV + Broadband,64,Active,447700900009
CUST-20010,Isabella White,Consumer,Leeds,2024-07-08,TV + Broadband,95,Inactive,447700900010
CUST-20011,Victoria Johnson,Consumer,Birmingham,2022-12-28,Mobile + TV,37,Active,447700900011
CUST-20012,Mason Clark,SMB,Cardiff,2024-09-19,TV Only,34,Active,447700900012
CUST-20013,Natalie Reed,Consumer,London,2020-07-16,Broadband Only,40,Active,447700900013
CUST-20014,Joseph Stewart,Consumer,Cardiff,2022-08-07,Broadband Only,88,Active,447700900014
CUST-20015,Henry Moore,Consumer,Nottingham,2023-01-17,TV + Broadband,101,Active,447700900015
CUST-20016,Elizabeth King,Consumer,Birmingham,2022-09-19,Broadband Only,17,Inactive,447700900016
CUST-20017,George Jackson,Consumer,Brighton,2024-08-19,Broadband Only,82,Active,447700900017
CUST-20018,Mason Turner,SMB,Nottingham,2019-10-27,TV Only,7,Active,447700900018
CUST-20019,George Edwards,SMB,Brighton,2019-12-29,Business Broadband,88,Active,447700900019
CUST-20020,Oscar Lopez,Consumer,London,2019-12-15,TV Only,103,Active,447700900020
CUST-20021,Isla Cook,Consumer,Cardiff,2022-09-11,TV Only,31,Active,447700900021
CUST-20022,Ryan White,Consumer,Brighton,2022-12-13,Volt Bundle,82,Active,447700900022
CUST-20023,James Taylor,SMB,Brighton,2020-06-13,Mobile Only,13,Active,447700900023
CUST-20024,Joseph Davies,Consumer,Sheffield,2017-10-11,Business Broadband,74,Inactive,447700900024
CUST-20025,Harry Evans,Consumer,Nottingham,2018-11-08,TV + Broadband,73,Inactive,447700900025
CUST-20026,Charlotte Thompson,SMB,Brighton,2024-09-26,Mobile Only,97,Active,447700900026
CUST-20027,Joshua Parker,Consumer,Nottingham,2022-01-24,Volt Bundle,37,Active,447700900027
CUST-20028,Emily Patel,Consumer,Leeds,2023-08-08,Mobile Only,6,Active,447700900028
CUST-20029,Aaron Brown,Consumer,London,2020-09-15,Volt Bundle,71,Active,447700900029
CUST-20030,Joshua Adams,Consumer,Birmingham,2023-05-28,TV Only,66,Active,447700900030
CUST-20031,Michael Wright,Consumer,Manchester,2024-05-23,Broadband Only,51,Active,447700900031
CUST-20032,Amelia Sanchez,Consumer,Cardiff,2024-03-31,Volt Bundle,13,Active,447700900032
CUST-20033,Emily Wilson,Consumer,Leeds,2023-01-06,Broadband Only,23,Active,447700900033
CUST-20034,Amelia Scott,Consumer,Manchester,2021-12-21,Business Broadband,76,Active,447700900034
CUST-20035,Victoria Carter,Consumer,Manchester,2019-08-27,Mobile Only,58,Active,447700900035
CUST-20036,Lily King,SMB,Birmingham,2021-04-02,Volt Bundle,55,Active,447700900036
CUST-20037,Amelia Rodriguez,Consumer,Reading,2023-03-27,Mobile + TV,97,Active,447700900037
CUST-20038,Leo Rodriguez,Consumer,London,2023-07-01,Mobile + TV,75,Active,447700900038
CUST-20039,Ethan Brown,Consumer,Sheffield,2022-08-22,Business Broadband,73,Active,447700900039
CUST-20040,Daniel Davies,SMB,Manchester,2023-09-04,Volt Bundle,92,Inactive,447700900040
CUST-20041,Mia Taylor,SMB,Leicester,2019-10-06,TV Only,82,Active,447700900041
CUST-20042,Noah Wright,Consumer,Leicester,2022-11-12,TV + Broadband,39,Active,447700900042
CUST-20043,Zoe Walker,Consumer,Liverpool,2018-06-21,Mobile + TV,88,Active,447700900043
CUST-20044,Ethan Rogers,SMB,London,2022-02-21,TV Only,78,Inactive,447700900044
CUST-20045,Ava Carter,Consumer,Bristol,2018-06-27,TV + Broadband,14,Inactive,447700900045
CUST-20046,Isabella Rodriguez,Consumer,Nottingham,2024-11-21,TV + Broadband,84,Inactive,447700900046
CUST-20047,Victoria Nelson,Consumer,Nottingham,2020-05-11,Mobile + TV,19,Inactive,447700900047
CUST-20048,Harry Robinson,Consumer,Manchester,2023-03-17,Mobile Only,40,Active,447700900048
CUST-20049,Lily Stewart,Consumer,Cardiff,2024-02-11,Business Broadband,39,Active,447700900049
CUST-20050,Henry Brown,Consumer,Liverpool,2020-02-08,Volt Bundle,6,Active,447700900050
CUST-20051,Harry Cook,SMB,Birmingham,2021-12-15,TV Only,96,Active,447700900051
CUST-20052,Emma Taylor,Consumer,Reading,2018-09-03,TV Only,10,Inactive,447700900052
CUST-20053,Elizabeth Mitchell,Consumer,Birmingham,2017-06-21,TV + Broadband,52,Inactive,447700900053
CUST-20054,Sophia Allen,Consumer,Leeds,2024-06-24,Volt Bundle,51,Inactive,447700900054
CUST-20055,Logan Phillips,Consumer,Leeds,2018-10-28,Business Broadband,109,Active,447700900055
CUST-20056,Logan Patel,Consumer,Glasgow,2021-08-14,Business Broadband,91,Inactive,447700900056
CUST-20057,Ella Clark,Consumer,Reading,2018-03-19,Broadband Only,10,Inactive,447700900057
CUST-20058,Freddie Martin,Consumer,Sheffield,2020-12-03,TV + Broadband,107,Inactive,447700900058
CUST-20059,Freddie Patel,Consumer,Liverpool,2020-09-06,TV + Broadband,14,Inactive,447700900059
CUST-20060,Amelia Allen,Consumer,Liverpool,2024-08-15,Business Broadband,74,Active,447700900060
CUST-20061,James Taylor,SMB,Bristol,2019-01-02,TV Only,39,Active,447700900061
CUST-20062,David Lopez,Consumer,Brighton,2020-07-08,Broadband Only,83,Inactive,447700900062
CUST-20063,George Hernandez,SMB,Leeds,2019-11-10,Volt Bundle,96,Active,447700900063
CUST-20064,Harper Carter,Consumer,Reading,2024-07-09,Mobile Only,52,Active,447700900064
CUST-20065,Joshua Hall,Consumer,Cardiff,2018-05-26,Mobile + TV,44,Active,447700900065
CUST-20066,Joshua Wright,Consumer,Reading,2020-04-26,TV Only,22,Active,447700900066
CUST-20067,Joshua Hernandez,Consumer,Birmingham,2023-11-27,TV Only,44,Active,447700900067
CUST-20068,Emma Lewis,Consumer,Liverpool,2023-07-04,TV Only,89,Active,447700900068
CUST-20069,Jacob Hill,Consumer,Nottingham,2022-04-23,Business Broadband,107,Active,447700900069
CUST-20070,Joshua Davies,Consumer,Cardiff,2024-02-06,TV Only,48,Active,447700900070
CUST-20071,Ryan Martinez,Consumer,Leeds,2019-03-27,Mobile Only,9,Active,447700900071
CUST-20072,Michael Phillips,Consumer,Manchester,2022-02-09,Broadband Only,86,Active,447700900072
CUST-20073,Zoe Collins,Consumer,Liverpool,2019-09-27,Mobile Only,89,Active,447700900073
CUST-20074,Ryan Reed,SMB,Brighton,2021-10-08,Mobile Only,28,Inactive,447700900074
CUST-20075,Christopher Nelson,Consumer,Nottingham,2019-10-18,Business Broadband,21,Active,447700900075
CUST-20076,Amelia Evans,Consumer,Nottingham,2023-09-05,TV + Broadband,102,Inactive,447700900076
CUST-20077,Sofia Sanchez,SMB,Liverpool,2023-02-23,Broadband Only,26,Active,447700900077
CUST-20078,Michael Hill,Consumer,Leeds,2024-02-25,TV + Broadband,104,Inactive,447700900078
CUST-20079,Evelyn Cook,Consumer,Sheffield,2017-11-14,Mobile + TV,42,Active,447700900079
CUST-20080,Emily Walker,SMB,Manchester,2018-07-21,Mobile Only,35,Active,447700900080
CUST-20081,Mia Stewart,Consumer,Liverpool,2021-07-28,TV + Broadband,75,Active,447700900081
CUST-20082,Oliver Thompson,Consumer,Liverpool,2023-07-21,Mobile + TV,8,Inactive,447700900082
CUST-20083,Ryan Perez,Consumer,London,2020-12-11,TV + Broadband,102,Active,447700900083
CUST-20084,Logan Carter,Consumer,Nottingham,2023-10-07,Mobile Only,68,Active,447700900084
CUST-20085,Charlotte Adams,Consumer,Glasgow,2024-07-02,Mobile + TV,108,Active,447700900085
CUST-20086,Jack Scott,SMB,Leicester,2022-12-28,Volt Bundle,56,Active,447700900086
CUST-20087,Joshua Patel,Consumer,Liverpool,2018-07-10,Business Broadband,65,Active,447700900087
CUST-20088,Henry Hernandez,Consumer,Sheffield,2020-08-31,TV + Broadband,103,Inactive,447700900088
CUST-20089,Amelia Rogers,SMB,Liverpool,2019-10-31,Business Broadband,16,Active,447700900089
CUST-20090,Layla Carter,Consumer,Glasgow,2019-07-08,Mobile + TV,14,Inactive,447700900090
CUST-20091,Victoria Williams,Consumer,Leeds,2019-03-28,Business Broadband,8,Active,447700900091
CUST-20092,Ella Moore,Consumer,Manchester,2023-04-30,Mobile Only,65,Active,447700900092
CUST-20205,Chris O'Newman,Consumer,Wolverhampton,2017-07-30,TV + Broadband,67,Active,447700900113
CUST-20093,Natalie Young,Consumer,Leicester,2018-04-15,Business Broadband,110,Active,447700900093
CUST-20094,Poppy Wilson,Consumer,Bristol,2023-06-17,Mobile + TV,54,Active,447700900094
CUST-20095,Zoe Martin,Consumer,Reading,2024-01-14,Mobile Only,19,Active,447700900095
CUST-20096,Poppy Edwards,Consumer,Manchester,2023-05-08,Business Broadband,11,Active,447700900096
CUST-20097,Charlotte Evans,Consumer,Nottingham,2024-04-06,TV + Broadband,7,Inactive,447700900097
CUST-20098,Evelyn Wilson,Consumer,Glasgow,2024-02-17,Business Broadband,64,Active,447700900098
CUST-20099,Charlotte Harris,Consumer,Cardiff,2020-01-12,TV Only,109,Inactive,447700900099
CUST-20100,Natalie Green,Consumer,Reading,2023-08-24,TV + Broadband,47,Inactive,447700900100
CUST-20101,Noah Clark,SMB,Leeds,2022-03-19,TV Only,84,Active,447700900101
CUST-20102,Emily Patel,Consumer,Glasgow,2019-01-15,Broadband Only,33,Active,447700900102
CUST-20103,Henry Hall,Consumer,Leicester,2024-11-12,TV + Broadband,77,Active,447700900103
CUST-20104,Leo Davies,Consumer,Liverpool,2022-06-25,TV Only,103,Active,447700900104
CUST-20105,Michael Parker,Consumer,Sheffield,2017-03-12,Volt Bundle,43,Active,447700900105
CUST-20106,Christopher Martinez,Consumer,Leicester,2021-02-20,Broadband Only,76,Active,447700900106
CUST-20107,Charlotte Morris,Consumer,Glasgow,2024-11-18,Broadband Only,40,Active,447700900107
CUST-20108,Freddie Taylor,Consumer,Glasgow,2018-05-05,Mobile + TV,74,Inactive,447700900108
CUST-20109,Christopher Harris,Consumer,Reading,2022-06-07,TV + Broadband,98,Active,447700900109
CUST-20110,Ryan Nelson,Consumer,Manchester,2019-03-07,TV + Broadband,35,Active,447700900110
CUST-20111,Poppy Clarke,Consumer,Birmingham,2020-01-29,Volt Bundle,12,Active,447700900111
CUST-20112,Christopher Moore,Consumer,Brighton,2022-07-04,Volt Bundle,7,Active,447700900112
CUST-20113,Michael Green,Consumer,Birmingham,2017-07-30,TV + Broadband,67,Active,447700900113
CUST-20113,Michael O'Sullivan,Consumer,Wolverhampton,2017-07-30,TV + Broadband,67,Active,447700900113
CUST-20114,Ava King,Consumer,Leicester,2024-01-23,Mobile + TV,12,Active,447700900114
CUST-20115,Joseph Lewis,Consumer,Leeds,2018-05-01,TV Only,103,Active,447700900115
CUST-20116,David Phillips,Consumer,Nottingham,2021-04-08,Broadband Only,62,Active,447700900116
CUST-20117,Elizabeth Lopez,Consumer,Leicester,2017-09-04,TV Only,100,Active,447700900117
CUST-20118,Ryan Thompson,Consumer,Bristol,2024-05-29,Volt Bundle,26,Active,447700900118
CUST-20119,Abigail Johnson,Consumer,Liverpool,2022-01-20,Mobile + TV,82,Active,447700900119
CUST-20120,Sophia Garcia,Consumer,Bristol,2024-11-19,Business Broadband,64,Active,447700900120
CUST-20121,Freddie Robinson,Consumer,Cardiff,2023-08-13,Mobile + TV,108,Inactive,447700900121
CUST-20122,Charlotte Taylor,Consumer,Cardiff,2018-09-03,TV + Broadband,24,Active,447700900122
CUST-20123,Jack Lewis,Consumer,Leicester,2020-03-28,Broadband Only,21,Active,447700900123
CUST-20124,Poppy Collins,Consumer,Bristol,2022-08-12,TV Only,69,Active,447700900124
CUST-20125,David Williams,SMB,Reading,2020-08-13,TV Only,38,Active,447700900125
CUST-20126,Freddie Edwards,Consumer,Leicester,2023-08-02,Volt Bundle,103,Active,447700900126
CUST-20127,Amelia Perez,Consumer,Brighton,2018-12-19,Broadband Only,72,Active,447700900127
CUST-20128,Amelia Harris,SMB,Liverpool,2024-02-14,Business Broadband,68,Inactive,447700900128
CUST-20129,Michael Allen,Consumer,Glasgow,2024-07-07,Volt Bundle,26,Active,447700900129
CUST-20130,Christopher Adams,Consumer,Liverpool,2023-03-04,Volt Bundle,64,Active,447700900130
CUST-20131,Henry Walker,Consumer,Brighton,2021-07-14,Business Broadband,71,Inactive,447700900131
CUST-20132,Emma Evans,SMB,Sheffield,2021-08-20,Volt Bundle,30,Active,447700900132
CUST-20133,Sofia Rogers,Consumer,Sheffield,2017-07-31,Mobile Only,40,Active,447700900133
CUST-20134,Oscar Hill,SMB,Sheffield,2018-05-13,Volt Bundle,86,Active,447700900134
CUST-20135,Ella Stewart,Consumer,Nottingham,2017-02-26,TV Only,58,Active,447700900135
CUST-20136,George Scott,SMB,Cardiff,2018-09-23,Broadband Only,97,Active,447700900136
CUST-20137,Zoe Clark,Consumer,Sheffield,2022-04-19,Mobile Only,64,Active,447700900137
CUST-20138,Mason Martin,SMB,Nottingham,2018-07-14,Business Broadband,14,Active,447700900138
CUST-20139,Logan Hall,SMB,Nottingham,2019-12-31,Business Broadband,6,Active,447700900139
CUST-20140,Poppy Roberts,Consumer,Cardiff,2022-06-29,Business Broadband,25,Active,447700900140
CUST-20141,Michael Allen,Consumer,Brighton,2023-02-04,Broadband Only,64,Inactive,447700900141
CUST-20142,Leo Collins,Consumer,Liverpool,2019-08-15,Business Broadband,105,Active,447700900142
CUST-20143,Ethan Morris,Consumer,Brighton,2021-04-11,Broadband Only,90,Inactive,447700900143
CUST-20144,Victoria Jackson,Consumer,London,2018-06-02,TV Only,81,Active,447700900144
CUST-20145,Isla Hill,Consumer,Sheffield,2017-03-04,Mobile + TV,24,Active,447700900145
CUST-20146,Victoria Jackson,Consumer,Brighton,2019-12-22,TV + Broadband,85,Active,447700900146
CUST-20147,Victoria Davies,SMB,Cardiff,2022-12-26,Broadband Only,46,Active,447700900147
CUST-20148,Ryan Adams,SMB,London,2023-12-05,Volt Bundle,36,Active,447700900148
CUST-20149,Oscar Garcia,Consumer,Liverpool,2018-02-08,Business Broadband,87,Active,447700900149
CUST-20150,Isla Hill,Consumer,Bristol,2017-04-29,Volt Bundle,47,Inactive,447700900150
CUST-20151,Oscar Allen,Consumer,Birmingham,2019-09-28,TV Only,58,Active,447700900151
CUST-20152,Grace White,Consumer,Leicester,2021-04-16,TV Only,93,Active,447700900152
CUST-20153,Elizabeth Jackson,Consumer,Cardiff,2019-11-07,Broadband Only,38,Active,447700900153
CUST-20154,Amelia Rodriguez,Consumer,Birmingham,2017-10-30,Broadband Only,50,Inactive,447700900154
CUST-20155,Poppy Cook,SMB,Reading,2019-10-22,Broadband Only,44,Active,447700900155
CUST-20156,Mason Green,Consumer,Liverpool,2023-06-01,TV + Broadband,79,Active,447700900156
CUST-20157,Christopher Rodriguez,Consumer,Cardiff,2021-06-10,TV + Broadband,7,Active,447700900157
CUST-20158,Hannah Reed,Consumer,London,2023-10-20,Mobile + TV,69,Inactive,447700900158
CUST-20159,Oscar Reed,Consumer,Leicester,2020-12-14,Mobile Only,87,Active,447700900159
CUST-20160,Henry Edwards,Consumer,Brighton,2024-05-24,Mobile + TV,23,Active,447700900160
CUST-20161,Aaron Parker,Consumer,Brighton,2021-12-11,Volt Bundle,80,Active,447700900161
CUST-20162,Harry Davies,SMB,Glasgow,2021-08-29,Mobile Only,31,Active,447700900162
CUST-20163,Matthew Young,Consumer,Bristol,2018-11-05,TV + Broadband,67,Inactive,447700900163
CUST-20164,Oscar Morris,SMB,Brighton,2018-04-17,Broadband Only,15,Active,447700900164
CUST-20165,Freddie Edwards,Consumer,Liverpool,2023-04-02,TV + Broadband,17,Inactive,447700900165
CUST-20166,Emma Robinson,Consumer,Sheffield,2021-02-18,Mobile + TV,101,Active,447700900166
CUST-20167,Elizabeth Hernandez,Consumer,Glasgow,2018-03-20,Mobile + TV,35,Active,447700900167
CUST-20205,Daniel Foster,SMB,Blackpool,2020-06-30,Broadband Only,58,Active,447700900205
CUST-20168,Sofia Mitchell,Consumer,Leicester,2019-06-26,Mobile + TV,14,Active,447700900168
CUST-20169,Amelia Collins,Consumer,Liverpool,2018-04-23,Mobile Only,11,Inactive,447700900169
CUST-20170,Poppy Adams,Consumer,Leeds,2023-01-11,Mobile Only,55,Active,447700900170
CUST-20171,Joshua Morris,Consumer,Nottingham,2021-09-13,TV Only,101,Active,447700900171
CUST-20172,Logan Parker,Consumer,Sheffield,2023-11-27,Broadband Only,41,Active,447700900172
CUST-20173,Isabella Thompson,Consumer,Leeds,2021-01-25,Volt Bundle,93,Active,447700900173
CUST-20174,Victoria Allen,Consumer,Bristol,2019-02-17,Volt Bundle,64,Active,447700900174
CUST-20175,Lily Parker,Consumer,London,2017-07-27,Business Broadband,48,Active,447700900175
CUST-20176,Harry Perez,Consumer,Brighton,2023-03-21,Mobile Only,81,Active,447700900176
CUST-20177,Freddie Hall,Consumer,Brighton,2023-09-08,Volt Bundle,41,Inactive,447700900177
CUST-20178,Mia Moore,Consumer,Brighton,2018-12-16,Volt Bundle,90,Inactive,447700900178
CUST-20179,Harry Clarke,Consumer,Brighton,2019-09-02,TV Only,47,Active,447700900179
CUST-20180,Henry Brown,Consumer,Liverpool,2022-11-25,Volt Bundle,101,Active,447700900180
CUST-20181,Jacob Reed,Consumer,Leicester,2018-03-23,Broadband Only,70,Active,447700900181
CUST-20182,Sofia Williams,Consumer,Cardiff,2022-11-06,TV + Broadband,64,Active,447700900182
CUST-20183,James Brown,SMB,Liverpool,2021-10-13,Mobile + TV,19,Active,447700900183
CUST-20184,Jacob Johnson,SMB,Glasgow,2023-10-28,Mobile Only,14,Active,447700900184
CUST-20185,Sofia Cook,Consumer,Reading,2020-08-24,Broadband Only,82,Active,447700900185
CUST-20186,Amelia Baker,Consumer,Manchester,2024-11-14,Volt Bundle,89,Active,447700900186
CUST-20187,Natalie Mitchell,Consumer,Leeds,2021-10-28,Broadband Only,35,Active,447700900187
CUST-20188,Amelia King,Consumer,Manchester,2020-07-04,Broadband Only,46,Active,447700900188
CUST-20189,Isabella Jackson,Consumer,Sheffield,2017-10-02,Volt Bundle,16,Active,447700900189
CUST-20190,Isla Morris,Consumer,Brighton,2018-06-17,TV Only,13,Active,447700900190
CUST-20191,Abigail Mitchell,Consumer,Manchester,2021-08-10,TV + Broadband,91,Inactive,447700900191
CUST-20192,Charlotte Sanchez,Consumer,Bristol,2023-09-26,TV + Broadband,51,Active,447700900192
CUST-20193,Daniel Thompson,Consumer,Sheffield,2019-07-08,Business Broadband,19,Active,447700900193
CUST-20194,Abigail Young,Consumer,Bristol,2023-06-10,Mobile Only,109,Active,447700900194
CUST-20195,Abigail Reed,Consumer,Leicester,2024-07-27,Mobile + TV,77,Active,447700900195
CUST-20196,Joshua Collins,Consumer,Birmingham,2020-01-25,Mobile + TV,103,Active,447700900196
CUST-20197,Emily Allen,Consumer,Birmingham,2023-05-09,Mobile + TV,57,Active,447700900197
CUST-20198,Layla Cook,SMB,Manchester,2022-12-13,Mobile Only,54,Active,447700900198
CUST-20199,Emily White,Consumer,Reading,2020-08-21,Business Broadband,78,Active,447700900199
CUST-20200,Oliver Jackson,Consumer,Leicester,2017-07-23,Mobile + TV,16,Active,447700900200
CUST-20204,Chloe Dawson,Consumer,Blackpool,2023-02-18,TV + Broadband,21,Active,447700900204
CUST-20204,Bukayo Saka,Consumer,London,2023-02-18,TV + Broadband,24,Active,447700900204
```

*FOLOWING CHALLENGE TIME*

*COPY OVER*

**SIMPLE SOLUTION**
```python
import csv

with open("vmo2-customers.csv", "r", encoding="utf-8") as f:
    customer_list = list(csv.DictReader(f))


def find_customers(customers, region):
    targeted_customers = []
    for customer in customers:
        if customer["region"] == region and customer["customer_status"] == "Active":
            targeted_customers.append(customer)
    return targeted_customers


contact_list = find_customers(customer_list,  "Blackpool")

print(contact_list)
```

So here's my solution

- We grab the data as we've seen before and store it to a variable, 'customer_list'
- The function I've written recieves that value on the 'customers' parameter but I could have easily hardcoded it directly into the function
- We define a new list, 'targeted_customers' inside the function code block
- loop over all the data, any customer with the region we're interested in, who's also active, we append to our new list, 'targeted_customers'
- which we return

*RUN* - `python main.py`


In our mock data, we're quite fortunate, there's only a few entries which relate the **blackpool**. 

Let me quickly search for customers if our works were happening in London. 

*SWAP BLACKPOOL FOR LONDON AND RUN* `python main.py`

It's hardly pleasing to look at

I've defined an alternative solution which, just tidies up the data a little but.

I'll copy it over

**CLEAN SOLUTION**
```python
import csv

with open("vmo2-customers.csv", "r", encoding="utf-8") as f:
    customer_list = list(csv.DictReader(f))


def find_customers(customers, region):
    targeted_customers = []
    for customer in customers:
        if customer["region"] == region and customer["customer_status"] == "Active":
            user = {
                "customer_id": customer["customer_id"],
                "name": customer["customer_name"],
                "contact_number": customer["contact_number"],
                "location": customer["region"]
            }
            targeted_customers.append(user)
    return targeted_customers


contact_list = find_customers(customer_list,  "London")

print(f"There are {len(contact_list)} members to contact:")

for customer in contact_list:
    print(f"{customer["customer_id"]} - {customer["name"]}, {customer["contact_number"]} ({customer["location"]})")
```

What I've changed is that, inside the for loop, for each row of data which in this case is for an active London customer I pull out the data I care about and use it to create a smaller dictionary, with less data. 

The original CSV had information about their product_bundle, join_date. If it's distracting and not relevant, I can remove it. 

Then I just have two new pieces of the code at the bottom. 

- One to tell me how long the new list is
- The second to return the data in a formatted string from within a loop

I do have one more potential improvement we could impliment. 

Who's to say, we couldn't be making improvements in 2027, not only in Blackpool, but in London, Cardiff and Wolverhampton. 

If this were to be the case, the function as it is won't work. This is a very real chance for our **variadic functions** to show their quality. 

Let me show you the final iteration of this solution I wrote. 

**COMPLEX SOLUTION**
```python
import csv

with open("vmo2-customers.csv", "r", encoding="utf-8") as f:
    customer_list = list(csv.DictReader(f))


def find_customers(customers, *region):
    targeted_customers = []
    for customer in customers:
        if customer["region"] in region and customer["customer_status"] == "Active":
            user = {
                "customer_id": customer["customer_id"],
                "name": customer["customer_name"],
                "location": customer["region"],
                "contact_number": customer["contact_number"]
            }
            targeted_customers.append(user)
    return targeted_customers


contact_list = find_customers(customer_list, "Blackpool")

print(f"There are {len(contact_list)} members to contact:")

for customer in contact_list:
    print(f"{customer["customer_id"]} - {customer["name"]}, {customer["contact_number"]} ({customer["location"]})")
```

Very similar function but we have room for *args now on the region variable. 

*RUN* `python main.py`

Aside from that, there's one important other difference. 

In our **if** statement, we checked whether the region we passed in was equal to the value held against the region key on the data. 

That's an awkward bit of logic to translate, when we have the possibility for multiple arguments being recieved. 

Earlier in the day, we saw that information arrised in a tuple. 

We haven't seen it, but the code `if customer["region"] in region` basically checks whether that value on the 'customer region' key exists in any of the values the region tuple may include. 

So now I can write in lots of different values and use my function a lot more freely. 

*RUN CODE WITH MULTIPLE VALUES*

---

*BREAK*



## 📦 Topic 5 — Packages and Imports

So far we've been working out of one Python file. it's nice but it isn't sustainable:

**ASK**
Does anyone fancy a guess how many lines of code are used in the Airbus A380?
**ANSWER**
100 million lines of code

All that code helps to get the plane off the ground, keep it in the air and probably provide the inflight entertrainment. 

Imagine how it'd be to have one file, 100 million lines long?

We're getting to the point where we need to organise our code a little more efficiently. 


We've already seen Python’s import system, handling externally defined functionality like **json**, **requests** and **datetime**

It makes using fuctionality, not defined in the file we're in, easy to use.

In professional projects, good structure enables testing, good documentation and just an ease of navigation to find what you're looking for. 


### Structuring a Simple Package

Let's start off by creating a file structure to replicate something a little more complex. 

I'm going to delete everything currently here, aside from **main.py**

*DELETE ALL FILES BUT main.py*

I now want a section of my code which is going to relate to **networking**. I'm not a VMO2 network engineer but I'm going to say for this purpose I want some functionality which can mock a connection to the different devices a user may have to try and connect to them


1. I've got a file called **main.py**
2. I'll create a folder at the root of the project called **network_tools**
3. Then inside that folder create two files **reboot.py** and **monitor.py**


```bash
.
├── main.py
└── network_tools
    ├── reboot.py
    └── monitor.py
```

What I'm trying to suggest through this file structure is there's a specific place where relating code should live. 

If there was functionality for customers, could be be it's own folder. Then it's straight forward to find what you're after. 

Let's add some code to our files

All I want to create a function which will simulate the process of rebooting a device

**reboot.py**
```python
# Import the random module, which will give us access to some fun functions
import random

def reboot_device(device):
    """
    Simulates rebooting a customer device.
    """
    print(f"Rebooting {device}...")
    # I'll use the rand-int function from the random module
    # It takes two arguments, which returns a random number between the two, inclusive of both
    number = random.randint(0, 10)
    if number > 2:
        print(f"{device} successfully rebooted.")
        return True
    else:
        print(f"{device} failed to reboot")
        return False
```

The function basically fakes an effort to reboot a device.

There's a high probability it'll succeed, if it does it'll return True, otherwise False

Now let's create another function which will test a connection

**monitor.py**
```python
# I'll import the time module here
import time

def test_connection(device):
    """
    Simulates testing connection to device.
    """
    print("Connecting...")
    # time.sleep(1) will pause the script for 1 second
    time.sleep(1)

    print("Connecting...")
    time.sleep(1)

    print("Connecting...")
    time.sleep(1)

    print(f"Running connection test for {device}... Connection OK.")
```

Let's try and consume these tools in **main.py**, because individually, they don't really mean much

**main.py**
```python
from network_tools.reboot import reboot_device
from network_tools.monitor import test_connection
```

If we're importing from outside the file, we introduce the 'from' keyword and then reference a relative file path from where we want to retrieve that import 

So from the 'network_tools' folder, we go into the 'reboot.py' file, we don't need to include the file extension. From that file we import the function 'reboot_device'

Let's see if our DocStrings are working.

**main.py**
```python
from network_tools.reboot import reboot_device
from network_tools.monitor import test_connection

help(reboot_device)
```

*RUN* `python main.py`

Now let's just try and use these two pieces of functionality here. 

**main.py**
```python
from network_tools.reboot import reboot_device
from network_tools.monitor import test_connection

reboot_succeeded = reboot_device("Router")

if reboot_succeeded == True:
    test_connection("Router")
```
*RUN* `python main.py`


- `__pycache__` called dunder pycache, is automtically created to store bytecode to make loading of functionality quicker, if you've noticed that. 

*BREAK*

---

## 🧱 Topic 6 — Classes and Objects

We're going to wrap up today looking at **classes** and **object orientated programming**

Last session we touched on the Zen of Python, how Python wants to be coded; it priotised ease of use and readability. 

Additionally to this, there's a main paradigm or approach about how code should be organised in Python. 

That is to model real-world entities using objects. 

Underneath the surface, everything in Python is actually an object and all objects are generated from classes.

To quickly show you.

*COPY CODE*

**main.py**
```python
name = "Emile"
age = 34
training = True
locations_lived = ["London", "Wolverhampton", "Colchester"]

print(type(name))
print(type(age))
print(type(training))
print(type(locations_lived))
```

*RUN* `python main.py`

The type function is is outputting the datatype passed in the argument :
- string
- int
- bool
- list

But I want to bring your attention to the 'class' keyword. All these datatypes originate from a class which creates these objects. 

Those classes define the data and behaviours objects created from that class have access to. It's hard to really understand Python code until we understand classes and Object Orientated Programming.

Imagine we worked for a car manufacturer. I've never worked in manufacturing but it's fair to assume before a factory starts putting a vehicle together, a team of designers will sketch out what features the car will have:
- The number of wheels
- The type of doors
- The engine

I don't have a driving license if it not already obvious. 


But following that design process, every time we wanted to build a new car, we'd take that design or blueprint and then go away and build the car.

It means that all the vehicles coming off the factory line are going to be standardised, uniform and it's much quicker than having the create a new design for every single car.

There can be alterations to that design, for instance if it's for the UK or Irish market the steering wheel will be on the right hand side or if it's for the continental European market the steering wheel will be on the left but that underlying blueprint is still useful. 

That initial blueprint is similar to classes in Python. They combine the data and behaviour objects in our program need to have, then allows us to create them at scale. 

For a car, the **data** maybe
- type of engine
- number of doors
- or milage

Where the **behaviours** would be, what can the car do:
- the ability to go forward
- indicate 
- wind down a window 

**IF ASKED**
- Encapsulation: Bundling data and the methods that operate on it within a class, while restricting direct access to protect the object’s internal state.
- Abstraction: Hiding complex implementation details and exposing only the essential features of an object through a simple interface.
- Inheritance: Allowing a class to acquire properties and behaviors from another class to promote code reuse and hierarchy.
- Polymorphism: Enabling objects of different classes to be treated through the same interface, typically by method overriding or overloading.
**END**

A common class which may be used in Python would be a class for a customer. 

It'd be helpful because firstly, there may be many customers, they'll all have their individual but relating data.

Their:
- name
- their internet speed
- the package their on
- an email
- whatever it may be

Additionally as customers, they'll also share a common set of behaviours, the ability to:
- upgrade a service
- cancel a membership
- see their latest bill


Let's actually create our own class, it'll be a limited one, it's best to understand the principles rather than get lost in the technicalities of a really extensive class. 


The class we'll create, is going to stipulate all the data and behaviours we can expect for our customers to have. 

For our use case I'm going to say every customer can have a:
- name
- an internet speed

Then as far as behaviours go, they'll be able to:
- say hello and tell us their name and internet speed


### Build and Extend Classes

If **def** is for definition which creates a function. We'll use **class** to define a class.

**main.py**
```python
class Customer:
```

You'll notice that we use a capitalised letter on the first character, which is fairly unique to creating classes in Python. It's not a strict rule but it helps us distinguise classes from other variables. 

Equally the colon on the end suggests the beginning of a code block. 

Every time a class is called to create a new object, under-the-hood a function fires, which we'll need to define. 

That function is called **__init__**. 

**main.py**
```python
class Customer: 
    # NEW CODE
    def __init__(self, name, speed):
```



- It's the name of the function Python recognises to build class instances
  - The instance is any object created from a class
- Like other functions, we can pass in parameters and we're allowing this constructor to receive information about a customers 'name' and 'speed'
- `self` is a reference to the new object being created, it allows the instance to access it's own data, generally we'll use it as the first parameter whenever an object needs to understand its own data
  - That initially sounds quite confusing, but we'll see it in action soon

Inside the constructer functions code block I just need to assign the values to `self`
**main.py**
```python
class Customer: 
    def __init__(self, name, speed):
        # NEW CODE
        self.name = name
        self.speed = speed
```

Let me create some instances then from this class. 

**main.py**
```python
class Customer: 
    def __init__(self, name, speed):
        self.name = name
        self.speed = speed

emile_customer = Customer("Emile", 500)
simon_customer = Customer("Simon", 200)

print(emile_customer.name)
print(simon_customer.speed)
```

*RUN CODE*

When dealing with dictionaries, we've had to to use **square bracket notation** to access keys, now we're using a different datatype objects, so we use **dot notation** instead.

Hopefully though, what we're seeing is once we've created our **class**, then it gets quite easy to create different objects from them. 

It's worth remembering that this is all Python, I can add default parameters and process data as it arrives. 

**main.py**
```python
class Customer:
    # UPDATED CODE
    def __init__(self, name, speed: 500):
        # UPDATED CODE
        self.name = name.title()
        self.speed = speed

# UPDATED CODE
emile_customer = Customer("emile", 500)
simon_customer = Customer("Simon", 200)

print(emile_customer.name)
print(simon_customer.speed)
```

I'll remove these for the timebeing

**main.py**
```python
class Customer:
    def __init__(self, name, speed):
        self.name = name
        self.speed = speed

emile_customer = Customer("Emile", 500)
simon_customer = Customer("Simon", 200)

print(emile_customer.name)
print(simon_customer.speed)
```

Let's move onto the behaviours. 

Defining functions within classes is actually quite simple. 

Same **def** keyword and regular syntax. 

The main thing to remember is if you want the method to refer to any data of an individual instance we have to pass the `self` keyword as a parameter. 

```python
class Customer:
    def __init__(self, name, speed):
        self.name = name
        self.speed = speed

    # NEW CODE
    def describe(self): 
        return f"{self.name} has {self.speed} Mbps broadband."

# NEW CODE
emile_customer = Customer("Emile", 500)
print(emile_customer.describe())
```


From this point, any customer we create will all share the same features and functionality as they've been created from the same blueprint. 

It makes our code predictable, maintainable and reusable - all the things we want. 


## OPTIONAL END POINT


Let's speak about extending this class.

**inheritance** is one of the most important features of classes in Python. 

If we've built a fairly broad class for a Customer, we could get to the point where the data and behaviours related to that customer have grown quite a lot and become hard. 

We might have added functionality which relates to:
- retail customers
- business customers
- private indivduals 

At that point, it's much easier to say: "Ok, instead of an instance of a 'Customer', I want an instance, specifically of a 'Business Customer' which can utilise the shared functionality of the base customer but also has custom data and behaviour. 

This is what I want to do with out Customer class

**main.py**
```python
class Customer:
    def __init__(self, name, speed):
        self.name = name
        self.speed = speed

    def describe(self): 
        return f"{self.name} has {self.speed} Mbps broadband."

# NEW CODE
class BusinessCustomer(Customer):
    def __init__(self, name, speed, discount):
```

We define our class as normal but provide the super or parent class into the parenthesies


The parent Customer class is responsible for assigning the **name** and **speed** to the instance, what we do is call the parent class constructor from within the child constructor

**main.py**
```python
class Customer:
    def __init__(self, name, speed):
        self.name = name
        self.speed = speed

    def describe(self): 
        return f"{self.name} has {self.speed} Mbps broadband."


class BusinessCustomer(Customer):
    def __init__(self, name, speed, discount):
        # NEW CODE
        super().__init__(name, speed)
        self.discount = discount
```

Super is short for superclass and simply means, "go to the parent class", then on the parent class call the constructor function 

We can see this in action by adding some print statement

**main.py**
```python
class Customer:
    def __init__(self, name, speed):
        self.name = name
        self.speed = speed
        # NEW CODE
        print("Customer constructor firing")

    def describe(self): 
        return f"{self.name} has {self.speed} Mbps broadband."


class BusinessCustomer(Customer):
    def __init__(self, name, speed, discount):
        super().__init__(name, speed)
        self.discount = discount
        # NEW CODE
        print("BusinessCustomer constructor firing")

lafosse = BusinessCustomer("LaFosse", 400, 20)
```

*RUN CODE*

So we can see the parent classes constructor function runs, then we fall back into the BusinessCustomer constructor and assign the discount property to the instance

The child class of BusinessCustomer, will have all the functionality, data and behaviours of the Customer, but any instance of the Customer class won't inherit any functionality from it's child. 

So if our BusiessCustomer can access behaviours which are unique to it; only instances of the BusinessCustomer or children of that class will have that functionality.

I'm going to define a new piece of data and method which only our business customer can access. I'll also clean up the print statements. 

**main.py**
```python
class Customer:
    def __init__(self, name, speed):
        self.name = name
        self.speed = speed

    def describe(self): 
        return f"{self.name} has {self.speed} Mbps broadband."


class BusinessCustomer(Customer):
    # UPDATED CODE
    def __init__(self, name, speed, discount, account_mananger):
        super().__init__(name, speed)
        self.discount = discount
        # UPDATED CODE
        self.account_mananger = account_mananger

    # NEW CODE
    def call_account_manager(self):
        print(f"Calling {self.account_mananger}")

lafosse = BusinessCustomer("LaFosse", 400, 20, "Abraham Andrews")
lafosse.call_account_manager()
```

If I tried to assign that behaviour to a regular customer then it wouldn't work. 

**main.py**
```python
class Customer:
    def __init__(self, name, speed):
        self.name = name
        self.speed = speed

    def describe(self): 
        return f"{self.name} has {self.speed} Mbps broadband."


class BusinessCustomer(Customer):
    # UPDATED CODE
    def __init__(self, name, speed, discount, account_mananger):
        super().__init__(name, speed)
        self.discount = discount
        # UPDATED CODE
        self.account_mananger = account_mananger

    # NEW CODE
    def call_account_manager(self):
        print(f"Calling {self.account_mananger}")

# lafosse = BusinessCustomer("LaFosse", 400, 20, "Abraham Andrews")
# lafosse.call_account_manager()

emile = Customer("Emile", 400)
emile.call_account_manager()
```

*RUN CODE*

This is dissapointing! 

# END



# CHALLENGE

There's a lot of useful things you can try and attempt if you wish. We had the function challenges from the first session and if you fancy something else, I'd recommend looking accessing the customer csv data again. 

It'd be possible to combine a few of the elements which we've looked at today and extend our customer class where each customer has a function which can pull from a CSV file their own information. 



























## Challenge

That's us done for today - as with last time there's some challenges available for you with the time that's left or for you in your own time. 

It's worth knowing that when we engage with code, the vast majority of the time we spend reading code or refactoring code rather than starting fresh from an empty folder. 

With this in mind I've taken the liberty of using a few off the concepts we've covered so far and built a mini project. 

The idea is that I can create a staff member and give them devices to work and call their colleagues. 

Any call which is made is logged to a JSON file. 

Let me show you: https://github.com/emilesherrott/python-staff-device-example
*CLICK GREEN Code BUTTON*
*CLICK Codespaces ON TOP TAB*
*CLICK ON BRANCH OR CREATE NEW ONE*

What we can see is a fairly limited file structure. 

If we start in **devices**

**__init__.py** basically takes our exports and bundles them into one file
```python
from .base_device import Base_Device
from .computer import Computer
from .phone import Phone
```

Then we have a parent class **Base Device** and two child classes **Computer** and **Phone**
- The computer has the ability to compute
- The phone doesn't have any behaviours defined directly on it

Then we can look at **staff**, there's a similar **__init__.py** file to export functionality but in the **staff member** file there's some interesting code. 

Let's ignore the imports to begin with

```python
class Staff_Member():
    def __init__(self, name, department, role):
        self.name = name
        self.department = department
        self.role = role
        self.devices = None
```

We can see in the constructor we allow to pass information in for the:
- name
- department
- role
We also give the member a property for **devices**, initially set to None. There's no way to create a new staff membmer already with devices assigned. 

```python
    def add_device(self, device):
        if self.devices is None:
            self.devices = []
        self.devices.append(device)
```

The next thing worth mentioning is that each staff member as the ability to add a device
When we initially create the staff membmer their devices property is None so always first assign an empty list to each member then we append the device to that list. If we add any further devices we just append to the list. 

I'm going to skip past the **show_devices** function and talk about **work**

```python
    def work(self):
        computer = None
        for device in self.devices:
            if isinstance(device, Computer):
                computer = device
        
        if computer:
            print(f"{self.name} is currently {computer.compute()}")
        else:
            print("No computer to work with")
```

In my profression, I can't really work without a computer so the first thing the method tries to establish is whether the staff member actually has a computer. 

We look over the devices and then we have some new code `isinstance` tags two arguments, the object and then the class, if the object is an instance of the class it returns true. 

If an member of staff then has a computer, we take that computer object and assign it to a computer variable. 

I spent the most time looking at the ability to **call**

```python
    def call(self, target):
        phone = None
        for device in self.devices:
            if isinstance(device, Phone):
                phone = device
        
        target_phone = None
        for device in target.devices:
            if isinstance(device, Phone):
                target_phone = device

        if phone and target_phone:
            call_log = {
                "time": datetime.now().strftime("%Y-%m-%d %H:%M:%S"),
                "caller": self.name,
                "caller_number": phone.number,
                "target": target.name,         
                "target_number": target_phone.number       
            }

            add_call_log(self, call_log)
            print(f"{self.name} calling {target.name} on {target_phone.number}")
```

The logic is similar but different

If I want to call a colleague, it stands to reason that I need a phone and the person I'm calling needs a phone. 

We can see the function takes a parameter for the **target** which is expected to be another instance of the **staff member** class.

Then we use the same logic to check whether both members have a phone. 

```python
        if phone and target_phone:
            call_log = {
                "time": datetime.now().strftime("%Y-%m-%d %H:%M:%S"),
                "caller": self.name,
                "caller_number": phone.number,
                "target": target.name,         
                "target_number": target_phone.number       
            }

            add_call_log(self, call_log)
            print(f"{self.name} calling {target.name} on {target_phone.number}")
```

If both do, we then basically create a Python dictionary with information about the call. We've seen **datetime.now()** before but this method and argument basically returns the value as a formatted string. 

Lastly we call a seperate function and pass in **self** which we know contains the data about the instance executing the method and then the call log dictionary. 

The final piece if the **add_call_log** function

```python
import os
import json

def add_call_log(staff_member, call_data):
    parent_folder = "logs"
    folder = staff_member.name.lower()
    full_folder_path = os.path.join(parent_folder, folder)
    os.makedirs(full_folder_path, exist_ok=True)
    file_path = os.path.join(full_folder_path, "call_log.json")


    if os.path.exists(file_path):
        with open(file_path, "r", encoding="utf-8") as f:
            try:
                logs = json.load(f)
            except json.JSONDecodeError:
                logs = []
    else:
        logs = []

    logs.append(call_data)

    with open(file_path, "w", encoding="utf-8") as f:
        json.dump(logs, f, indent=4)    
```

The parameters are **staff member** and **call data** which positionally represent the instance which called the function and the log data when we called the method. 

All we do here is write to a JSON file the call log data. 

The **if statement** basically checks in any logs exist already, if so we load them into our logs variable, otherwise we create a list. 

Either way we append the new data to the list before writing back to the file.

Finally we put it all together in **main.py**

We create phones, computers and staff members and make a call. 

*RUN CODE main.py*

That was quick

## TASKS

As part of the task I really want you to spend time reading through the file
- Understand the links between different pieces of code
- Trace data through the functions
- Have a go creating your own staff members and devices 

Once you're fairly comfortable with how things work there's a few directions you could take it. 

- In the **staff member** class, I could pass in any device, you could write some code which ensures a device is only added if it's a Phone or Computer. 
- Create some Docstrings and Typehints to make the file more readable 
- You can create your own child class of **base device** in order to extend the functionality of a staff member. 

- Another option would be to start from scratch and use this as a guide to create your own mini project, in my job I always lean on other code examples I've created to create new projects which follow similar design patterns or architecture. 


What I want you to do is take this code, read it and see how different pieces of functionality fit together. From that point feel free to either expand it with further devices

# TASKS
https://gist.github.com/emilesherrott/b42d4f67a16545b1d91d967741f38dfe
---


 # END



























































# OTHER

## Previously following TOPIC 4

I want to take a quick look at some errors which we may get. 

Errors happen in programming — maybe a file doesn’t exist or data is corrupted. 

If we don’t plan for them, the programme can crash and stop running. But Python lets us handle errors with some grace. 

By that I mean the program can still run and maybe give some information about what the error is. 

A message saying, *cannot perform operation, file doesn't exist* whilst not working, is better than an operation just not working and us not understanding why. 

You've heard me say, good code is readable and whilst that can relate to the code itself, having software which an engineer can navigate and understand what's happening is always a positive. 

We'll be using something called try and except blocks to handle these errors:

Inside the **try block** — we put the code that might fail. Python will attempt to run it.

Then we'll have an **except** — if an error is generated from within the try block, Python will jump to the corresponding except block instead of crashing.
**main.py**
```python
import json

# NEW CODE
try:

except:

data = {
    "customer": "Alex",
    "speed": 500,
    "plan": "Fibre Max"
    }

with open("customer.json", "w", encoding="utf-8") as f:
    json.dump(data, f, indent=4)

with open("customer.json", "r", encoding="utf-8") as f:
    loaded_data = json.load(f)

print("Loaded:", loaded_data)
```

Let me move everything into the **try** block and then in our **except** block I'm going to write a simple **print statement**

**main.py**
```python
import json

try:
    data = {
    "customer": "Alex",
    "speed": 500,
    "plan": "Fibre Max"
    }

    with open("customer.json", "w", encoding="utf-8") as f:
        json.dump(data, f, indent=4)

    with open("customer.json", "r", encoding="utf-8") as f:
        loaded_data = json.load(f)

    print("Loaded:", loaded_data)
except:
    print("Issue with customer.json file")
```

I want to trigger the **except** block to show you what I mean so I'm going to do two things quickly.

1. Comment out the lines of code which write and create the file
2. I'm going to introduce a spelling mistake into our json file
3. Write a print statement at the bottom to check the script can still continue after the error

**main.py**
```python
import json

try:
    data = {
    "customer": "Alex",
    "speed": 500,
    "plan": "Fibre Max"
    }

    # with open("customer.json", "w", encoding="utf-8") as f:
    #     json.dump(data, f, indent=4)

    with open("customer.json", "r", encoding="utf-8") as f:
        loaded_data = json.load(f)

    print("Loaded:", loaded_data)
except:
    print("Issue with customer.json file")


print("File end")
```

*CHANGE customer.json* TO custom.json*

I've not yet this script but essentially it wants to read from a file called **customer.json** and that doesn't exist so it should fail.

*RUN CODE*

Hopefully you'll all see the code inside the **except** block run and also the script continue to work. 

Right now our code handles every issue in the same way.

We've seen if the file's not found it results in an error. We can actually capture the error and see what it is.

**main.py**
```python
import json

try:
    data = {
    "customer": "Alex",
    "speed": 500,
    "plan": "Fibre Max"
    }

    # with open("customer.json", "w", encoding="utf-8") as f:
    #     json.dump(data, f, indent=4)

    with open("customer.json", "r", encoding="utf-8") as f:
        loaded_data = json.load(f)
        print("Loaded:", loaded_data)

# UPDATED CODE
# We're going to look at classes in a bit but 'Exception' is a class for blueprint to create data
# What we're doing is capturing the error as an exception, renaming the exception as e and print printing the type
except Exception as e:
    print("Issue with customer.json file", type(e))


print("File end")
```

*RUN CODE*

In the output we can see the error is specifically FileNotFoundError which adds up. 

There's many things which could go wrong with these operations, the file not existing is definitely one of them. 

The least we can do is let the programmer know exactly why the error has arisen. 

**main.py**
```python
import json

try:
    data = {
    "customer": "Alex",
    "speed": 500,
    "plan": "Fibre Max"
    }

    # with open("customer.json", "w", encoding="utf-8") as f:
    #     json.dump(data, f, indent=4)

    with open("customer.json", "r", encoding="utf-8") as f:
        loaded_data = json.load(f)
        print("Loaded:", loaded_data)

# UPDATED CODE
# This block only runs now specifically when the file isn't found
except FileNotFoundError:
    # UPDATED CODE
    # I can now be more specific with the print statemtn
    print("File not found, please check file system")

print("File end")
```

What you'll most likely see is developers link multiple **except blocks** to a single **try block** to handle different types of errors.

```python
import json 

try:
    with open("customer.json", "r", encoding="utf-8") as f:
        data = json.load(f)
        print("File read successfully:", data)

except FileNotFoundError:
    print("File not found, please check file system")

# NEW CODE
except json.JSONDecodeError:
    print("Invalid JSON data detected.")

# NEW CODE
except:
    print("Final except block to catch uncommon errors")
```

I'll change the file name back and introduce an error just to show off the other **except blocks**

- *CHANGE FILE NAME BACK TO customer.json*
- *INTRODUCE ERROR IN JSON*
- *RUN CODE*


All this does it mitigate any potential errors, if something goes wrong, we can handle it without the programme crashing. 

It's worth saying that we ordinarilly won't just write print blocks, we could write other code which potentially checks another location for the file or perhaps pulls data through another way. 






## OS

### OS Module

**main.py**
```python
import json
import os
```

As with everything we've looked at, we can go deeper and deeper into the tech.

It's not expected that you know everything by the way, more that you can implement the basics and research how to do things as and when the need arises. 

But the os module in Python lets your program go a little further and talk to your computer’s operating system — things like folders, files, and paths.

In this case I'm going to be dealing with some mock signal data and I want to store it into a specific file, away from other JSON. 

**main.py**
```python
import json
import os

# Example data that might be collected from a network engineering system.
signal_report = {
    "cell_id": "LON_0452_A",
    "site_name": "London Central",
    "timestamp": "2025-11-11T10:30:00Z",
    "operator": "VMO2",
    "frequency_band": "1800MHz",
    "signal_strength_dBm": -78,
    "signal_quality": "Good",
    "connected_users": 124,
    "uptime_percent": 99.97,
    "alerts": [],
}

# Create a variable which will hold the name of the folder
folder = "json_logs"
# Then we can access our operating system and digging into the os object access the 'join()' method which joins a folder to a file into a complete pathway
file_path = os.path.join(folder, "signal_report.json")

# Ensure the folder exists before writing
# 'exist_ok=True' basically says, if the folder exists don't raise an error
os.makedirs(folder, exist_ok=True)


with open(file_path, "w", encoding="utf-8") as f:
    json.dump(signal_report, f, indent=4)

print(f"Signal report saved to: {file_path}")
```

*RUN CODE*

We can read from this file in a similar way. 

*BREAK*





## Unknown


I want to take a quick look at some errors which we may get. 

Errors happen in programming — maybe a file doesn’t exist or data is corrupted. 

If we don’t plan for them, the programme can crash and stop running. But Python lets us handle errors with some grace. 

By that I mean the program can still run and maybe give some information about what the error is. 

A message saying, *cannot perform operation, file doesn't exist* whilst not working, is better than an operation just not working and us not understanding why. 

You've heard me say, good code is readable and whilst that can relate to the code itself, having software which an engineer can navigate and understand what's happening is always a positive. 

We'll be using something called try and except blocks to handle these errors:

Inside the **try block** — we put the code that might fail. Python will attempt to run it.

Then we'll have an **except** — if an error is generated from within the try block, Python will jump to the corresponding except block instead of crashing.
**main.py**
```python
import json

# NEW CODE
try:

except:

data = {
    "customer": "Alex",
    "speed": 500,
    "plan": "Fibre Max"
    }

with open("customer.json", "w", encoding="utf-8") as f:
    json.dump(data, f, indent=4)

with open("customer.json", "r", encoding="utf-8") as f:
    loaded_data = json.load(f)

print("Loaded:", loaded_data)
```

Let me move everything into the **try** block and then in our **except** block I'm going to write a simple **print statement**

**main.py**
```python
import json

try:
    data = {
    "customer": "Alex",
    "speed": 500,
    "plan": "Fibre Max"
    }

    with open("customer.json", "w", encoding="utf-8") as f:
        json.dump(data, f, indent=4)

    with open("customer.json", "r", encoding="utf-8") as f:
        loaded_data = json.load(f)

    print("Loaded:", loaded_data)
except:
    print("Issue with customer.json file")
```

I want to trigger the **except** block to show you what I mean so I'm going to do two things quickly.

1. Comment out the lines of code which write and create the file
2. I'm going to introduce a spelling mistake into our json file
3. Write a print statement at the bottom to check the script can still continue after the error

**main.py**
```python
import json

try:
    data = {
    "customer": "Alex",
    "speed": 500,
    "plan": "Fibre Max"
    }

    # with open("customer.json", "w", encoding="utf-8") as f:
    #     json.dump(data, f, indent=4)

    with open("customer.json", "r", encoding="utf-8") as f:
        loaded_data = json.load(f)

    print("Loaded:", loaded_data)
except:
    print("Issue with customer.json file")


print("File end")
```

*CHANGE customer.json* TO custom.json*

I've not yet this script but essentially it wants to read from a file called **customer.json** and that doesn't exist so it should fail.

*RUN CODE*

Hopefully you'll all see the code inside the **except** block run and also the script continue to work. 

Right now our code handles every issue in the same way.

We've seen if the file's not found it results in an error. We can actually capture the error and see what it is.

**main.py**
```python
import json

try:
    data = {
    "customer": "Alex",
    "speed": 500,
    "plan": "Fibre Max"
    }

    # with open("customer.json", "w", encoding="utf-8") as f:
    #     json.dump(data, f, indent=4)

    with open("customer.json", "r", encoding="utf-8") as f:
        loaded_data = json.load(f)
        print("Loaded:", loaded_data)

# UPDATED CODE
# We're going to look at classes in a bit but 'Exception' is a class for blueprint to create data
# What we're doing is capturing the error as an exception, renaming the exception as e and print printing the type
except Exception as e:
    print("Issue with customer.json file", type(e))


print("File end")
```

*RUN CODE*

In the output we can see the error is specifically FileNotFoundError which adds up. 

There's many things which could go wrong with these operations, the file not existing is definitely one of them. 

The least we can do is let the programmer know exactly why the error has arisen. 

**main.py**
```python
import json

try:
    data = {
    "customer": "Alex",
    "speed": 500,
    "plan": "Fibre Max"
    }

    # with open("customer.json", "w", encoding="utf-8") as f:
    #     json.dump(data, f, indent=4)

    with open("customer.json", "r", encoding="utf-8") as f:
        loaded_data = json.load(f)
        print("Loaded:", loaded_data)

# UPDATED CODE
# This block only runs now specifically when the file isn't found
except FileNotFoundError:
    # UPDATED CODE
    # I can now be more specific with the print statemtn
    print("File not found, please check file system")

print("File end")
```

What you'll most likely see is developers link multiple **except blocks** to a single **try block** to handle different types of errors.

```python
import json 

try:
    with open("customer.json", "r", encoding="utf-8") as f:
        data = json.load(f)
        print("File read successfully:", data)

except FileNotFoundError:
    print("File not found, please check file system")

# NEW CODE
except json.JSONDecodeError:
    print("Invalid JSON data detected.")

# NEW CODE
except:
    print("Final except block to catch uncommon errors")
```

I'll change the file name back and introduce an error just to show off the other **except blocks**

- *CHANGE FILE NAME BACK TO customer.json*
- *INTRODUCE ERROR IN JSON*
- *RUN CODE*


All this does it mitigate any potential errors, if something goes wrong, we can handle it without the programme crashing. 

It's worth saying that we ordinarilly won't just write print blocks, we could write other code which potentially checks another location for the file or perhaps pulls data through another way. 
