
# Advanced Python — Day 2

## Recap to OOP (Trainer Notes)

**Target delivery time:** ~ 1 Day
**Purpose:** Build a shared mental model of *why* OOP exists before introducing Python-specific syntax and patterns.  
**Trainer notes:** This is conceptual first, technical second. Focus on *why OOP helps humans manage complexity*.

---

### Learning Outcomes
By the end of this section, learners will be able to:
- Explain what Object-Oriented Programming (OOP) is in practical terms.
- Describe why OOP exists and what problems it aims to solve.
- Compare objects and functions, and explain when each approach is appropriate.



---

# Pre-Training

Load Slidee - **Day 2**


# Training Session

`SLIDE 1` 

Ok, good morning everyone and welcome back. 

# POTENTIAL SPACE TO VISIT CHALLENGES FROM YESTERDAY IF TIME ISSUE

Learning a programming language is similar to learning an actual language... I believe. If I watch losts of korean films and television, that can be helpful but until I actually start trying to speak it, the language won't really cement itself. 

So I want to revisit just a couple of the challenges from yesterday. 

Solving this programmes is actually a two step process.

1. The first is thinking about the logic I can write which will solve the problem.
2. Then actually converting that logic to the syntax of the programming language I'm using. 

Let me show you an example. 

## Training

Today we're going to push on from base camp and take a much closer look at Object Orientated Programming. This hopefully will enable us to build applications as scale and handle more complex data.

It's my hope that you'll leave today being able to articulate what OOP is and how it helps us build those larger applications and then be able to assess the different some of the different types of functionality classes can give us. 

Just incase it got lost, **OOP** is an acronym for **Object Orientated Programming**.

Across programming broadly, you'll see OOP implimented in:
- Java
- C++
- C Sharp

Then regarding the industries, it's commonly utilised in:
- banking systems
- insurance software
- you'll notice it used in CRM platforms

Essentially Enterprise Software, for large corporations.

This is because it helps developers organise complex software, reuse code and maintain large systems more easily, and I hope you'll see that throughout today. 


### Plain-English Definition

The explain that a little further, Object-Oriented Programming is a way of structuring code around **things**, specifically **objects** rather than just **actions** or functions.

So far when we've been writing code, generally speaking it flows from top to bottom through a script. 

We could have functions which call other functions which alters that flow slightly but our code, we'd describe as being functional in it's process. 

OOP on the other hand encourages the idea is that everything can be replicated in code via an object. Then in the development of software, we mimic real-world concepts via the objects our software depends on. 

`SLIDE 2`

So let's think about those objects

An object usually represents a real world entitiy, which we create programmatically. 

On the screen there's two objects which we could start to think about translating to code. 

The first thing to note is, we represent these objects through combining **data** and **behaviour**, or respectively **attributes** and **methods**

So we have a person and a bus as two things we could create as objects. 

If we think back to the code we've written so far on the course, we could create a dictionary for a customer which has different keys of information. 

Additionally, we've created functions which could perform actions on behalf of a customer, maybe checking what package their entitled to based on their internet speed or asking them to say hello. 

It was always seperate through, a dictionary which related to one customer, or a function which operated on behalf of a customer. 

When we create objects, again, it's about combing these pieces of data and behaviour into objects.

  
- In the example the person's data are things like their **height, age, nationality** but they have behaviours as well, like **talking**
  
- Notice the parenthesies are brackets next to **talking()** it looks like a function and it is, things the object can do, but on objects we call them **methods** instead of functions but practically, they're the same.

We also have a bus, the **data** or **attributes** are the information the object stores about the:
- maximum capacity
- the gearing
- the colour

Then the behaviour is the ability to drive and stop. 

We'll see it in a little bit, but we define the classes which enable us to create objects at scale and it's us, working in Python who decide what data and behaviours we care about. 

 OOP is about bundling data and behaviour that belong together, and giving that bundle a name.
 

Objects also don't have to be real world things like people or buses. They can be conceptual as well.

One of the things we saw earlier in the first part of the course was our ability to read from JSON and CSV files. We could have an object which sole purpose was to read from external files and convert them into Python.

`SLIDE 3`

So our objects can be anything

**ASK**
Take a moment and think about what the data and behaviours may be for some of these possible objects.

**ANSWER**
- Customer
  - data
    - orders
    - member since data
    - address
  - behaviour
    - add to basket
    - make order

- Bank Account
  - data
    - balance
    - interest rate
    - number of seperate accounts
  - behaviour
    - make a payment
    - receive a payment

- E-Commerce Order
  - data
    - total cost of order
    - items in basket
    - supplier
    - courier
  - behaviour
    - ammend an order
    - return an order

A lot of these things feel fairly abstract but take returning an order for example. All of our consumer rights dictate we're able to return an order. 

Image we work for Argos and do lots of business fulling orders. If we can programmatically create a object for every single order we process and give them all the ability to process a return or another behaviour like a cancellation, that saves huge cost define that functionality individually for each order.

---

### Objects as Models
Objects are *models* of real-world or hypothetical concepts. There few things where we can't define an object for.

Whether that be:
- A `Customer`
- A `Router`
- A `BankAccount`
- A `GameCharacter`

Each has:
- Properties or data
- Actions it can perform

This is the paradigm which Python is built upon. I said to you before that all our datatypes in Python are essentially objects. 

If we think about a string.

**main.py**
```python
string = "Hello World"
```

**ASK**
What data or properties would this string have?
**ANSWER**
- The **value**
- The **length**

**main.py**
```python
string = "Hello World"

print(len(string))
```

- *RUN* `python main.py`

**ASK**
What about the behaviours? What can it do as a string?

**ANSWER**
The string based methods

**ANNOTATED**
**main.py**
```python
string = "Hello World"

print(string.upper()) # CAPITALISES ALL CHARACTERS
print(string.lower()) # LOWERCASES ALL CHARACTERS
print(string.title()) # CAPITALISES FIRST CHARACTERS OF EACH NEW WORD
print(string.replace("World", "VMO2")) # REPLACES FIRST ARGUMENT IN STRING WITH THE SECOND ARGUMENT
print(string.split()) # CONVERTS STRING TO LIST
print(string.startswith("Hello")) # RETURNS BOOLEAN VALUE IF STRING STARTS WITH THE PAST ARGUMENT
```

**NOT ANNOTATED**
**main.py**
```python
string = "Hello World"

print(string.upper()) 
print(string.lower()) 
print(string.title())
print(string.replace("World", "VMO2"))
print(string.split())
print(string.startswith("Hello")) 
```

- *RUN* `python main.py`

As we've said already these are called **string methods** and remember **methods** are essentially pieces of **functionality** which exist on objects. 


---

## Why OOP Exists

So why does OOP exist in the first place?

### The Problem OOP Solves
As programs grow:
- Data becomes scattered
- Functions multiply
- Then the relationships become unclear between all these seperate pieces of data and functionality
- It's those changes which become risky

OOP exists to:
- Reduce mental load
- Group related logic together
- Make large systems easier to reason about


OOP isn't there to make programmes faster. It makes *developers* faster and importantly safer.

---

### Life Before OOP (Function-Only Thinking)

I'll show you some code which would look familiar to what we were doing yesterday

They'll be two functions, one to calcuate a customer discount and one basically printing a customers name. 

**main.py**
```python
def calculate_discount(customer_type: str, total: float) -> float:
    if customer_type == "vip":
        return total * 0.8
    else:
        return total * 0.95


def print_customer(customer_name: str, customer_type: str) -> str:
    print(customer_name, customer_type)
```

This works, and the type hints make it clear what data types are expected. 

However, as an application grows, this approach can start to cause problems.

The same pieces of data (such as **customer_type**) are passed around to multiple functions, even though they all conceptually belong to a customer. That relationship isn’t explicit in the code — it exists only in the developer’s head. 

As a result, it becomes easy to mix up arguments, misuse functions, or call them in the wrong context.

Over time, this makes the code harder to reason about, harder to change, and more fragile as the system grows.

