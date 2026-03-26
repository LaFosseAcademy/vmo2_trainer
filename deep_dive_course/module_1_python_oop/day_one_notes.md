# Advanced Python — Day 1

## Python Recap — Core Syntax & Concepts (Trainer Notes)

**Target delivery time:** ~ 1 Day
**Purpose:** Align the group on core Python fundamentals quickly so everyone starts the advanced material from the same baseline.  
**Trainer notes:** This is a *recap*, not a re-teach. Keep it fast, practical, and focused on habits that affect maintainability.

---

### Learning Outcomes
By the end of this section, learners will be able to:
- Explain how variables and assignment work in Python (names → objects).
- Identify and use core built-in data types appropriately.
- Apply control flow structures (`if`, loops) in a readable, professional style.

---

# Pre-Training

Load Slidee - **Day 1**

## Resources

- General: https://gist.github.com/emilesherrott/87216ff34dda8caf9e793fcfd1acb146
- Post Session Challenges: https://gist.github.com/emilesherrott/7eb0942982fa8bb65b04e4c39a141d61
- Post Session Challenge Solutions: https://gist.github.com/emilesherrott/c19a06d133ed311e793b7ac61f80a795

# Training Session

`SLIDE 1`

Hello everyone, really good to be back with you on the second part of this course. 

We're moving into what we'll call the Deep Dive, and we'll be taking a look into lots more of the things we can do in Python. 

I'm aware that some of those with us today weren't with us for the initial intro session. 

If I understand correctly some resources have been shared with you but regardless, today we're going to be going to be revisiting what we looked at previously, but in a little more detail, so there should be value in that for everone. 

Before we begin though, let's take a look at what we'll be covering in the next two and a half weeks. 



`SLIDE 2`

The first thing you'll notice is that there's a lot of content for us to be going through. You may have heard about of few of the acronyms jotted throughout the schedule, don't worry if they don't mean too much to you right now, we'll be looking at everything in more detail as we approach them. 

There's three things I want to highlighout though are that:

1. This is the only full day we'll have together, from tomorrow onwards we'll be meeting with each other every morning. From Tuesday 10th until Friday the 20th, that'll be from 09:00 until 12:20.
2. Which leads me onto my next point, between the 23rd and 25th, those days will run between 09:00 and 13:50 and that's because excitingly, you'll be working on a little applcation yourselves, in small groups. On the final day the 25th, hopefully you'll be able to present them back to the other members.
3. So, the final and third point I want to make is, whereas the previous two sessions, were me, primarily talking you through how things work. This new 'Deep Dive' will have more of an emphasis on you all getting hands on with the code yourself to build up your confidence in reading through programmes a bit more independantly, and ultimately creating some of your own.

# Begin Proper

So there's a lot to get through, I hope you're excited. Let's start by getting our codespace up and running. 

If you weren't on the previous section of the course, we need somewhere to write and inspect our code. We can do this on our own computers but we've been using an oline platform called **GitHUbCodespaces** so can we open a browser and Google **GitHub Codespaces**:

1. Click on the first result
2. Then the green **Get started for free button**
3. From that point we're going to use a blank template
4. Finally we just need a Python file to write and execute our code, so on the left hand side I'm going to click on the icon to create a new file and call it **main.py**

Just to make sure everyone is ok, on that file can we write **print("Hello World")**

**main.py**
```python
print("Hello World")
```

Then in the terminal at the bottom, run: `python main.py`

What this is doing, is taking the Python installed on the computer we're accessing and running it against the file **main.py**.

We've passed a string, which is the text *"Hello World"* wrapped in quotation marks and passed it to a function called print which basically outputs that message. 

## Variables and Assignment

We're going to start with covering variables. 

In Python as well as other programming languages a **variable** is a reference for an object. We usually think of them like **labels** or **name tags** for an object. The distinction to make is our variables are not the object themselves. 

Similar to how my name's **Emile**, **Emile** just refers to who I am but **Emile** isn't actually myself. I could dye my hair blonde, I could cut it off or change myself in a whole number of ways, the fundamental object would have changed but the reference **"Emile"** would stay the same. 

For those recently joining, all I'll do is define a quick variable now called greeting. No need to code along for this section.

**main.py**
```python
greeting = "Hello World"
print(greeting)
```

- *RUN* `python main.py`

If I change the underlying data, the reference to that data can stay the same.

**main.py**
```python
greeting = "Hello VMO2"
print(greeting)
```

- *RUN* `python main.py`

There's a good reason why programming languages behave this way - when we write code, that software runs on hardware and we want it to perform well on the hardware we have.  

Hardware can be expensive so software should try to be memory efficient.

It's reported that Netflix's annual spend on the computing power it uses from AWS is around 1 billion dollars, so if your software was 20% less efficient, that would mean a big cost in the computing power needed to accomodate that lost efficiency. 

I want to dig into that a little more. 

`SLIDE 3`

This image represents an object is stored in memory, in this case some information about me. We refer to that object with the reference **Emile** which we're able to use.

```python
# NEW CODE
emile = {
    "name": "Emile",
    "age": 34,
    "works_for": "La Fosse"
}

print(emile)
```

- *RUN* `python main.py`

This datatype is called a dictionary and as we can see, it stores lots of information on **key/value pairs**

Because we can refer to this data through a variable, I can pull out specific pieces of information.

```python
emile = {
    "name": "Emile",
    "age": 34,
    "works_for": "La Fosse"
}

# UPDATED CODE
print(emile["age"])
```

- *RUN* `python main.py`

Because **"emile"** is just a reference the actual object or data, we can assign another reference to it. 

Take my grandmother for example, as far as I remember, she's never called me "Emile", she likes to call me, "grandson". In this context both "emile" and "grandson" would point to the exact same object but go by difference names. 

```python
emile = {
    "name": "Emile",
    "age": 34,
    "works_for": "La Fosse"
}

# NEW CODE
grandson = emile

# UPDATED CODE
print(grandson["age"])
```

So the memory of this application still only has one object but we're allowed to refer to it via two. references or two variables. 

Single object, multiple references.

`SLIDE 4`

This is memory efficient, now take a much larger piece of data, rather than the one we have here. Instead of copying large objects, everytime we assign them to a variable, Python uses references which saves memory and makes operations faster. 

Because they point to the same object in the programmes memory, changes on one should show in the other. 

With dictionaries, I can target a key and print it, like we've seen but I can also update values as well. 

```python
emile = {
    "name": "Emile",
    "age": 34,
    "works_for": "La Fosse"
}

grandson = emile

# NEW CODE
grandson["age"] = 35

# UPDATED CODE
print(emile["age"])
```

- *RUN* `python main.py`

What we need to remember more than anything else is, we have data and we assign it to a variable as a reference. 

So the: 
- **variable name** is our **reference**
- The three key/value pairs inside the **dictionary** is our **data**
- the, the **equals sign** isn't a mathematical operations but it's assigning the **data** to the **variable**

And we'll see this a lot, we taking what's on the right hand side of the **assignment operator** and pass it to the variable on the left hand side. 

Remember the data, whatever the datatype is what's actually stored in memory. 

I'll tidy this up a little and just keep the **grandson** reference as well. 

**main.py**
```python
emile = {
    "name": "Emile",
    "age": 34,
    "works_for": "LaFosse"
}

grandson = emile
```