Some of the best paying jobs in tech are based in legacy or older companies, where all these relationships in big programmes exist inside the developers mind and companies can't afford for them to leave, just because a new hire is never going to understand how these things fit together.


What happens if our data set needs to grow, if we add 5 more customer attributes about their, **age, start_year** or anything else?

If a customer recieves a discount it's based on their location. Do we need to add this to our **print_customer()** function. Things can get messy. 

---

### OOP’s Core Idea
This is why OOP exists.
The core idea is to put the data **and** the logic that works on that data in one place.

Instead of passing data into lots of functions

We pose the question can an object to do something itself and if so we create a class for those objects. 

---

## Objects vs Functions

What I'm saying now by the way doesn't mean functions by themselves have no value. 

### Functions 

Functions are great when:
- Logic is stateless
  - That is, they don't need to remember anything between calls, they receive an input, perform an operation and return a result
  - There's no hidden context just input -> output 
- Also when behaviour is simple and reusable
  - It does one thing, easy to describe and can be reused in multiple places
- Lastly when there’s no long-lived data
  - Once the function has finished running, everything needed is gone, when data is passed between many functions and there's lots of relationships between them then objects start to become helpful.



Take:
- Parsing input - converting from one datatype to another
- Calculations
- Formatting values

**main.py**
```python
def calculate_tax(amount):
    return amount * 0.2
```

With something like this, imagine we developed some accounting software, and we can calculate tax for the user:
- someone can say how much something cost
- we'll pass it into the function
- return the value to the user

The state and information can dissappear and the function can be run thousands of times with different users. 

Functions are not “bad” — they’re foundational.

---

### Objects — When They Shine
Objects are useful when:
- Data has identity
  - When data represents a real or conceptual thing, like our **bus** or **customer**, grouping related values gives data a clear identity and meaning within a system
- Or when state changes over time
  - Objects really shine when data evolves, if our customer upgrades from a basic package to a vip package for instance
- Behaviour also depends on internal state
  - What this means is, if an action is dependant on what that action is being performed on, objects allow a natural ability to update their information
  - If we take an order for example and a behaviour or method could be adding a product to a basket, then an awareness of what's already in the basket is instrinsicly linked. 


If something has a lifecycle, it’s usually a good candidate for an object.

---

### Side-by-Side Comparison

Let's look at writing out some logic using a functional approach and an OOP approach

#### Function-Based Approach

It's not going to be overly complex but I want to illustrate a point

**main.py**
```python
def add_device(devices: list, device: str):
    devices.append(device)
    return devices

original_devices = ["Mobile", "Smart TV"]

updated_devices = add_device(original_devices, "Router")

print(updated_devices)
```

- *RUN* `python main.py`

This code works and is easy to understand at a small scale. However, it also highlights some important limitations of a purely function-based design when data starts to matter.

Issues:
- Caller must manage state, when I say "caller" I mean the person who triggers this code
  - The function does not own the list of devices — it simply receives it, modifies it, and hands it back.
  - the caller must remember to store the returned value
  - the caller must understand that the list has been mutated
  - state management is spread across the codebase
- Easy to misuse
  - Because the function accepts any list, it can be called in unintended or incorrect contexts, I could pass a list of countries and it'd still work.
- No ownership of data
  - The list of devices doesn’t belong to anything — it’s just data being passed around.

---

#### Object-Oriented Approach

Let's look at the OOP apprach

So we start off with the **class** keyword. Followed by the name of the class we're creating. 

**main.py**
```python
def add_device(devices: list, device: str):
    devices.append(device)
    return devices

original_devices = ["Mobile", "Smart TV"]

updated_devices = add_device(original_devices, "Router")

print(updated_devices)





# NEW CODE
class Customer:
```

The main purpose of creating these classes, again, is to create objects at scale and we fire a function underneath the hood. That's refered to as a **constructor function** and it's purpose of the construct instances or the class, i.e. our objects. 

So that function is always called **dunder init**, written, double underscore, init, double underscore. 

The first parameter is always going to **self** and we'll see how that enables each instance to understand it's own data. 

**main.py**
```python
def add_device(devices: list, device: str):
    devices.append(device)
    return devices

original_devices = ["Mobile", "Smart TV"]

updated_devices = add_device(original_devices, "Router")

print(updated_devices)





class Customer:
    # UPDATED CODE
    def __init__(self, name: str):
```

This code right now means, we can call our Customer class and we have room to pass in information about the Customer name.

I also want to give each customer a list of devices they may own. That'll always be initiated as an empty list, which translates as all of our customers being new and not having pre-existing devices.

**main.py**
```python
def add_device(devices: list, device: str):
    devices.append(device)
    return devices

original_devices = ["Mobile", "Smart TV"]

updated_devices = add_device(original_devices, "Router")

print(updated_devices)





class Customer:
    def __init__(self, name: str):
        self.name = name
        self.devices = []
```

What we're seeing is **self dot** and that self. is creating a property or attribute, every single time we call the class constructor. 

Right now, each Customer will have a name, which we pass in as an argument and also a **devices** property, which is an ampty list. 

Now that we have limited data about each hypothetical customer, I want to define a behaviour. 

Every instance of the customer class, should equally have the ability to add a new device.

This is a function or method, defined within the class, so we'll need to ident to the same level as our constructor function and define that method. 

**main.py**
```python
def add_device(devices: list, device: str):
    devices.append(device)
    return devices

original_devices = ["Mobile", "Smart TV"]

updated_devices = add_device(original_devices, "Router")

print(updated_devices)





class Customer:
    def __init__(self, name: str):
        self.name = name
        self.devices = []

    # NEW CODE
    def add_device(self, device: str):
```

Practically, if we had five thousand customers, they'd all potentially have different devices, so we pass in **self** as the first parameter so when the instances of our customer class, use the **add_device** function, they understand the data which relates to themselves. 

The last thing is just to define the actions, within the code block. 

We target the instances devices property and then we want to append the new device passed. 

**main.py**
```python
def add_device(devices: list, device: str):
    devices.append(device)
    return devices

original_devices = ["Mobile", "Smart TV"]

updated_devices = add_device(original_devices, "Router")

print(updated_devices)





class Customer:
    def __init__(self, name: str):
        self.name = name
        self.devices = []
        
    def add_device(self, device: str):
        self.devices.append(device)
```

The difference is now, when we call the **add_device** function from an instance of the customer class, that data and behaviour all relates to each other. Our customer.

Let's call it, and I'll remove our standard function at the very top of the page. 

**main.py**
```python
class Customer:
    def __init__(self, name: str):
        self.name = name
        self.devices = []
        
    def add_device(self, device: str):
        self.devices.append(device)
        
paul = Customer("Paul")
paul.add_device("Router")
```

When we create Paul, Paul with has a **name**, which we pass as the sole argument, we don't worry about **self**.

Additionally we add a list of **devices**, these are his properties or information.

We should also be able to see which part of this class relates to the objects data and the methods or behaviours.

Now, if we have 5 or 5 million customers, each of them have this shared data blueprint and the ability to add a device. 

Let's print some data and create another customer and give them some devices. 

**main.py**
```python
class Customer:
    def __init__(self, name: str):
        self.name = name
        self.devices = []
        
    def add_device(self, device: str):
        self.devices.append(device)
        
paul = Customer("Paul")
paul.add_device("Router")
print(paul.devices)

susan = Customer("Susan")
susan.add_device("Mobile")
print(susan.devices)
```

One more thing to point out is we can see we use **dot notation** when accessing attributes and methods from objects instead of square brackets. 

**ASK**
Out of curiosity, anyone from the first part of the course, can you think of a way we could pass in multiple devices at once, instead of one at a time?

**ANSWER**
Our variadic functions

Very quickly for those who didn't attend the first part, we can alter our functions to accept a ranging number of arguments by placing one or two asterixes next to the parameter. 

One asterix, which is the most common, basically takes a ranging number of arguments and the function recieves them as a **tuple**. 

Let me show you.

**main.py**
```python
class Customer:
    def __init__(self, name: str):
        self.name = name
        self.devices = []

    # UPDATED CODE
    def add_device(self, *device: str):
        # NEW CODE
        print(device)
        # UPDATED CODE
        # self.devices.append(device)
        
paul = Customer("Paul")
paul.add_device("Router")
print(paul.devices)

susan = Customer("Susan")
# UPDATED CODE
susan.add_device("Mobile", "TV", "Printer")
print(susan.devices)
```
- *RUN* `python main.py`

Then all I want to do is loop through that tuple and append each element seperately. 

**main.py**
```python
class Customer:
    def __init__(self, name: str):
        self.name = name
        self.devices = []
        
    def add_device(self, *devices: str):
        # NEW CODE
        for device in devices:
            self.devices.append(device)
        
paul = Customer("Paul")
paul.add_device("Router")
print(paul.devices)

susan = Customer("Susan")
susan.add_device("Mobile", "TV", "Printer")
print(susan.devices)
```

- *RUN* `python main.py`

To bring it back to OOP

It's benefits are: 
- Data and behaviour live together
- Clear ownership of state
- Easier to extend safely

If we want Paul or Susan to have an address or a membership tier as part of their data or the ability to remove devices, there's a centralised **class** we can look to, to impliment those changes. 

**main.py**
```python
class Customer:
    def __init__(self, name: str):
        self.name = name
        self.devices = []
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
        
paul = Customer("Paul")
paul.add_device("Router")
print(paul.devices)

susan = Customer("Susan")
susan.add_device("Mobile", "TV", "Printer")
print(susan.devices)

cleo = Customer("Cleo")
martin = Customer("Martin")
natalie = Customer("Natalie")
```

We've created three new objects, Cleo, Martin and Natalie quickly and cheaply. 

---

### Challenge

I want you to expand our customer class, our application has grown and now I want each customer to hold information about their **internet speed**.

I want you to add that attribute to the class, it should be an **int** and also a method which allows the customer to increase their internet speed by a given value when the method is called. 

So an additional piece of data and another behaviour. 

I'll give you 10 minutes to do that. 

Feel free to remove the instances of **Susan, Cleo, Martin and Natalie**, we can just work with Paul for clarity.

**SOLUTION**
**main.py**
```python
class Customer:
    # UPDATED CODE
    def __init__(self, name: str, internet_speed: int):
        self.name = name
        # NEW CODE
        self.internet_speed = internet_speed
        self.devices = []

    # NEW CODE
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)

# UPDATED CODE
paul = Customer("Paul", 200)
# NEW CODE
paul.increase_internet_speed(20)
paul.add_device("Router", "Mobile")
# NEW CODE
print(paul.internet_speed)
print(paul.devices)
```


*BREAK*



## Key OOP Concepts (High Level)

So that's a basic understanding of OOP. 

I want to talk to you about the four main principles, sometimes called the four pillars of OOP. 

These pillars basically describe how objects and classes should be designed and how we interact with them. 

We'll go through them but as a highlevel overview, they're:
- **Encapsulation** - which refers to bundling data and methods which manipulate that data inside of a class in a way which restricts direct access to the data
- **Inheritance** - which allows one class to reuse and extend another class
- **Polymorphism** - meaning, different objects can respond to the same method in different ways
- And finally **Abstraction** - which means hiding complex implementation details and only showing the essential features



### Encapsulation

Let's start with encapsulation.

Encapsulation means:
- Hiding internal details
- Exposing clear behaviour

It's about reducing what other code needs to *know*.

This is important because how we structure data and behaviours directly affects how easy a system is to understand and extend. 

Without encapsulation it's harder to answer simple questions like:
- what changed Paul's devices?
- when did it change?
- was the change intentional?

Right now, there's nothing stopping me writing the code which changes Paul's name to Emile.

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int):
        self.name = name
        self.internet_speed = internet_speed
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
        
paul = Customer("Paul", 200)

# NEW CODE
paul.name = "Emile"
print(paul.name)
```

- *RUN* `python main.py`

*UNDO CHANGES*

---

Encapsulation is about controlling *how* other code interacts with your object.

I'd like to emphasise the *control* within that

---

### Encapsulation in Practice

Encapsulation is not about secrecy.

It’s about **intentional access**.

In Python, this is mostly done by **convention**, not enforcement.

---

#### Public vs “Private” Attributes

If we were to extend this class, we could include information about a customers **password** or **address** and other sensitive information. 

These pieces of data are obviouisly quite delicate and we'll need to manange these attributes slightly differently. 

We have this concept of **public attributes** and **private attributes**


Public attributes:
- Are part of the object’s external interface
- They're considered safe for other code to read or modify
- Represent stable, meaningful data

In our class so far, **name** and **devices** are both public attributes

Public attributes are named, what we'd consider, "normally" and that tells other developers that they can be accessed and modified relatively freely. 

---

#### “Private” Attributes (By Convention)
Python uses naming conventions to signal intent. We've seen it before with **constant variables**. They shouldn't be changed and we define them all in upper case. 

**main.py**
```python
# NEW CODE
OUR_GALAXY = "Milky Way"

class Customer:
    def __init__(self, name: str, internet_speed: int):
        self.name = name
        self.internet_speed = internet_speed
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
        
paul = Customer("Paul", 200)

paul.name = "Emile"

print(paul.name)
```

Nothing is enforced which will actually stop anyone who wants to update our variable from updating it but they'll see it's all written in upper caps and they have to then ignore the intention of other developers or themselves and change it. 

REMOVE CONSTANT VARIABLE**

The same approach is true for **private attributes**, when the constructor runs, we can modify the attribute name to convey meaning. 

**main.py**
```python
class Customer:
    # UPDATED CODE
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        # NEW CODE
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)

# UPDATED CODE
paul = Customer("Paul", 200, "seanbean007")

```

This **password** would be a private attribute

Explain:
- A single underscore means “internal use”
- It is a signal to other developers, not something which will stop the attribute being used

Which is fine, I could access the **password** outsite the class if I wished but this is where the culture in the team comes in to play. 

For me to know there's an attribute of **password**, I'd have to see the class and then I'd see the underscore. 

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
        
paul = Customer("Paul", 200, "seanbean007")

# NEW CODE
paul._password = "hello-world123"
print(paul._password)
```

As a developer if I go and then write a lot of code which accesses the **password** externally from the class, or allows someone to do so, I'd suggest that's an issue with myself regarding my technical skill or perhaps a cultural issue within the organisation.

Python trusts developers to respect boundaries.

---

### Why Python Doesn’t Enforce Privacy
There's good reason Python doesn't enforce privacy too
Python assumes:
- Professional discipline
- And prioritises readability over restriction

Compared to languages like Java and C++, Python is much more readable and cleaner to work with but Python's tradeoff is that it lacks sytnax we could write to literally block you from accessing attributes outside a class.

There's benefits to both approaches. 

Working with Python it's really about the clairty of code and signalling intention. 


---



### Objects Communicate
Our objects will be communicating with other objects a lot of the time which we'll see. Again, **encapusulation** has an opinion on this.

We want to be able to limiit what's accessible from one object to another. If we want to expose what devices Paul has, then it's better if we know exactly how and when that can happen. 

It's easy to understand if we have access to sensetive data, hypothetically for Paul's address, it's important we can limit exactly how and when a customer's data is exposed. 

I'll show you technically how this is done shortly but if there's only one way our programme can reveal an address, if an address is then revealed, it's far easier to debug what's gone wrong compared to if data is free romaing through software.

It's like if we had a large house with a front door, a side door and a back door. If someone breaks in, a police officer would have to find out where that entry took place. 

If there was only a front door, we'd know where the weakness in our property was immediately. 


---

*BREAK*

I want to cement our understanding of this class as it currently stands. 

#### Constructor (`__init__`)