We can quite nicely use a built in function to see where the data is stored in memory. That function is called **id**

```python
emile = {
    "name": "Emile",
    "age": 34,
    "works_for": "La Fosse"
}

grandson = emile

print(id(emile))
```

- *RUN* `python main.py`

So what we're seeing is the id of an object, essentially it reveals inforation about where the data is stored

I have a question for you....

**ASK**
If I also added `print(id(grandson))` to the code, would the value be different?

```python
emile = {
    "name": "Emile",
    "age": 34,
    "works_for": "La Fosse"
}

grandson = emile

print(id(emile))

# NEW CODE
print(id(grandson))
```

- *RUN* `python main.py`

The same value, I do this, just to show under the hood that both variables point to the same data. 

I've another question, what if I do duplicate this data.

**main.py**
```python
emile = {
    "name": "Emile",
    "age": 34,
    "works_for": "La Fosse"
}

emile_clone = {
    "name": "Emile",
    "age": 34,
    "works_for": "La Fosse"
}

print(id(emile))

# NEW CODE
print(id(emile_clone))
```

**ASK**
Would it or wouldn't it have the same memory address?

- *RUN* `python main.py`

Different addresses


There are cost benefits to referencing the same data multiple times compared to repeating the data like we have right here.

1. Two references for the same data - it's memory efficinent but potentially risky in changing data unintentionally 
2. Two copies of the data - it's not memory efficient but safer

One more thing with variables I want you to think about

```python
speed = 100
print(id(speed))

speed = 200
print(id(speed))
```

**ASK**
Will two prints or logs share the same address?

- *RUN* `python main.py`
- 
They won't, we refer to the data by the same name but the data themselves are different.

This takes us back to a previous concept, called **mutability**

Some datatypes, we can reassign their values, those are called **mutable**

Other's, like our **int, speed** are **immutable**, they're destroyed and recreated, which is why there's a new id. 

If I show you a **list**

What does their **id** suggest about the datatype, whether it's mutable or immutable. 

**main.py**
```python
cities = ["London", "Cardiff", "Edinburgh"]
print(id(cities))

cities.append("Belfast")
print(id(cities))
```

- *RUN* `python main.py`

**ANSWER**
They're **mutable**

Let me update my code a little, underneath the hood, based on this code what do you think Python is doing.

**main.py**
```python
cities = ["London", "Cardiff", "Edinburgh"]
print(id(cities))

# UPDATED CODE
cities = ["Paris", "Lyon", "Marseille"]
print(id(cities))
```
- *RUN* `python main.py`

So now we're getting different **id's** back.

We're deleting the data and reassigning it. 


---

## Data Types (int, float, str, bool, list, dict, tuple)

Let's turn our attention to the different types of data we can store in Python now. 

I've been referring to different types of data this morning:
- strings
- dictionaries
- ints


Fundametally these different data types exist because each serve distinct purposes and are optimised for different operations. 

`SLIDE 5`

### Core types overview
- `int` — whole numbers  
- `float` — decimal numbers 
- `list` — ordered data, mutable  
- `tuple` — ordered data, but immutable
- `dict` — key/value pairs  
- `str` — text  
- `bool` — `True` / `False`  - like a switch, on or off, do this or do that

When we're coding we expect data to be returned to us as a certain type.

If I'm writing software for a self-service checkout at Tesco, I probably want the total price of items output as a float. 

That's because the datatype has been properties and attributes which make it convenient for certain actions. 

I believe it's Tesco where you can round your total to the nearest pound and donate that amount to charity.

We could of course, store a number within a string but we'd lose the ability the manipulate the data as easily. 

I appreciate again, this may be the first time people are seeing these different datatypes so I'll write some out very quickly. 


**main.py**
*INCLUDE COMMENTS*
```python
# INT
customer_id = 204

# FLOAT
latency_ms = 12.5

# STRING
site_name = "London Central"

# BOOLEAN
is_active = True

# LIST
devices = ["Router", "Mobile"]

# TUPLE
site_coordinates = (51.5194, -0.1790)

# DICTIONARY
profile = { "name": "Emile", "age": 34, "customer_id": customer_id}
```

The tuple, again is immutable, we can't change the data inside.

Where we saw the **append** function being used with a list. It wouldn't work with a tuple.

**main.py**
```python
# INT
customer_id = 204

# FLOAT
latency_ms = 12.5

# STRING
site_name = "London Central"

# BOOLEAN
is_active = True

# LIST
devices = ["Router", "Mobile"]

# TUPLE
site_coordinates = (51.5194, -0.1790)
# NEW CODE
site_coordinates.append(1.2345)

# DICTIONARY
profile = { "name": "Emile", "age": 34, "customer_id": customer_id}
```

- *RUN* `python main.py`


Python as a programming language treats everything as an object which we'll look at more closely later on but objects originate from classes so we're seeing that these data types or objects originate from these classes.

It's these parent classes or objects which define the different behaviours or actions we can use on each data type.

Let's take a quick look at some of the built in functions associated with each data type, again, which originate from a parent class.

### STRINGS

We'll start off with strings

One thing which will be consistent with all of these is, we define our string, assign it to a variable and then call a string methods but we could as easily attach these to where the string is defined as well. 

**main.py**
```python
site_name = "London Central"
print(site_name.lower())
print(site_name.upper())

lower_site_name = "london central"
print(lower_site_name.title())
```

- *RUN* `python main.py`

**ASK**
I'm going to define a few more, what do you think these will do?

**main.py**
```python
site_name = "London Central"
print(site_name.lower())
print(site_name.upper())

lower_site_name = "london central"
print(lower_site_name.title())

site_name_whitespace = "    London Central    "
print(site_name_whitespace.strip())

sites = "London,Birmingham,Manchester"
print(sites.split(","))
```

### Numbers

Let's move onto numeric data. Other programming languages treats both whole numbers and decimal numbers as one data type, where Python seperates these out into **ints** and **floats**

The first thing we can do is convert strings into **ints** and **floats**

**main.py**
```python
string_to_int = int("42")
string_to_float = float("42.24")
```

Useful if you've received input from a user, like their age, which arrives as a string. 

But we can also perform functions on these data types as well.

**main.py**
```python
string_to_int = int("42")
string_to_float = float("42.24")

pie = 3.1415926536
# round takes two arguments, the number we want to round, and to how many decimal places
print(round(pie, 2))

negative_number = -10
# abs gives to distance any number is from 0
print(abs(negative_number))

# pow, outputs the first argument, to the power of the second
print(pow(2,3))

# min and max returns the smallest number passed
# maybe you have an offer, giving the cheapest item in a basket for free
print(min(1,2,3,4))
print(max(1,2,3,4))

# sum, adds all the numbers together
print(sum([1,2,3,4]))
```

- *RUN* `python main.py`

With all of these, I'd invite you to think about any broad use casses for the built in functions, where they could benefit any of the tasks you frequently need doing. 

### Booleans

Booleans to remind you are our True and False values, often used in a programs logic. 

We can have pure Boolean True and False

**main.py**
```python
value_a = True
value_b = False
```

But we also have truthy and falsey values which lean in either direction.

There's a built in **bool()** function which can tell us these values

I'm going to write out some values and hopefully, you can tell me if they're truthy or falsey