Let's break down the components of our class again and we'll start with the constructor function

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
```

### What the Constructor Does
The constructor function or what we see `__init__` is a function:
- Runs automatically when a new object is created
- Sets up the object’s initial state
- Ensures the object starts life valid

If I add a print statement to the function, we'll see everytime we create a new instance, the constructor functions runs, and we should see our print statement logged

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        # NEW CODE
        print("Constructor function running")
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)

# UPDATED CODE        
paul = Customer("Paul", 200, "seanbean007")
cleo = Customer("Cleo", 300, "password1234")
samantha = Customer("Samantha", 250, "northernlights54")
```

- *RUN* `python main.py`
 
The constructor is where an object is *born*

We take the arguments passed when we call the class and pass those values into the new object. 


Without a constructor:
- Objects may be incomplete
- State may be inconsistent
- Bugs appear later 

What would happen if we forgot to set the `internet_speed`? How could it affect our code later in a programme. 


Constructor parameters:
- Define what data is required to create the object
- Communicate the object’s dependencies clearly

A lot of the time and when you'll be working on your projects, a big part of it will be discussing what classes you want to create and then what information you'll need available to you. 

---



#### What `self` Is
`self` refers to:
- The current object
- The instance receiving the information 

`self` is how an object talks about itself.


---

### Why `self` Is Required
Methods need a way to:
- Access the object’s data
- Distinguish between different instances

With our method **increase_internet_speed**, we need a way to refer to the specific customer calling the method

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
```

Explain:
- `self.internet_speed` belongs to *this* customer
- Another customer has their own `internet speed`

---

#### Common Beginner Confusion

A common thought is often, “Why do I have to pass `self`?”

Explain:
- Under the hood, Python passes the object automatically
- Writing `self` makes it explicit and readable

I'll remove **cleo** and **samatha** again. 

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
        
paul = Customer("Paul", 200, "seanbean007")
```

Internally what happens is we call our class method and we pass the instance and any other arguments being used. So If I want to add some devices. It'd look like:


**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
        
paul = Customer("Paul", 200, "seanbean007")
Customer.add_device(paul, "Router", "TV")

print(paul.devices)
```

This is because the **add_device** method is defined on the Customer class but we're specifically calling this on the instance of Paul. 

It is a little complicated just remember to pass `self` to get access to an instances own data. 

---

## Micro Exercise (5–10 mins)

`SLIDE 4`

### Task
1. Create a `Device` class.
2. Add:
   - A public attribute `name`
   - An internal or private attribute, called: `_status`
3. Use `__init__` to set both.
4. Add a method to change the device status.
5. Add a method to display device details.

We don't need to be too specific about what value **status** takes, but things like `offline`, `online` are fine.

When displaying information, I'd invite you to return an f string which basically includes the name and status. 

I'd also like you to think about datatypes and add typehints as well. 


**SOLUTION**
**main.py**
```python
class Device:
    def __init__(self, name: str, status: str):
        self.name = name
        self._status = status
        
    def update_status(new_status: str):
        self._status = new_status
        
    def display_details(self):
        return f"{self.name} currently has a status of {self._status}" 
    
router = Device("Router", "online")
print(router.display_details())
```

---

- Encapsulation controls access, not secrecy
- Python uses conventions, not strict enforcement




*BREAK*











## Inheritance & Polymorphism (Trainer Notes)

We've looked at **encapuslation** briefly, looking at keeping data private, let's turn to two other features of **OOP** which are **Inheritance and Polymorphism**.

Theres concepts revovle around extending one class from another and different objects using the same method in seperate contexts. 

---

### Inheritance

Let's start with inheritance. 

Inheritance allows one class to:
- Reuse behaviour from another class
- Extend or customise that behaviour
- Represent an “is-a” relationship

---

What do I mean by a **is a**

`SLIDE 5`

If we had a class for an Animal, we could say:

- A `Dog` **is an** `Animal` → which is inheritance  
- Also a `Cat` **is an** `Animal` -> which is inheritance
- However a `Table` **has** legs → which is called composition instead 


---

Let's write down an example

We've already got a class for a Customer. 

What if we got to the point where our Customer class has grown so much, there's lots of attributes and methods defined.

We may want to seperate some of these pieces of data and behaviour out. 

For Business Customers and maybe for Student Customers or VIP Customers, each with more specific behaviours and data. 

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
        
# NEW CODE
class BusinessCustomer(Customer):
    pass
```

What we're saying is a BusinessCustomer **is a** Customer, and I refer back to that **is a**, so we're confident we can use inheritance. 

- A `BusinessCustomer` should inherit everything from the parent `Customer`, so like our regular Customer a BusinessCustomer will have a:
- name
- internet_speed
- password
  
We don't need to duplicate any of the data defined in the parent class. 

And because a Customer has the ability to **increase internet speed** because a BusinessCustomer **is a** type of Customer then it automatically has the ability to **increase internet speed** as well. 

---

### Base Classes and Child Classes

So we have this idea of **parent classess** and **child classess**

- **Base class** (parent): general behaviour  
- **Child class** (subclass): more specific behaviour  

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
        

class BusinessCustomer(Customer):
    pass

# NEW CODE
paul = Customer("Paul", 200, "seanbean")
print(paul.name)
```

- *RUN* `python main.py`

Everything should work if Paul is now a Business Customer. 

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
        

class BusinessCustomer(Customer):
    pass

paul = BusinessCustomer("Paul", 200, "seanbean")
print(paul.name)
```

- *RUN* `python main.py`

Although this is a fundamental feature across most programming languages we should still avoid deep inheritance chains — keep hierarchies shallow.

`SLIDE 6`

In this situation for us to understand what a GuideDog can do we have to look at and understand 4 other classes:
- Dog
- Pet
- Mammal
- Animal

This generally makes code harder to read and equally, if we change something in the Animal class, those changes often ripple unpredictably through the others. 

Generally speaking 2 to 3 levels of inheritance is normal. 

---


Let's add some behaviour to the BusinessCustomer class, something a BusinessCustomer can do but not a generic Customer. 

#### Adding New Behaviour in a Child Class

```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
        

class BusinessCustomer(Customer):
    # NEW CODE
    def generate_invoice(self):
        print("Requesting invoice")

paul = BusinessCustomer("Paul", 200, "seanbean")
print(paul.name)
```
So our child classes can add new methods but our base class remains unchanged

Let me turn paul back into a regular Customer and I'll create a new instance of our BusinesCustomer and call I'll try call the method

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
        

class BusinessCustomer(Customer):
    def generate_invoice(self):
        print("Requesting invoice")

paul = Customer("Paul", 200, "seanbean")
la_fosse = BusinessCustomer("LaFosse", 300, "courmayeur")

la_fosse.generate_invoice()
```

- *RUN* `python main.py`

As we'd hope, our business customer can call the method defined within it's class. 

Let's see if Paul can. 

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
        

class BusinessCustomer(Customer):
    def generate_invoice(self):
        print("Requesting invoice")

paul = Customer("Paul", 200, "seanbean")
la_fosse = BusinessCustomer("LaFosse", 300, "courmayeur")

paul.generate_invoice()
```

- *RUN* `python main.py`

It fails, "Customer object has no attribute 'generate_invoice"

This is helpful, we can keep parent classes managable in size and define more specific data and behaviours on child classes. 


---

### Method Overriding

Let's look at Method Overriding which I referred to briefly earlier

#### What Overriding Means
Method overriding allows a child class to:
- Replace base-class behaviour
- Customise how an action works

So the **Customer** can increase their internet speed but perhaps we want our BusinessCustomer to have the same behaviour but a different implimentation.

What I want is that everytime a BusinessCustomer increases their internet speed, they get 10Mbs extra as a bonus. 

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
        

class BusinessCustomer(Customer):
    def generate_invoice(self):
        print("Requesting invoice")

    # NEW CODE    
    def increase_internet_speed(self, increase: int):
        self.internet_speed += (increase + 10)




paul = Customer("Paul", 200, "seanbean")
la_fosse = BusinessCustomer("LaFosse", 300, "courmayeur")