**main.py**
```python
value_a = True
value_b = False

print(bool(1))
print(bool(0))

print(bool("Hello World"))
print(bool("")

print(bool([]))
print(bool(["London", "Paris"]))
```

- *RUN* `python main.py`

As we said, these boolean or truthy and falsey values are used when making logical decisions along side different opperators.

I've got a series of statements and I'd like for you to spend a handful of minutes deciding whether they'd evaluate as **true** or **false**

A quick reminder, with the **and** operator, everything either side of the **and** condition needs to evaluate in the direction of True. With the **or** operator, only one thing either side needs to evaluate as true or truthy. 

**ASK**

**main.py**
```python
unknown = True or False

print(bool(unknown))
```

- *RUN* `python main.py`

**ASK**

**main.py**
```python
unknown = True and (5  or "")

print(bool(unknown))
```

- *RUN* `python main.py`

**ASK**
**main.py**
```python
unknown = True and (5  or "")

print(bool(unknown))
```

- *RUN* `python main.py`

**ASK**

**main.py**
```python
order = ["5 courgettes", "2 code pieces", "1 butter"]
payment_information = False
delivery = True
collection = False

unknown =  order and payment_information and (delivery or collection)

print(bool(unknown))
```

- *RUN* `python main.py`

### Lists and Tuples

Let's move onto lists and tuples.

They store collections of data by position.

We've seen before we can target the different elements by their index.

**main.py**
```python
devices = ["Router", "Mobile"]
print(devices[0])
print(devices[-1]
```

- *RUN* `python main.py`

We always start from 0 or we can count from the end of the list

But again, there's lots of built in methods available to us as well.

We can add an element with **append**

**main.py**
```python
devices = ["Router", "Mobile"]
devices.append("Laptop")
print(devices)
```

Or a series of devices with **extend**

**main.py**
```python
devices = ["Router", "Mobile"]
devices.extend(["Laptop", "Tablet"])
print(devices)
```

We can insert an element at a specific point

**main.py**
```python
devices = ["Router", "Mobile"]
devices.insert(1, "Laptop")

print(devices)
```

- *RUN* `python main.py`

Also we have the ability to remove elements

**main.py**
```python
devices = ["Router", "Mobile", "Laptop"]
# remove targets a specific element
devices.remove("Mobile")

print(devices)

# pop always removes the last element
devices.pop()
print(devices)
```

- *RUN* `python main.py`

One of the more commonly done tasks is to sort elements in a list.

**main.py**
```python
numbers = [1, 4, 9, 2, 3]

numbers.sort()
print(numbers)
```

- *RUN* `python main.py`

This works intuitively with numbers and we can sort in descending order as well by passing in an arguemnt.

**main.py**
```python
numbers = [1, 4, 9, 2, 3]

numbers.sort(reverse=True)
print(numbers)
```

- *RUN* `python main.py`

This function also works on strings.

**main.py**
```python
names = ["Ziggy", "Mark", "Annabelle", "Lottie"]

names.sort()
print(names)
```

- *RUN* `python main.py`

We can sort larger data types like dictionaries too which we'll look at later. 

The last **list** method we'll look at is **range** which generates lists on our behalf. 

**main.py**
```python
zero_to_ninty_nine = list(range(100))
print(list)
```

- *RUN* `python main.py`

Underneath the hood, `range(100)` converts itself to `range(0, 100)` which is the start and end point. So I've wrapped a **list** function around it to convert everything to a list. 

### Dictionaries

The last datatype we'll look at are dictionaries

This is where our data complexity will grow fairly quickly. 

I'll write down an example which uses lots of different data types as the values for our different keys. 

**main.py**
```python
site = {
    "customer_id": 204,
    "latency_ms": 12.5,
    "site_name": "Lodnon Central",
    "is_active": True,
    "devices": ["Router", "Mobile"],
    "site_coordinates": (51.5194, -0.1790)
}
```

There's three methods I want to show you here, the ability to extract the value of the keys, then the values and finally both. 

**main.py**
```python
site = {
    "customer_id": 204,
    "latency_ms": 12.5,
    "site_name": "Lodnon Central",
    "is_active": True,
    "devices": ["Router", "Mobile"],
    "site_coordinates": (51.5194, -0.1790)
}

print(site.keys())
```

- *RUN* `python main.py`

We can see all the values from the keys are printted off as a list. 

**main.py**
```python
site = {
    "customer_id": 204,
    "latency_ms": 12.5,
    "site_name": "Lodnon Central",
    "is_active": True,
    "devices": ["Router", "Mobile"],
    "site_coordinates": (51.5194, -0.1790)
}

print(site.values())
```

- *RUN* `python main.py`

Same thing but now it's the values being returned 

Finally, let's print both.

**main.py**
```python
site = {
    "customer_id": 204,
    "latency_ms": 12.5,
    "site_name": "Lodnon Central",
    "is_active": True,
    "devices": ["Router", "Mobile"],
    "site_coordinates": (51.5194, -0.1790)
}

print(site.items())
```

- *RUN* `python main.py`

We've got a list of data and each element is a tuple, containing both the key and values. 

Let's move onto actually extracting information from this dictionary

**ASK**
If I wanted to access the **int** value **204** on the **customer_id** key, how'd I do that?

**ANSWER**
**main.py**
```python
site = {
    "customer_id": 204,
    "latency_ms": 12.5,
    "site_name": "Lodnon Central",
    "is_active": True,
    "devices": ["Router", "Mobile"],
    "site_coordinates": (51.5194, -0.1790)
}

print(site["customer_id"])
```

- *RUN* `python main.py`

I want to reintroduce this **square bracket notation**, just because it's going to become more important, as we spend time with larger pieces of data.

Ok...

**ASK**

What will I need to write if I want to access the "Mobile" string from the **devices** key?

**ANSWER**
**main.py**
```python
site = {
    "customer_id": 204,
    "latency_ms": 12.5,
    "site_name": "Lodnon Central",
    "is_active": True,
    "devices": ["Router", "Mobile"],
    "site_coordinates": (51.5194, -0.1790)
}

print(site["devices"][1])
```

- *RUN* `python main.py`

The value on the devices key is a list, we can still use square bracket notation but instead of targetting just the name of the key, we also need to target the position on the list. 

We always start from 0. 

## CHALLENGE 10 MINUTES

I want to give you a challenge which leans into this, I've got a large piece of data.

The most parent level is a tuple and it contains a collection of dictionaries, each dictionary being one of the O2 Academy sites. 

I'll share the link with you now. 

https://gist.github.com/emilesherrott/87216ff34dda8caf9e793fcfd1acb146

You'll see in each dictionary, there's a fair bit of nested data, my challenge to you is to write a print statement which basically outputs your name. 

You can copy and paste this code into GitHub Codespaces and to find your name, you can run: `Control + F` on Windows which will bring up a search bar. 

### TIP

If I were you I'd dig, layer by layer to isolate my name.

So once I've found my name, I'd just look to print that dictionary.

*COPY AND PASTE TUPLE*
```python
[ . . . ]
print(o2_academy_sites_uk[11])
```

- *RUN* `python main.py`

Then I'd think about what the next level would need to be, and go like that. 


---

Now we understand a little more about accessing pieces of data from Dictionaries, I've got one more logical task for you. 

**ASK**

**main.py**
```python
customer = {
    "name": "Emile",
    "active_customer": True,
    "existing_package": False,
    "payment_details": True
}

new_customer_promotion_deal = True

order_items = ["O2 SIM", "5G Plan"]

offer_promotion = customer["active_customer"] and customer["payment_details"] and not customer["existing_package"] and new_customer_promotion_deal and order_items

print(bool(offer_promotion))
```

- *RUN* `python main.py`
  
---

*BREAK*



### Mutability (light touch)
We've mentioned the term **mutability** a little, I want to dig into this just a bit more

When I create a list, by design it's easy to update that same data stored underneath the hood
```python
numbers = [1, 2, 3]
print(id(numbers))

numbers.append(4)
print(id(numbers))
```

Python makes objects mutable, primarily for performance. 

If lists weren't mutable, then underneath the hood, we'd need to create a new list, copy all the elements of the list to the new object and then add the 4th element. 

It's much faster just to modify the existing object.

That's why the datatypes which are commonly changed are mutable:
- lists
- dictionaries

The other data types which are immutable:
- ints
- booleans
- strings
- tuples

You may think then, if mutability is better for performance, then why do we have immutable data.

- safety - it's harder to accidently change
- optimisation - in certain instances python can cache data for quicker access, which is easier to do if the data isn't expected to change

All of this is leading us onto the conversation about efficient programmes.  

Let me write some code down

**main.py**
```python
name = "Emile"

full_name = "Emile Stephen Edward Sherrott"
```

**ASK**
Which variable do we think is going to occupy the least memory?

**ASNWER**
'name'

Different datatypes or different values within the same datatype occupy the different amounts of space.

I'd stress that what you're writing code, especially to begin with, the size of your application isn't what I'd spend time thinking about, but once your comfortable designing simple applications, it's worth thinking about.


`SLIDE 6`

This isn't perfect and there's some caviets. 

But what it's showing us is the size of different pieces of data in Python. 

Collections like **lists** for example, over allocate space up to certain thresholds to make adding and removing from them quicker. 

We can also use built in Python functionality to check the size of our variables. 

I'll import the system module, which gives access to system level information. 

Then there's a method which does what it says on the tin. 

**main.py**
```python
import sys

my_int = 42
print(sys.getsizeof(my_int))

my_float = 28.1
print(sys.getsizeof(my_float))

my_string = "Hello World"
print(sys.getsizeof(my_string))

my_bool = True
print(sys.getsizeof(my_bool))
```

*RUN* `python main.py`

This is basically checking the size of data contained in the variables. 

And whilst this is a good indication of how well a programme can run, the real savings come from the different algorithms our script can use. 

Let's say we want to add every number between 1 and a million - that could take some time. It's also the type of operation computers excel at. 

I'm going to write down some code and both will achieve the same thing but use different processes. 

What I care about, isn't what the sum of every number between 1 and 1 million is but how quickly Python can generate an answer. 

I'm going to add some code which will essentially take a snapshot of the time, perform the calculation and then take another snapshot of the time and we can calculate the difference between the two. 
**main.py**
```python
import time

# Method 1 - FOR LOOP
start = time.time()
loop_total = 0
for i in range(1000000):
    loop_total += i
print("Loop:", loop_total,  time.time() - start)

# Method 2 - BUILT IN METHODS
start = time.time()
built_in_total = sum(range(1000000))
print("Built-in:", built_in_total, time.time() - start)
```

- *RUN* `python main.py`

One is quicker than the other, when we use built in methods, generally they're optimised to perform as quickly as possible and this takes us closer to how the programming language works. 

Our **for loop** is pure Python and with every loop it needs to:
- Understand the value held in **loop_total**
- Interpret or convert it into machine code
- Perform the operation
- It does than 1 million times

Then with our built in methods, it uses what's called CPython which is internally much closer to machine code, it skips that step of **interpretation** so the action is much faster. 

---

The reason we're spending the day revisiting a lot of these concepts is firstly to ensure everyone is comfortable with the foundations of Python but again, just to make sure we're comfortable not just with the theory but also practically writing didn't programs in Python. 



## Control Flow (if / elif / else) — (for / while)

Let's start putting all this together with **control flow**

I want to create a programme that takes an internet speed and determines what type of internet package they may be eligable for.

To do this we're going to use **control flow** or **if/else** statements. This is another feature which is fairly consistent amongst programming languages and is the difference between linear code and code which can adapt to different situations and work dynamically.


---

### `if / elif / else`

**main.py**
```python
# Our fictional user has an internet speed for 350
speed = 350

# We now need to write our 'if' statement and condition which is followed by a colon ':'
# If the speed is greater or equal to 500 they're eligable for Fibre Max
if speed >= 500:
    print("Eligible for Fibre Max")
# Otherwise if it's greater or equal to 200 they're eligable for Fibre Plus
elif speed >= 200:
    print("Eligible for Fibre Plus")
# Otherwise
# No condition on an 'else' as it behaves like a catch all
else:
    print("Eligible for Standard Fibre")
```

*RUN CODE*

Generally it's considered good practice to place the **most specific** condition at the top which makes things readable. 

It's also good to note that if the first 'if' statement doesn't return True or be executed, then the next 'elif' statement is evaluated, so on and so forth so there's a tendency to put the condition which is expected to evaluate True higher up as the programme will execute more quickly. 

`SLIDE 7`

Take this example.

This type of code would generally run slower than if the first condition was checking if someone was right handed. Simply because if this program ran for every person in the world we'll have to evaluate more lines of code. 

I researched that between 85-90% of people in the world are right handed, meaning that for everyone person who is, we'll have to evaluate the first two conditions to see whether they're **ambidextrious** and **left handed** before we see a condition which returns true. 

### Control Flow Challenges

I've got some data which I want you to define some control flow for. 

https://gist.github.com/emilesherrott/87216ff34dda8caf9e793fcfd1acb146

There's two challenges under the header **Control Flow Challeges**, both have solutions in the file as well, which I'd encourage you not to look at. The second challenge is harder and requires careful consideration regarding the order of the **elif** statements. 

I'll give you 15 minutes to attempt both before we come back and look at the second. 

**Challenge 2 SOLUTION**

**main.py**
```python
site_name = "Manchester Central"
latency_ms = 72.4
connected_users = 230
packet_loss = 1.8
is_active = True

if is_active == False:
    print("Site offline")
elif latency_ms < 50 and packet_loss < 1 and connected_users < 150:
    print("Site operating normally")
elif latency_ms >= 50 and latency_ms <= 100:
    print("Site experiencing latency issues")
elif packet_loss > 1.5:
    print("Network packet loss detected")
elif connected_users > 200:
    print("Site overloaded")
else:
    print("Site operating with minor issues")
```

This has different statements for all but one of our conditions, the one where there's *major problems**

The problem is, if I put this final one at the bottom, a previous statement maybe triggered. This is where the order becomes quite important. We know that following the first condition the **is_active** status must be true, then following the second condition we know if the site is operating nomrally. 

Underneath that though, we check to see if there's any individual issues. 

I need to have a condition above these, as otherwise the we'll never be abl to evaluate if the issues are major. 