# NEW CODE
la_fosse.increase_internet_speed(100)
print(la_fosse.internet_speed)
```

- *RUN* `python main.py`

Same method name, different behaviour.

---

So the method overrding we've implimented allows:
- Specialised behaviour
- Shared interfaces
- Cleaner conditional-free code
  - What I mean by that is we avoid having to write, if **lafosse** is instanceof Customer do this, otherwise do that. 

I hope it's a useful analogy but it'd be my assumption a computer game like Fifa, it's a computer game to play football matches, I think it would be leaning into OOP quite heavily and you could have a parent class of a generic footballer and then several child classes for:
- Goalkeepers
- Defenders
- Midfielders
- Strikers

All have the ability or the method to shoot but depending on who is shooting, that'll work to various degrees of success.

---

### Calling the Base Implementation

Let's call the parent class from our child class. What I'll do is define a method which just prints a basic string.  

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)

    # NEW CODE
    def test_function(self):
        print("Test function running")
        

class BusinessCustomer(Customer):
    def generate_invoice(self):
        print("Requesting invoice")
        super().__init__()
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += (increase + 10)




paul = Customer("Paul", 200, "seanbean")
la_fosse = BusinessCustomer("LaFosse", 300, "courmayeur")

la_fosse.increase_internet_speed(100)
print(la_fosse.internet_speed)
```

Then I'll remove Paul for the time being place a special function in our **BusiessCustomers** **generate_invoice** function

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
            
    def test_function(self):
        print("Test function running")
        

class BusinessCustomer(Customer):
    def generate_invoice(self):
        print("Requesting invoice")
        # NEW CODE
        super().test_function()
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += (increase + 10)



la_fosse = BusinessCustomer("LaFosse", 300, "courmayeur")
# NEW CODE
la_fosse.generate_invoice()
```

- *RUN* `python main.py`

So we can see our **test functions** print statement fired. 

`super()` refers to the parent class

So we're actually calling the parent class through the use of **super()** and then using dot notation to access the **test function**, all from within the child class. 

Let me remove this code:

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)

        

class BusinessCustomer(Customer):
    def generate_invoice(self):
        print("Requesting invoice")
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += (increase + 10)



la_fosse = BusinessCustomer("LaFosse", 300, "courmayeur")
```

But what this allows us to do is let us extend the data our classes have

So perhaps our BusinessCustomer will have data regarding their name, internet speed and password, but also maybe an account mananger

Let me refactor the code to show you

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)

        

class BusinessCustomer(Customer):
    # NEW CODE
    def __init__(self, name: str, internet_speed: int, password: str, account_mananger: str):

    def generate_invoice(self):
        print("Requesting invoice")
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += (increase + 10)



la_fosse = BusinessCustomer("LaFosse", 300, "courmayeur")
```

Our business customer now has it's own constructor, but we know the:
- name
- internet_speed
- password

Are assigned on the parent class, we need a way to pass these values to the parent Customer. 

This is where we'll commonly see **super** called

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)

        

class BusinessCustomer(Customer):
    def __init__(self, name: str, internet_speed: int, password: str, account_mananger: str):
        # NEW CODE
        super().__init__(name, internet_speed, password)
        
    def generate_invoice(self):
        print("Requesting invoice")
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += (increase + 10)



la_fosse = BusinessCustomer("LaFosse", 300, "courmayeur")
```

So now the flow of data visably flows through both classes. It arrives in the BusinessCustomer constructor function,  then the values we give are passed to the parent constructor and we use that parent class to create an instance of the BusinessCustomer. 

We're missing the argument for the account mananger and that's assigned directly on the BusinessCustomer.

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)

        

class BusinessCustomer(Customer):
    def __init__(self, name: str, internet_speed: int, password: str, account_mananger: str):
        super().__init__(name, internet_speed, password)
        # NEW CODE
        self.account_mananger = account_mananger
        
    def generate_invoice(self):
        print("Requesting invoice")
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += (increase + 10)


# UPDATED CODE
la_fosse = BusinessCustomer("LaFosse", 300, "courmayeur", "Daniel Whitaker")
```

So we can see that our BusinessCustomer now takes 4 arguments. 
1. Name
2. Internet Speed
3. Password
4. Account Mananger

The first three are all shared from the parent Customer class and the attribute for Account Mananger is specific for the BusinessCustomer.

Let me just add another method, unique to the BusinessCustomer

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)

        

class BusinessCustomer(Customer):
    def __init__(self, name: str, internet_speed: int, password: str, account_mananger: str):
        super().__init__(name, internet_speed, password)
        self.account_mananger = account_mananger
        
    def generate_invoice(self):
        print("Requesting invoice")
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += (increase + 10)

    # NEW CODE
    def request_account_support(self):
        print(f"Reaching out to {self.account_mananger} for support")


la_fosse = BusinessCustomer("LaFosse", 300, "courmayeur", "Daniel Whitaker")
# NEW CODE
la_fosse.request_account_support()
```

The last thing I'll show you before another activity, is just the order in which these constructors are called. I'll remove the `la_fosse.request_account_support` call at the bottom as well, just to make this a little clearer. 

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        # NEW CODE
        print("Customer constructor method called 1")
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        # NEW CODE
        print("End of Customer constructor method 2")
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)

        

class BusinessCustomer(Customer):
    def __init__(self, name: str, internet_speed: int, password: str, account_mananger: str):
        # NEW CODE
        print("BusinessCustomer constructor method called 3")
        super().__init__(name, internet_speed, password)
        self.account_mananger = account_mananger
        # NEW CODE
        print("End of BusinessCustomer constructor method 4")
        
    def generate_invoice(self):
        print("Requesting invoice")
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += (increase + 10)

    def request_account_support(self):
        print(f"Reaching out to {self.account_mananger} for support")


la_fosse = BusinessCustomer("LaFosse", 300, "courmayeur", "Daniel Whitaker")
```

**ASK**
Can anyone work out in what order these print statements will show, using the numbers on the end?

- *RUN* `python main.py`

**ANSWER**
- 3
- 1
- 2
- 4

## Micro Exercise (10-20 mins)

`SLIDE 7`

A little exercise for you now:
- Create a class for a Person
- Create a child class for a profession of your choice
- Both should have a method to go to work, where the parent class prints a generic message and the child class prints a more specific message. 
- Both the parent and child class should contain data for, name and age, whilst the child class has one more piece of data for their profession


**SOLUTION**
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
        
    def go_to_work(self):
        print(f"{self.name} is going to work")
        
class Teacher(Person):
    def __init__(self, name, age, profession):
        super().__init__(name, age)
        self.profession = profession
        
    def go_to_work(self):
        print(f"{self.name} is going to work to teach")
        
martin = Person("Martin", 31)
emile = Teacher("Emile", 34, "Teacher")

martin.go_to_work()
emile.go_to_work()
```
---

*BREAK*

## Polymorphism

Let's look at Polymorphism 

We've done Polymorphism through the method overriding already.


Polymorphism as a concept is more general

It means:
- Different objects respond to the same method name
- Behaviour depends on the object’s type



---

### Polymorphism in Action

*THIS CODE EXISTS IN STUDENT SUPORT*

**main.py**
```python
class Person:
    def __init__(self, name: str, age: int):
        self.name = name
        self.age = age
        
    def go_to_work(self):
        print(f"{self.name} is going to work")
        
class Teacher(Person):
    def __init__(self, name: str, age: int, subject_speciality: str):
        super().__init__(name, age)
        self.subject_speciality = subject_speciality
        
    def go_to_work(self):
        print(f"{self.name} is going to work to teach {self.subject_speciality}")
        

class Chef(Person):
    def __init__(self, name: str, age: int, restuarant: str):
        super().__init__(name, age)
        self.restuarant = restuarant
        
    def go_to_work(self):
        print(f"{self.name} is going to work at {self.restuarant}")   
        
martin = Person("Martin", 31)
emile = Teacher("Emile", 34, "History")
tom_kerridge = Chef("Tom", 52, "The Hand and Flowers")

martin.go_to_work()
emile.go_to_work()
tom_kerridge.go_to_work()
```

- *RUN* `python main.py`

---

We've called the same method three times, and needed no conditionals.