**main.py**
```python
site_name = "Manchester Central"
latency_ms = 72.4
connected_users = 230
packet_loss = 1.8
is_active = True

if is_active == False:
    print("Site offline")
elif latency_ms < 50 and packet_loss < 1 and connected_users < 150:
    print("Site operating normally")
elif latency_ms >= 50 and packet_loss > 1.5 and connected_users > 200:
    print("Site operating with major issues")
elif latency_ms >= 50 and latency_ms <= 100:
    print("Site experiencing latency issues")
elif packet_loss > 1.5:
    print("Network packet loss detected")
elif connected_users > 200:
    print("Site overloaded")
else:
    print("Site operating with minor issues")
```

---

If **'if/else'** statements are a way to execute different pieces of code under different conditions, **'loops'** are a way to execute code on many pieces of data efficiently. 

### `for` loops

We can loop over most data types but generally it's easiest if our data exists in a collection like a list or tuple and what we want to do is perform an action against all items in the collection.  


**main.py**
```python
# Define our collection
devices = ["Router", "Mobile", "Landline"]

# Use the 'for' keyword
# Then it's custom to take a singular item from the plural collection name
for device in devices:
    print(f"Checking device: {device}")
```


One of the most important things to remember is our collections are 'indexed' from 0. 

So in our 'devices' list, the "Router" is indexed from position 0

```python
devices = ["Router", "Mobile", "Landline"]

# We can refer to the index, we don't have to use 'i' but it's convention
# 'enumarate' is a built in fuction that lets us loop over the index and value at the same time
for i, device in enumerate(devices):
    print(i, device)
```

Practically you'd use code like this if you're trying to see the specific position of an item or some conditional logic, maybe if you're begugging as well. 

---

### `while` loops

Another loop worth revisiting is the 'while' loop. 

Generally we'd use this when we don't know how many times we'll need to loop through something. 

Maybe trying to log into an account. 

We can't let a user progress until they've entered the right password. 

**main.py**
```python
attempts = 0
max_attempts = 3
password = "LaFosse"

# This loop will run as long as they've had 3 or less attempts
while attempts < max_attempts:
    # We'll need to gather input from the user
    user_input = input("Enter password: ")

    # If the input matches the password we'll need to let them know and then break out of the loop
    if user_input == password:
        print("Access granted")
        break
    # Otherwise we'll let them know they got it wrong and then increment the value of the attempts
    else:
        print("Incorrect password")
        attempts += 1

# Then if the condition for the while loop now returns false, we can check whether they maxed their attempts
if attempts == max_attempts:
    print("Maximum attempts reached")
    
print("End of script")
```

#### Safety note
Always ensure a `while` loop has a clear exit condition otherwise, we get what's known as an infinite loop, which will eventually crash your computer.

If we removed `attempts += 1` then, the while loop will always evaluate as true and the user will never be able to break out of this part of the software. 
“What happens if `attempts += 1` is missing?”

---

I've got another challenge for you. 


## Micro Exercise (5–10 mins)

`SLIDE 8`

There's some mock data, again for you to copy over and I want you to loop through them all. 

If any of the items need an internet connection, I want you to print: *Broadband subscription required* and then break out of the loop.

I want you to break out of the loop because if one item requires the internet, then we don't really need to evaluate whether any others do because it wont change the requirement. 

**SOLUTION**
```python
checkout_items = [
    {"name": "Laptop", "price": 900.99, "internet_connection_needed": True},
    {"name": "Printer", "price": 52.99, "internet_connection_needed": False},
    {"name": "Smart TV", "price": 349.00, "internet_connection_needed": True},
    {"name": "USB Drive", "price": 15.99, "internet_connection_needed": False},
]

for item in checkout_items:
    if item["internet_connection_needed"]:
        print("Broadband subscription required")
        break
```

---

*BREAK*


---

## Functions & Code Reuse (Trainer Notes)

For the next part of the day we're going to progress from writing code which works for writing code which is **reusable, readable and predictable**

---

### Learning Outcomes
By the end of this section, I hope you'll be able to:
- Articulate why functions are essential for maintainable code.
- Write functions with clear parameters and return values.
- Use default parameters safely and intentionally.
- Write meaningful docstrings that describe behaviour, not implementation.

---

## Why Functions Matter

### Core idea
Functions exist to:
- Reduce duplication
- Isolate logic
- Communicate intent
- Make code testable

We'll be looking at testing at the end of the course but for I want to reintroduce a term called DRY code.

DRY being an acronym for **'DO NOT REPEAT YOURSELF'**

### Before functions — duplicated logic
Imagine we want to impliment some functionality which increases the broadband speed of a user. 

**main.py**
```python
customer_speed = 300

# We want to increase their speed by 100 megabits per second
new_customer_speed = customer_speed + 100

# Then later down the line we want to increase it by another 80
new_new_customer_speed = new_customer_speed + 80

print(new_new_customer_speed)
```

*RUN CODE*

This is bad for many reasons:
1. We're defining 3 variables when we could use one, so it's not memory efficient
2. We're doing the same task several times - adding the new speed to the old speed 
    - We're repeated ourselves


This is a good usecase to define a function

When we create a function, there becomes a single source of truth. 

We start with the **def** keyword which singles the intention to create a function, followed by the name

Then we need to use parenthesies to tell Python this is a callable function, passing in any parameters 

**main.py**
```python
customer_speed = 300

def upgrade_speed(current_speed, speed_increase):
    current_speed += speed_increase
    return f"Customer speed is now {current_speed}"


print(upgrade_speed(customer_speed, 100))
```

The return keyword then passes the value back to where the function was called. 

- *RUN* `python main.py`

---

## Parameters and Return Values

So there's lots of terminology here
### Parameters vs arguments
- **Parameters**: names in the function definition, in this case: **current_speed** and **speed_increase**
- **Arguments**: values passed when calling the function, our variable which references the value 300 and the int 100 which is our **speed_increase**

There's lots of useful functionality we may want to call repeatedly. 

**main.py**
```python
def calculate_latency(distance_km):
    return distance_km * 2

calculate_latency(10)
```

- *RUN* `python main.py`

### Return values
- `return` sends data back to the caller
- A function without `return` returns `None`

**main.py**
```python
def log_message(message):
    print(message)

result = log_message("System online")
print(result)  # None
```

- *RUN* `python main.py`

Any code detailed after the return keyword, won't execute. 

```python
def log_message(message):
    return message
    print("Hello World")

result = log_message("System online")
print(result)
```

- *RUN* `python main.py`


---

## Default Parameters

Let's expand our function to include **default values**

### Why defaults exist
Defaults allow functions to:
- Be flexible
- Support common cases without extra arguments
- Remain backward compatible

By **'backward compatible'** we mean new changes won't break old code 

The only difference with a default parameter is we use the '=' syntax and the default value if no argument is passed in

**main.py**
```python
def greet(name="Guest"):
    print(f"Hello, {name}!")

greet()
greet("Emile")
```


We can use functions with the other concepts we've looked at so far.

I'll start with a 'dictionary' about a customer

```python
user = {
    "name": "Emile",
    "broadband_speed": 100,
    "is_vip": False,
    "devices": ["Router", "Mobile", "Smart TV"],
    "member_since": "2018/01/12"
}
```

What I want to do is check how long they've been a customer for and if it's since before 2020 and they're not already a vip, they'll be eligable for a VIP package

If we take it step by step the first thing I want to do is find out if they've been a customer since before 2020.

**main.py**
```python
user = {
    "name": "Emile",
    "broadband_speed": 100,
    "is_vip": False,
    "devices": ["Router", "Mobile", "Smart TV"],
    "member_since": "2018/01/12"
}

def offer_vip(customer):
    member_start_date_as_list = customer["member_since"].split("/")
    return member_start_date_as_list

print(offer_vip(user))
```

We've seen the **split** method before, it takes a string and then creates a list based on a seperator found inside the string, in this case, a forward slash. 

- *RUN* `python main.py`

So we can see the we've return a list which now gives us access to built in list functionality. 

There's many ways to write programmes and why I personally find it enjoyable seeing the different approaches.

What I'll do now is target the first element of this list, to see the year.

**main.py**
```python
user = {
    "name": "Emile",
    "broadband_speed": 100,
    "is_vip": False,
    "devices": ["Router", "Mobile", "Smart TV"],
    "member_since": "2018/01/12"
}

def offer_vip(customer):
    member_start_date_as_list = customer["member_since"].split("/")
    member_start_year = member_start_date_as_list[0]
    vip_eligable = member_start_year < 2020 and customer["is_vip"] == False
    return vip_eligable
    
print(offer_vip(user))
```

- *RUN* `python main.py`

**ASK**
We've got an error, can anyone tell me what the error is and even better, how we could fix it?

**ANSWER**
We can see at the bottom: `TypeError: '<' not supported between instances of 'str' and 'int'`

Which basically is telling us we're trying to compare whether a string is less than an int which doesn't make sense as an operation. 

Specifically, the variable **member_start_year** is currently a string. 

So we need to convert this to an **int**

We've seen a built in method to do this. 

**main.py**
```python
user = {
    "name": "Emile",
    "broadband_speed": 100,
    "is_vip": False,
    "devices": ["Router", "Mobile", "Smart TV"],
    "member_since": "2018/01/12"
}

def offer_vip(customer):
    member_start_date_as_list = customer["member_since"].split("/")
    # UPDATED CODE
    member_start_year = member_start_date_as_list[0]
    # NEW CODE
    member_start_year_int = int(member_start_year)
    # UPDATED CODE
    vip_eligable = member_start_year_int < 2020 and customer["is_vip"] == False
    return vip_eligable
    
print(offer_vip(user))
```

- *RUN* `python main.py`

This is fine it works, earlier in the day we spoke about applications being memory efficient and we can see there's three lines of code where we define three different variables.

- The first one holds a list
- The second holds a string
- The third holds an int

We can write all of this on one line by nesting and chaining functionality 

I'll start by chaning on accessing the first element in our list and updated our variable name

**main.py**
```python
user = {
    "name": "Emile",
    "broadband_speed": 100,
    "is_vip": False,
    "devices": ["Router", "Mobile", "Smart TV"],
    "member_since": "2018/01/12"
}

def offer_vip(customer):
    # UPDATED CODE
    member_start_year = customer["member_since"].split("/")[0]
    member_start_year = member_start_date_as_list[0]
    member_start_year_int = int(member_start_year)
    vip_eligable = member_start_year_int < 2020 and customer["is_vip"] == False
    return vip_eligable
    
print(offer_vip(user))
```

That will hold our string 2018 and I can convert all of this into an **int**

I'll also remove our redundant code and rename our variable from our condition at the bottom

**main.py**
```python
user = {
    "name": "Emile",
    "broadband_speed": 100,
    "is_vip": False,
    "devices": ["Router", "Mobile", "Smart TV"],
    "member_since": "2018/01/12"
}

def offer_vip(customer):
    # UPDATED CODE
    member_start_year = int(customer["member_since"].split("/")[0])
    vip_eligable = member_start_year < 2020 and customer["is_vip"] == False
    return vip_eligable
    
print(offer_vip(user))
```

- *RUN* `python main.py`


So now everything is done on one line and we don't waste memory by defining three variables. 

**ASK**
Do you have a preference?
**MY THOUGHTS**
If you prefer this version great but in any stage of working professional code, I'd suggest to you that readable code is the better code. 

You'll be able to read more complex code the longer you engage with programmes in general, and it'll naturally get tigther. For now I'd prioritse readability.


---

## Docstrings

An aspect of readability we looked at earlier was Docstrings

Documentation about parts of a programme in Python which helps to describe:
- what the function does
- what input it expects
- what it returns

They're important because good code is readable and if we go away on a sabbatical we should be able to return and still be able to understand the code quickly even if it's been changed or refactored.  


### One-line docstring

We'll start with a one-line docstring

**main.py**
```python
def is_active(speed):
    """Return True if the customer has an active service."""
    return speed > 0

help(is_active)
```

- *RUN* `python main.py`

### Multi-line docstring (Google style)

Then a multi-line docstring for more substaintial information

**main.py**
```python
def upgrade_speed(speed, bonus=100):
    """
    Increase broadband speed by a bonus amount.

    Args:
        speed (int): Current broadband speed.
        bonus (int): Additional speed to apply.

    Returns:
        int: Updated broadband speed.
    """
    return speed + bonus

help(upgrade_speed)
```

- *RUN* `python main.py`

They may seem fairly simple but they help:
- New team members
- Debugging unfamiliar code
- Large projects with separated files

**Trainer reminder:**  
Docstrings explain *why* and *what*, not *how*.

The how should be readable for the software developer. 

---

## Micro Exercise (10-15 mins)

I'm going to get you working again on another little challenge, there's a code snippet inside the GitHub Gist. 


```python
emile = {
    "name": "Emile",
    "broadband_speed": 100,
    "is_vip": False,
    "devices": ["Router", "Mobile", "Smart TV"],
    "member_since": "2018/01/12",
    "address_information_present": False,
    "mobile_number": +447123456789
}
```

`SLIDE 9`

What I want you to do is write a function which takes a dictionary like the one I've given as an argument and asseses whether the customer should be contacted for a possible upgrade.

Firstly we need to check whether they have a slow enough internet connection and if they do our preference is to contact them via a letter to their address

Otherwise we'll send a text to their mobile phone

If we have their address information I want the function to print that it'll send a letter to the address

If we don't I want the function to print that it'll send an SMS to their mobile

If their internet speed is good print a message saying as such.

Part of this is also defining a solid docstring. 

**SOLUTION**

**main.py**
```python
emile = {
    "name": "Emile",
    "broadband_speed": 100,
    "is_vip": False,
    "devices": ["Router", "Mobile", "Smart TV"],
    "member_since": "2018/01/12",
    "address_information_present": False,
    "mobile_number": +447123456789
}

def contact_customer_for_upgrade(user):
    """
    Checks a customer's broadband speed and contacts them if an upgrade is recommended.

    If the customer's broadband speed is below 200 Mbps, the function determines
    the appropriate contact method:
    - Sends a letter if address information is available
    - Sends an SMS if no address is present

    If the broadband speed is 200 Mbps or higher, no action is taken.

    Args:
        user (dict): A dictionary containing customer information, including:
            - name (str)
            - broadband_speed (int)
            - address_information_present (bool)
            - mobile_number (int or str)

    Returns: 
        str: Whether contact is required and method
    """
    if user["broadband_speed"] < 200:
        if user["address_information_present"]:
            print(f"Sending upgrade letter to {user['name']}'s address.")
        else:
            print(f"Sending SMS to {user['mobile_number']} about broadband upgrade.")
    else:
        print("No contact needed.")
        
        
# help(contact_customer_for_upgrade)

contact_customer_for_upgrade(emile)
```