- We haven't need to write code which says, `if Tom Kerridge is an instance of Chef print, 'they're off to work at their restaurant`
- No type checks
- Python chooses behaviour at runtime based on the object


---

## Polymorphism vs Conditionals

The alternative would be each **go_to_work** method looking something like: 

### Conditional Approach (Avoid)

**main.py**
```python
class Person:
    def __init__(self, name: str, age: int):
        self.name = name
        self.age = age
        
    def go_to_work(self):
        print(f"{self.name} is going to work")
        
class Teacher(Person):
    def __init__(self, name: str, age: int, subject_speciality: str):
        super().__init__(name, age)
        self.subject_speciality = subject_speciality
        
    def go_to_work(self):
        print(f"{self.name} is going to work to teach {self.subject_speciality}")
        

class Chef(Person):
    def __init__(self, name: str, age: int, restuarant: str):
        super().__init__(name, age)
        self.restuarant = restuarant
        
    def go_to_work(self):
        print(f"{self.name} is going to work at {self.restuarant}")   
        
martin = Person("Martin", 31)
emile = Teacher("Emile", 34, "History")
tom_kerridge = Chef("Tom", 52, "The Hand and Flowers")

# NEW CODE
def go_to_work(person):
    if isinstance(person, Person):
        print("going to work")
    elif isinstance(person, Teacher):
        print("going to teach")
    elif isinstance(person, Chef):
        print("going to cook")
```

It's so messy, not very Zen of Python.

This is also very much our final pillar of OOP **abstraction**, we don't care about the underlying code and how it behaves, all we know is that **martin, emile and tom_kerridge** all go to work. 

*REMOVE RECENTLY ADDED CODE*

---

Our previous approach is 
- Cleaner
- Respects object responsibility

---


























### Class Variables vs Instance Variables

Let's look at some more advanced Class features in Python

What we've seen so far is that we can have the class and then we create objects from that class which we call instances and they all have their own data which relates to that specific instance. 

That makes sense. 

For our customer, they all have a name and those names will be different. 

We refer to these as **instance variables** and they belong to each instance of those objects. 

We also have the ability to define **Class variables** which belong to the class. 


Instance variables vary per object. Class variables are shared.



---


Let's take a look.

I'll bring back our code for the Customer class. 

**main.py**
```python
class Customer:
    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
```

The **instance variables** are our:
- name
- internet speed
- password

It makes sense that all of these are seperate dependant on the instance. 

Some information can relate to the class though and shared throughout.

**main.py**
```python
class Customer:

    account_type = "Standard"

    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
```

Each `Customer` has its own name etc., but all `Customers` created from this class have a `Standard` account type


**main.py**
```python
class Customer:

    account_type = "Standard"

    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)

# NEW CODE            
emile = Customer("Emile", 200, "gandalf2026")

print(emile.account_type)
```

- *RUN* `python main.py`

---


- One shared value
- Accessible via the class or instances
- Changing it affects all instances

---

Let me show you

**main.py**
```python
class Customer:

    account_type = "Standard"

    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
            
emile = Customer("Emile", 200, "gandalf2026")

# UPDATED CODE
print(Customer.account_type)
```

- *RUN* `python main.py`

If I change the value on the instance, it'll only change for that instance. 

**main.py**
```python
class Customer:

    account_type = "Standard"

    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
            
emile = Customer("Emile", 200, "gandalf2026")

# NEW CODE
emile.account_type = "Premiun"
print(Customer.account_type)
```

- *RUN* `python main.py`

But if I change the value on the class, that'll impact all instances. 

**main.py**
```python
class Customer:

    account_type = "Standard"

    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
            
emile = Customer("Emile", 200, "gandalf2026")

# NEW CODE
Customer.account_type = "Premium"
print(emile.account_type)
```

- *RUN* `python main.py`

Having this shared state is helpful when there needs to be a single source of truth. 

We spoke about how variables are stored in memory and being to refer to them many times improves performance and memory efficciency. 

You don't want to use shared state or class variables when the data is mutable or expected to change frequently though. 

We can start combining different aspects of Python together.

Let me swap out our **class variable** with something more exciting

**main.py**
```python
class Customer:

    # NEW CODE
    speed_tiers = {
        "standard": 100,
        "fibre": 500,
        "gigabit": 1000
    }

    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
```

Now I want to use this class information to provide some custom information back to each Customer.

**main.py**
```python
class Customer:

    speed_tiers = {
        "standard": 100,
        "fibre": 500,
        "gigabit": 1000
    }

    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)

    # NEW CODE            
    def get_tier(self):
        for tier, min_speed in self.speed_tiers.items():
            if self.internet_speed <= min_speed:
                return tier
        return "custom"

emile = Customer("Emile", 200, "gandalf2026")
```

What this is doing is basically looping over our different tiers of speed and it'll return the key of the category of internet speed their in. 

Remember if we have the **return** keyword we'll break out of the function. But if our **if** statement never fires, we'll just return **custom**

Anyway, I want to use this in another function to give a message back to a customer. 

**main.py**
```python
class Customer:

    speed_tiers = {
        "standard": 100,
        "fibre": 500,
        "gigabit": 1000
    }

    def __init__(self, name: str, internet_speed: int, password: str):
        self.name = name
        self.internet_speed = internet_speed
        self._password = password
        self.devices = []
        
    def increase_internet_speed(self, increase: int):
        self.internet_speed += increase
        
    def add_device(self, *devices: str):
        for device in devices:
            self.devices.append(device)
            
    def get_tier(self):
        for tier, min_speed in self.speed_tiers.items():
            if self.internet_speed <= min_speed:
                return tier
        return "custom"

    # NEW CODE
    def describe_internet_package(self):
        print(f"{self.name} has a {self.get_tier()} package")            
            
            
emile = Customer("Emile", 200, "gandalf2026")

# NEW CODE
emile.describe_internet_package()
```

- *RUN* `python main.py`


*BREAK*


Let's look at something called **decorators**, is a piece of code we usually add to our classes which modify or change the behaviour of methods without changing their core lgoic. 

That may be hard to conceptualise at first but I'll take you through a few examples. 

## `@property`

The first one we'll look at is **@property**.

`SKIP SLIDE 9`

### Why Properties Exist
Properties allow you to:
- Expose data like an attribute
- And enforce rules when reading or writing
- Change impementation without changing the interface


So what this picture is trying to illustate is there's a class with an attribute for internet speed and we're trying to set the speed value to -100 which the **@property decorator **is blocking.

We shouldn't be able to have a negative internet speed but right now there's no logic which would block this. 

---

### Basic Property Example

I'm still going to use a Customer class, but I'll make it simpler for these examples

**main.py**
```python
class Customer:
    def __init__(self, name: str, speed: int):
        self.name = name
        self._speed = speed

peter = Customer("Peter", 100)

peter._speed = -100
peter._speed = "Gandalf is the greatest wizard"

print(peter._speed)
```

So fairly simple code but there's an issue. 

- *RUN* `python main.py`

I shouldn't be able to change my speed to -100, definitely I shouldn't be able to change it to, "Gandalf is the greatest wizard".

Equally we've defined the attribute with an underscore so it's not the best practice to access it this way and lastly we've completely ignored the type hints. 

We've said before but the point of OOP is to try and model the world through objects and in our world right now someones account speed can be completely unrelated

The first thing I'll do is add in some protection about how we can read the speed value

**main.py**
```python
class Customer:
    def __init__(self, name: str, speed: int):
        self.name = name
        self._speed = speed

    # NEW CODE
    @property
    def speed(self):
        return self._speed

peter = Customer("Peter", 100)

# NEW CODE
print(peter.speed())
```



- *RUN* `python main.py`

We get an error, and that's because we treat this function like a **property** of the instance now. 

If we want to see information on speed, we should treat it like a property instead of a function. 

**main.py**
```python
class Customer:
    def __init__(self, name: str, speed: int):
        self.name = name
        self._speed = speed

    @property
    def speed(self):
        return self._speed

peter = Customer("Peter", 100)

# UPDATED CODE
print(peter.speed)
```