*BREAK*

---











## Dynamic Typing in Python


We'll continue to expand on what we've been doing and introduce dynamic typing. 

Dynamic typing basically means we don't have to define the datatype of our variables. 

We can do things like this. 

**main.py**
```python
x = 10
x = "hello"
x = [1, 2]
```

'x' doesn't have a fixed type and this can be really helpful

It's faster to write code and change code throughout a script, it's more readable as well which is important when dealing with lots of data, which is where Python is mainly used. 

Conversely the opposite is **static typing** where we have to define what datatype a variable is and then it doesn't change. 

Languages like Java do this and it has a few benefits, primarily around safety, data types can't change unexpectidly and because of this the programme knows from the offset how much memory needs to be allocated, which can increase performance. 

This can be problematic for us using Python because if there's the potential for errors in our code due to data types, we won't know it until the code runs. 

Take our earlier object:

**main.py**
```python
emile = {
    "name": "Emile",
    "broadband_speed": 100,
    "is_vip": False,
    "devices": ["Router", "Mobile", "Smart TV"],
    "member_since": "2018/01/12",
    "address_information_present": False,
    "mobile_number": +447123456789
}
```

We took the value on `member_since` and converted it from a **string** to a **list** and then to an **int**. If the `member_since` accidently contained an **int** to begin with our code would fail and we'd not know about it until later in the development or the deployment.

There's a real trade off between reliability and ease of programming.

---

## Variables Can Change Type

Variables often change 

**main.py**
```python
data = 500
print(data + 100)
```

- *RUN* `python main.py`

If for some reason `data` is converted to a string

**main.py**
```python
data = "500"
print(data + 100)
```

- *RUN* `python main.py`

We get an error
- The error is not at assignment when we define the variable
- It happens only when Python tries an invalid operation


This often happens whilst writing code when:
- Reading input from users
- Loading data from files or APIs
- Parsing JSON

All of which we'll look at this week 

**main.py**
```python
speed = input("Enter speed: ")
print(type(speed))
print(speed + 100)
```

*PASS 200 AS THE VALUE*
- *RUN* `python main.py`

We can see the input arrives as a string even if we type a number

Dynamic typing pushes responsibility onto the developer.

---

## Duck Typing

This brings us onto something called **duck typing**

Duck typing is a design philosophy:

“If it looks like a duck and quacks like a duck, it’s a duck.”

Remember under the hood, in Python everything is an object. 
- Objects are used based on **behaviour**, not their explicit datatype
- If an object supports the required methods, it works


What I'll do is try and find the length of different data types

**main.py**
```python
def print_length(item):
    print(len(item))

print_length("Network")
print_length([1, 2, 3])
print_length({"a": 1, "b": 2})
```

- *RUN* `python main.py`

This works for:
- Strings
- Lists
- Tuples
- Dictionaries

**main.py**
```python
def print_length(item):
    print(len(item))

print_length(100)  # TypeError
```

- *RUN* `python main.py`

### Why this is powerful
Duck typing allows:
- Flexible APIs - which means we can consume data from many different origins
- Our functions become more reusable, we don't need the same function for:
    - strings
    - lists
    - dictionaries


We can ask “Can this object do what I need?” and take it from there

---

## Duck Typing vs Type Checking

### Naive type checking (discouraged)

We could if we want write code like this:

**main.py**
```python
equipment = ["Router", "Mobile", "Printer"]

def process_devices(devices):
    # We check straight away if we're iterating over a list
    if not isinstance(devices, list):
        return
    else:
        for device in devices:
            print(device)
            
process_devices(equipment)
```

- *RUN* `python main.py`

### Behaviour-based approach (preferred)

The preferred approach however is to omit that code

```python
equipment = ["Router", "Mobile", "Printer"]

def process_devices(devices):
    for device in devices:
        print(device)

process_devices(equipment)
```

- *RUN* `python main.py`

Explain:
- Python will fail naturally if the object doesn’t support iteration
- A core philosophy of Python is that it cares what data can do rather than what it is
- Again: "If it walks like a duck and quacks like a duck, for python, it is a duck"
- This keeps code simpler and more idiomatic, i.e. how Python intended itself to be written


Let Python raise clear errors instead of pre-emptively blocking valid objects.

---

## Limitations of Duck Typing

### Important caveat
Duck typing works best when:
- Behaviour is predictable
- Codebases are small to medium

As systems grow and data passes through lots of files and functions:
- These implicit assumptions can become dangerous
- Bugs become harder to trace

This is the **bridge** to static typing and type hints.

Duck typing gives us flexibility — type hints give us safety nets.

---

We can also implement different blocks to protect us if data does get converted into something unexpected. 

**main.py**
```python
information = "VMO2 provides connectivity and digital services"

def display_information(info):
    """
    Displays the provided information in uppercase.

    This function takes a string input, converts it to uppercase,
    and prints the result to the console.

    Args:
        info (str): The information text to be displayed.
    """
    print(info.upper())
    
display_information(information)
```

- *RUN* `python main.py`

The built in function `.upper()` converts a string characters from lowercase to uppercase.

This won't work if the `information` variable contained an int

```python
information = 100

def display_information(info):
    print(info.upper())
    
display_information(information)
```

- *RUN* `python main.py`

It's not a duck

But I can **try** to perform an operation and if it fails just print the value as standard.

This is called **try/except**

We **try** something and if it fails we **except** its failed and do something else

**main.py**
```python
information = 100

def display_information(info):
    try:
        print(info.upper())
    except:
        print(info)
    
display_information(information)
```

- *RUN* `python main.py`

*REPLACE 100 WITH "Hello World" AND RUN CODE AGAIN*

We'll look at **try/except** later in the week but they do look fairly similar to **if/else control flow**

The main different is:
- **if/else** is for decisions we expect
- **try/except** are for failures we don't expect, but want to protect ourselves against 


## Micro Exercise (5–10 mins)

`SLIDE 10`

### Task
I want you to write a function called `double_value()` which takes an **int** and returns the value doubled, however if it receives a data type, which can't be doubled, the programme should fail but should print `can't double value`

I want you to use `try/except`

**SOLUTION**

**main.py**
```python
def double_value(data):
    try:
        print(data * 2)
    except:
        print("Can't double value")
    
double_value(2)
```

- *RUN* `python main.py`

*RUN CODE AGAIN REPLACING 2 WITH "Hello"

There is an issue which some of you may have spotted

**main.py**
```python
def double_value(data):
    try:
        print(data * 2)
    except:
        print("Can't double value")
    
double_value([1,2])
```

*RUN CODE*

It doesn't trigger out `except` block.

Python basically treats this not as a mathematical process but as we can see, it's interpreted as repetition. 

The solution is that we lean slightly towards statically typed code and make sure this process is performed on an **int**

```python
def double_value(data):
    try:
        # UPDATED CODE
        result = int(data * 2)
        print(result)
    except:
        print("Can't double value")
    
double_value([1, 2])
```

- *RUN* `python main.py`

---

*BREAK*


## Static Typing in Python (Trainer Notes)

Let's talk more about static typing 

As we know, by nature Python isn't statically typed but we can provides hints about expected data as a communiction tool

These **Type hints**:
- Don't change runtime behaviour or enforce datatypes
- It's designed to improve readability and maintainability

**main.py**
```python
def upgrade_speed(speed: int) -> int:
    return speed + 100

print(upgrade_speed(20))
```

- *RUN* `python main.py`

What this code is saying is that the **argument** passed in for **speed** should be an **int** and the expected return value should be an **int**

If the wrong type is passed:
- Python still runs
- Errors still occur at runtime
- Type hints *warn*, they don’t *protect*


---

## Basic Type Hints

Let's look at some more hints and why they matter

They:
- Communicate intent
- Catch mistakes early in editors
- Make large codebases easier to navigate


**main.py**
```python
speed: int = 300
site_name: str = "London Central"
is_active: bool = True
```

Again this code is completely valid

**main.py**
```python
speed: int = 300
site_name: str = "London Central"
is_active: bool = True

speed = "hello"
```

We define intent, not rules and this is where the culture of organisations matter. 

We can override all of these things but if you care about collaberation, then we shouldn't. 

The purpose of these hints is the make life easier not harder, you shouldn't be defining **docstrings** and **type hints** on everything

We should annotate:
- Public functions
- Shared modules
- Complex logic

---


### Return types

The **return types** we've seen are useful to:
- A lot of the time the returned value from one function will be consumed elsewhere, either by another function or sent back to a user.
- If we know that a function returns a string then it's much easier to handle and use that function elsewhere in the program. 

**main.py**
```python
def get_plan(speed: int) -> str:
    if speed >= 500:
        return "Fibre Max"
    else:
        return "Standard Fibre"
    
plan = get_plan(300)

print(plan)
```

Because we know the data stored in **plan** will be a string, it's easier for me to use that data in a **f string**

**main.py**
```python
def get_plan(speed: int) -> str:
    if speed >= 500:
        return "Fibre Max"
    else:
        return "Standard Fibre"
    
plan = get_plan(300)

print(f"Your current speed permits you to have the {plan} plan")
```




### Missing returns

A few more topics to discuss today, we're going to stick with functions and take a look at what happens if there's no value returned. 

This also helps us think through code a little more thoroughly

**main.py**
```python
def get_discount(is_vip: bool) -> int:
    if is_vip:
        return 10

print(get_discount(True))
```

**ASK**
This doesn't make too much sense practically but what do you think happens if `is_vip` is `False`?

Answer:
- Function returns `None`

- *RUN* `python main.py`

Again these type hints don't enforce rules but suggestions so we should add an additional condition

**main.py**
```python
def get_discount(is_vip: bool) -> int:
    if is_vip:
        return 10
    else:
        return 0

print(get_discount(False))
```

- *RUN* `python main.py`

---


## Optional

There's additional layers of complexity we can add with a couple of keywords and this will round us off for the day. 

The first one is called **Optional**

We have to import this from the built in module 'typing'

I'm going to define a simple function can return one of two things
**main.py**
```python
from typing import Optional

def greet_customer(name: str) -> str:
    if name == "Alex":
        return "Hello Alex"
    else: 
        return None

print(greet_customer("Alex")
```

Not the most exciting thing, our Type Hints suggest that the data type returned will be a string. We can see that this isn't entirely accurate though. 

Let's use our import

**main.py**
```python
from typing import Optional

def greet_customer(name: str) -> Optional[str]:
    if name == "Alex":
        return "Hello Alex"
    else: 
        return None
    
print(greet_customer("Alex"))
```

So what does **Optional** actually mean?

`Optional`, followed by square brackets and a datatype means the return value may be of type `str` **or** `None`

It does **not** mean “optional argument”.


Without `Optional`, `None` becomes an invisible edge case.

It can happen but our code doesn't suggest it realistically will

With `Optional[T]` we know to anticipate a `str` or `None`, essentially an empty data type

If I updated my code so the **if** statement, doesn't trigger like this.

**main.py**
```python
from typing import Optional

def greet_customer(name: str) -> Optional[str]:
    if name == "Alex":
        return "Hello Alex"
    else: 
        return None

#  NEW CODE
result = greet_customer("Bob")
result.upper()  
```

Now we're being much more explicit in what that function may return

Because of our hints we can expect **result** will hold a **string** or **None**

Because we can use the `.upper()` function on a string and not on None, type hints force you to handle uncertainty explicitly in the development process.

- *RUN* `python main.py`

---

## Union

Our final keyword of the day is going to be **Union**

`Union` allows **multiple valid types**.

Take converting calcius to fahrenheit, we don't know if the function is going to be called with an **int**, **float** or even a **string**. 

Again, the purpose of this is to make it easy as possible for other developers to know what to expect when handling and utilising our functions. 

**main.py**
```python
from typing import Union

def calsius_to_fahrenheit(value: Union[float, int, str]) -> float:
    calcius = float(value)
    return (calcius * 1.8) + 32

print(calsius_to_fahrenheit(100))
print(calsius_to_fahrenheit(100.0))
print(calsius_to_fahrenheit("100"))
```

- *RUN* `python main.py`


We ought to use `Union` when:
- Input comes from external sources and we have less control over the initial data
- Multiple formats are expected
- You want to be explicit about flexibility

---

### Comparison

We can combine all of these together as well

`SLIDE 11`

There's a little comparison on the board about how Optional and Union can be used. 

It's uncommon but possible

- **Optional** only takes one datatype and it'll expect to be that datatype or None.
- **Union** expects to take 2 or more


---


## Micro Exercise (5–10 mins)

I've got one more exercise for you. 

`SLIDE 12`

### Task
1. Write a function `calculate_total` that, it should have two parameters:
   - `base_cost`:  as a `float`
   - `discount`: which is an `Optional[int]`
   - Returns a `float`
2. If discount is `None`, apply no discount.
3. Add appropriate type hints and a docstring.

**SOLUTION**
```python
from typing import Optional

def calculate_total(base_cost: float, discount: Optional[int] = None) -> float:
    """
    Calculates the final total cost after applying an optional discount.

    If no discount is provided (i.e. discount is None), the base cost is
    returned unchanged. Otherwise, the discount value is subtracted from
    the base cost.

    Args:
        base_cost (float): The original cost before any discount.
        discount (Optional[int]): The discount amount to apply, or None.

    Returns:
        float: The final calculated cost.
    """
    if discount is None:
        return base_cost
    else: 
        return base_cost - discount
    
print(calculate_total(50.34))
```

---

## Remainder of the day

I now really want to get you practicing Python yourselves. 

I've got a set of challenges for you to work through:

https://gist.github.com/emilesherrott/7eb0942982fa8bb65b04e4c39a141d61

As always, there's a solution document I'll share but please work through these at your own pace and collaborate if we wish. 

https://gist.github.com/emilesherrott/c19a06d133ed311e793b7ac61f80a795

These challenges do build on the different techniques we've covered today but I'd recommend having a tab open, ready to use CoPilot or Google to research different things. 

I'd encourage you not to copy the challenge directly into CoPilot or ChatGPT. It may give you the answer but for where we are, you won't learn too much. 

I'll be here to help you if you get stuck. 