- *RUN* `python main.py`

Now we can see the speed

Explain:
- Looks like an attribute
- Behaves like a method

---

I appreciate you may not yet be impressed

But there's some common things we'll want to do with this **speed** value, we could:
1. **get** the value 
2. **set** or assign a value
3. **delete** the value

If these can be defined by functions or methods it gives us much more control about how they be be updated

Let me show you an example 

We'll use a series of decorators, the first one, generally is always to **get** or see information, then the subsequent decorators take the name of the function followed by **setter** or **deleter**

**main.py**
```python
class Customer:
    def __init__(self, name: str, speed: int):
        self.name = name
        self._speed = speed

    @property
    def speed(self):
        return self._speed

    # NEW CODE    
    @speed.setter
    def speed(self, value: int):
        if int(value) < 0:
            print("Speed cannot be negative")
        self._speed = value

peter = Customer("Peter", 100)

# NEW CODE
peter.speed = -100
```

- *RUN* `python main.py`

Now when I try to update the speed, if it doesn't pass the condition, we don't update it. 

This would also work if I tried to pass in my Gandalf string. 


This is implemented fairly often because now the validation lives close to the data

I'll add in a **deleter decarator**

**main.py**
```python
class Customer:
    def __init__(self, name: str, speed: int):
        self.name = name
        self._speed = speed

    @property
    def speed(self):
        return self._speed
    
    @speed.setter
    def speed(self, value: int):
        if int(value) < 0:
            print("Speed cannot be negative")
        self._speed = value
        
    @speed.deleter
    def speed(self):
        del self._speed

peter = Customer("Peter", 100)

peter.speed # CALLS GETTER
peter.speed = -100 # CALLS SETTER
del peter.speed # CALLS DELETER
```

`del` is a built in Python keyword to delete different values

Again, the main reason these are used is to add our own Python logic because allowing actions to complete. 

A **@speed.getter** does exist but it's rarely used, you'll usually just see **@property**


---

There's two more decorators I want to show you.  **classmethod** and **static method**


A class method belongs to the class, not a specific object or instance.

*REMOVE UNDERSCORE FROM _speed*

---

### Class Method Example

**main.py**
```python
class Customer:

    # NEW CODE
    default_speed = 100
    
    def __init__(self, name: str, speed: int):
        self.name = name
        self.speed = speed

    # NEW CODE
    @classmethod
    def with_default_speed(cls, name):
        return cls(name, cls.default_speed)

peter = Customer("Peter", 100)
```

So what is a **class method**

A class method:
- Receives the class as its first argument (`cls`) instead of the instance
- Often used as alternative constructors
 

So what that means is we can create instances often with generic data.

**main.py**
```python
class Customer:
    
    default_speed = 100
    
    def __init__(self, name: str, speed: int):
        self.name = name
        self.speed = speed

    @classmethod
    def with_default_speed(cls, name):
        return cls(name, cls.default_speed)

peter = Customer.with_default_speed("Peter")

print(peter.name)
print(peter.speed)

```

- *RUN* `python main.py`

What's happening is we call the Class method, **with_default_speed** and pass in the one argument, name, as Peter. 

Within the method's return statement we can see it'll evaluate as: `Customer("Peter", 100)` which is essentially our contstructor. Which we return to the variable `peter`

Not very common to see but they do allow us to create methods and impliment our own logic. 
Again, their use can get quite complex but simply allows us to create methods and add in our own logic.

We could add logic within our **classmethod** which said if the name parameter is "Emile" give an internet speed of 1000, else use the class default speed. 

Python isn't the primary language I use, I find it funny but the only time I've seen this type of logic used in industry was when X's codebase got leaked a couple of years ago after Elon Musk took over the company, during that period of disruption. 

Anyway, someone noticed some code implemented which showed that each tweet was an instance from a class and this type of **classmethod** was implimented saying if it was Elon Musk was where the post originated, give that post additional visable etc.. 

Fun stuff. 

---

### static methods

Lastly I'll talk about **staticmethods**


A static method:
- Lives inside a class
- Does *not* receive `self` or `cls`
- And is logically related to the class


---

**main.py**
```python
class Customer:
    
    default_speed = 100
    
    def __init__(self, name: str, speed: int):
        self.name = name
        self.speed = speed

    @classmethod
    def with_default_speed(cls, name):
        return cls(name, cls.default_speed)

    # NEW CODE
    @staticmethod
    def estimate_download_time(file_size_mb: int, speed_mbps: int):
        return f"Estimated download time {file_size_mb / speed_mbps} seconds"
```

So our **static methods** have no access to instance or class data but improve organisation, we can call them either on instances or classes. 

**main.py**
```python
class Customer:
    
    default_speed = 100
    
    def __init__(self, name: str, speed: int):
        self.name = name
        self.speed = speed

    @classmethod
    def with_default_speed(cls, name):
        return cls(name, cls.default_speed)
    
    @staticmethod
    def estimate_download_time(file_size_mb: int, speed_mbps: int):
        return f"Estimated download time {file_size_mb / speed_mbps} seconds"


peter = Customer.with_default_speed("Peter")

# NEW CODE
print(peter.estimate_download_time(100, 10))
print(Customer.estimate_download_time(200, 5))
```

- *RUN* `python main.py`

---

There's often the question whether functionality like this be defined in the class or as a seperate standalone function

Ask:
- Does this logic conceptually belong with the class?
- Does grouping it here improve readability?

If yes → static method.

In this case, I don't think this functionality relates to a customer close enough. 

More applicable I think would be checking if a phone number is valid. 

Let me refactor our code a little and create our customer instance the old fashioned way. 

**main.py**
```python
class Customer:
    
    default_speed = 100

    # UPDATED CODE
    def __init__(self, name: str, speed: int, phone_number: str):
        self.name = name
        self.speed = speed
        # NEW CODE
        self.phone_number = phone_number

    @classmethod
    def with_default_speed(cls, name):
        return cls(name, cls.default_speed)

    # NEW CODE
    @staticmethod
    def is_valid_mobile(number: str):
        return number.startswith("07") and len(number) == 11

# UPDATED CODE
peter = Customer("Peter", 200, "07123456789")
```

So we have a **static method** which exists on the class.

This for me works because conceptually checking for a valid number it related to the customer. 

I'm going to use this method, within our constructor function and basically check before we create the instance, that the phone number is valid. 

**main.py**
```python
class Customer:
    
    default_speed = 100

    def __init__(self, name: str, speed: int, phone_number: str):
        self.name = name
        self.speed = speed
        # NEW CODE
        if Customer.is_valid_mobile(phone_number):
            self.phone_number = phone_number
            print("Valid phone number")
        else:
            self.phone_number = "Invalid"
            print("Invalid phone number")

    @classmethod
    def with_default_speed(cls, name):
        return cls(name, cls.default_speed)

    @staticmethod
    def is_valid_mobile(number: str):
        return number.startswith("07") and len(number) == 11

peter = Customer("Peter", 200, "07123456789")
```

---



















## Modularity & Project Structure (Trainer Notes)


---

We'll finish today and finish our recap generally looking at **modularity**, how we achieve it and why it's important. 

---

## Why Modularity Matters

### The Problem with One Big File
Early Python learning often happens in a single file.
This works — until it doesn’t.

As files grow:
- Finding code becomes harder
- Changes become risky
- Unrelated logic mixes together
- Merge conflicts increase

Merging is when there's multiple people in a group coding together and if I add some python code in one file and someone else updates a class somewhere else in that same file - when we try to merge both of our changes to a central location they'll be conflicts. 

We're not looking at those specific tools but it's a critical part of writing code. 

---

### What Modularity Gives You
`SLIDE 11 - day_2_slidee_10`

Modularity helps us though

Modularity helps by:
- Grouping related code together
- Making responsibilities explicit
- Allowing safe, localised changes
- Improving testability and reuse which we'll come to

The easiest way to explain it is probably the difference between trying to build a shed and there's one massive tool you have to do the job, it's:
- heavy
- hard to handle
- confusing

It can do the job but maybe if you had a well organised tool box where you knew exactly what to find and where to find it. You'd be happier. 

Each module should have **one clear purpose**.

---

## Splitting Code into Files

### What a Module Is
In Python:
- A **module** is a `.py` file
- A **package** when we've been importing things into files is a directory of modules

Let's update our project structure.

I want a **project** folder and then 4 files inside it.
1. main.py
2. customers.py
3. devices.py
4. utils.py

```text
project/
│
├── main.py
├── customers.py
├── devices.py
└── utils.py
```

Explain:
- File names matter
- Names should reflect responsibility

---

### What Goes Where

- `main.py` → orchestration / entry point
  - usually where we'll launch our applcation from 
- `customers.py` → customer-related classes and logic
- `devices.py` → device-related classes and logic
- `utils.py` → shared helper functions
  - basically functions which have a broader use, like our tool box, we can keep them here and pull them out when needed

---

## Imports

One of the main thing about modularity if the need to import functionality, classes, objects from other files. 

### Basic Import Forms

**main.py**
```python
import customers # IMPORT 'customers.py'

from customers import Customer # FROM `customers.py` IMPORT REFRENCE TO 'Customer'

from customers import Customer, VIPCustomer # FROM `customers.py` IMPORT REFRENCE TO 'Customer' AND 'VIPCustomer'
```

Explain:
- `import module` keeps names explicit
- `from module import X` is more concise 

---

### How Imports Actually Work
Explain simply:
- Python executes the imported file **once**
- The module object is cached
- Subsequent imports reuse it


Practically just know importing runs code. It’s not just linking.

---

### Reading Imports as Dependencies
I'd encourage you when working with importants or looking at other peoples code
- Read imports top-down
- Treat them as dependency declarations, i.e. this programme is equipped to run because of a dependency on x, y and z. 

**main.py**
```python
from devices import Router
from customers import Customer
```

We don't know what this will because but we know whatever happens in **main.py** will involve a Router and a Customer. 

---

## Avoiding Circular Imports
One thing to note is we want to avoid what's known as **circular imports**

### What a Circular Import Is
A circular import happens when:
- File A imports File B
- File B imports File A

Python gets stuck mid-import and your programme generally won't behave itself. 

---

### Why Circular Imports Happen
Common causes:
- Poor separation of responsibilities
- There's a term caled “God” modules, where basically everything is imported into one file, that file knows too much and to break it down you start exporting from that file.

Again, a good seperation of responsibilities help this. 


---

### Example of a Problem

**customers.py**
```python
from devices import Device

class Customer:
    ...
```

**devices.py**
```python
from customers import Customer

class Device:
    ...
```

Explain:
- Both files need each other
- Neither finishes importing cleanly

---


## Packages and `__init__.py` (Light Touch)

Sometimes we want to control what's exposed. 

Let me structure this project with a little more complexity. 

I'll create a folder inside **project** called **devices** and inside that folder create three files. 
1. `__init__.py`
2. `router.py`
3. `mobile.py`

I'll also delete `devices.py` from the **project** folder

Explain:
- A directory becomes a package
- `__init__.py` controls what’s exposed

Think of it as the **main file** for this subsection of code

```text
devices/
├── __init__.py
├── router.py
└── mobile.py
```

**__init__.py**
```python
from .router import Router
```

Let's create a little application using these files. 

I want some code just to simulate a Customer connecting devices to a router. 

**customers.py**
```python
class Customer:
    def __init__(self, name: str):
        self.name = name

    def greet(self):
        print(f"Customer name: {self.name}")
```


**devices/router.py**
```python
class Router:
    def __init__(self, model: str):
        self.model = model

    def power_on(self):
        print(f"Router {self.model} powering on")
```

**devices/mobile.py**
```python
class Mobile:
    def __init__(self, brand: str):
        self.brand = brand

    def connect(self):
        print(f"Mobile {self.brand} connecting to network")
```

So we've got three classes, two of them exist inside the **devices** folder. 
I want to be able to export simply from **devices**, instead of going deeper to **router** and **mobile**, if we want 100 devices this would't be practical.

So from the **devices/__init__.py** 
```python
from .router import Router
from .mobile import Mobile
```

We can import both our Router and Mobile into this central reservation. 

It reads from the file **router.py**, that `.` basically means from the current file system so from the **devices folder** find the file called `router` then from that file import the class Router. 

Which allows us to import cleanly into **main.py**

**main.py**
```python
from customers import Customer
from devices import Router, Mobile
```

Now let's try and put it together, **main.py** now has access to all the classes we've defined. 

**main.py**
```python
from customers import Customer
from devices import Router, Mobile

customer = Customer("Emile")
router = Router("VM Hub 5")
mobile = Mobile("Apple")

customer.greet()

router.power_on()
mobile.connect()
```

*RUN CODE*

Let's define a funcion for **utils.py**

**utils.py**
```python
def print_divider():
    print("-" * 20)
```

**main.py**
```python
from customers import Customer
from devices import Router, Mobile
# NEW CODE
from utils import print_divider

customer = Customer("Emile")
router = Router("VM Hub 5")
mobile = Mobile("Apple")

customer.greet()
# NEW CODE
print_divider()

router.power_on()
mobile.connect()
```

*RUN CODE* 

Obviously there's a lot missing from this, we can add:
- inheritance (parent / child classes)
- encapsulation (hiding information)
- polymorphism (method overidding)
- decarators

---

## Exercise (1 hour)

# Mini Project: VMO2 Network Ops Simulator

## Scenario

You’ve just joined the **VMO2 Network Operations Team**.  
Your job is to bring devices online and keep the network running smoothly.

Each device behaves differently, but they all follow the same core rules.

🎯 **Your mission:** power up the network without breaking anything.

---

## Core Objectives (Must-Have)

### 1️⃣ Base Class — `Device`

Create a base class called `Device`.

It should include:

- `name` (string)
- `_status` (internal: `"off"` or `"on"`)

Add:
- `power_on()`
- `power_off()`
- a **read-only property** `status`

---

### 2️⃣ Specialised Devices (Inheritance)

Create two device types that inherit from `Device`:

#### 🚦 Router
- attribute: `frequency_band`
- overrides `power_on()`
- prints extra setup steps (e.g. *“Establishing network…”*)

#### 📱 Mobile
- attribute: `os`
- overrides `power_on()`
- prints a different startup message

Both should:
- call `super().power_on()`
- extend the behaviour

---

### 3️⃣ Safety Check (Static Method)

Add a static method to `Device`:

```python
is_valid_status(value: str) -> bool
```

---



## Solution

```text
.
├── device.py
├── router.py
├── mobile.py
└── main.py
```

**device.py**
```python
class Device:
    VALID_STATUSES = {"on", "off"}

    def __init__(self, name: str):
        self.name = name
        self._status = "off"

    @property
    def status(self):
        return self._status

    @staticmethod
    def is_valid_status(value: str) -> bool:
        return value in Device.VALID_STATUSES

    def power_on(self):
        if Device.is_valid_status("on"):
            self._status = "on"
            print(f"{self.name} powered on")

    def power_off(self):
        self._status = "off"
        print(f"{self.name} powered off")
```

**router.py**
```python
from device import Device

class Router(Device):
    def __init__(self, name: str, frequency_band: str):
        super().__init__(name)
        self.frequency_band = frequency_band

    def power_on(self):
        super().power_on()
        print(f"{self.name}: Establishing network on {self.frequency_band}")
```

**mobile.py**
```python
from device import Device

class Mobile(Device):
    def __init__(self, name: str, os: str):
        super().__init__(name)
        self.os = os

    def power_on(self):
        super().power_on()
        print(f"{self.name}: Booting {self.os}")
```

**main.py**
```python
from router import Router
from mobile import Mobile

devices = [
    Router("VMO2 Router", "5GHz"),
    Mobile("Customer Phone", "Android"),
    Mobile("Backup Phone", "iOS")
]

for device in devices:
    device.power_on()

if all(device.status == "on" for device in devices):
    print("\nNetwork online!")
```
