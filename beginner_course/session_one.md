# Essential Python — Fundamentals & Style (Instructor Edition)


---

# Pre Start

- Open Slidee and choose slide deck for: **Introduction Course Day 1**

`SLIDE 1`

# Trainer Start
Hello!

Really good to meet you all today, my name's Emile and I'm an engineering trainer for LaFosse. 

There's lots of stuff we're going to talk about today, hopefully you're all going to find it quite interesting.

When I've been desigining and going through this course, there's a couple of things I really hope you get out of it - firstly the ability to have conversations about code; what it does and how its running. 

For some of you I hope that you'll even be able to create some of your own simple software programs. 

I personally think of software as quite a creative discipline; it's technical of course, too. But at it's core, writing code is about solving problems and there's always a lot of different ways to achieve similar functionality.

I think its quite enjoyable and once we finish, you should be able to engage in more meaningful technical conversations.

As we go through the course, please do ask questions. One of the best ways to learn a programming language is to use it and they'll be plenty of opportunities throughout the day. 

`SLIDE 2`

In case anyone is isn't aware, we'll have two different sessions together which will cover the basics of Python. 

It's within these two sessions I hope you'll get to the point I mentioned earlier; where you can read a little bit of Python code.

Both sessions run for 3 and a half hours each, from 9 o'clock until 12:30 and we'll aim to have a couple of breaks in each.


`SLIDE 3`

Today we're going to looking at some of the fundamentals in Python. 

On the screen you can see variables, control flow, functions, loops. These are concepts which are true for most programming languages and they're what determine how software programms store data, make decisions and take actions. 

Every programming language has been developed to be used a certain way and Python is no different.

`SLIDE 4`

The **Zen of Python** was created as a set of principles for how Python should be written. 

The main takeway if you don't want to read it all, is the best Python code is simple, readable and obvious in its intentions. 

Code can and does get quite complicated and I'm sure there's things I'll show you today, which won't feel simple. 

One of my aims is for you to be able to break down some files, which initially may seem quite daunting but when you take those smaller components by themselves, it's actually quite manageable. 


## The training

Before we start, the training will be a mix of me talking you through why things are implimented a certain way in Python, but also asking you to have a go at writing some code for yourself. 

Most of my time is spent trying develop students technical skill, regarding different programming languages.

I also focus on on cloud computing, but regardless of the discipline, getting hands, even getting stuck, in my opinion is what helps people understand how software actually works. 

You're also free to make notes if you wish but I'll be recording these sessions and we'll make them available to you. 

I've also created a little cheat sheet for each session which I'll make sure is shared with you.



# 💻 How to Access and Use GitHub Codespaces

So the first thing we need to do is actually have somewhere to write code. 

Typically we'd write in what's called an IDE or an Integrated Development Environment, essentially somewhere we can type and execute our code locally. 

We're fortunate to not be having this session 60 years ago, programmers would use plug boards and switches, even pen and paper.

Now, generally speaking we'd download apps onto our computer and use them. 

Today we'll be using a program on the internet called GitHub Codespaces. You may have heard of GitHub, they're owned my Microsoft and their main business is sharing code repositories, big collections of code online and between teams. 

But they also have a development space where we can execute simple programs. 

**ASK**

Can I check that everyone has a GitHub account?

**IF NOT**

For those who don't, can you search for GitHub on Google and create an account - they won't ask for any card details - it's probably a worthwhile account to have. 

**WHILST WAITING**

Whilst we wait, it's worth knowing that at the beginning of 2026, Python was the most well used programming language. 

If your interest in Python extends beyond these sessions, there's lots of videos and documentation about how to do build more complex programms. That's because there's so much support for the language. 

The person who first created the language, a dutch man I believe, named it after Monty Python. 

**END OF FILLER**


1. If you can go to Google or any search engine, please type in **GitHub Codespaces**, it should be the first result. 

2. Once you've clicked through to the site, you should see a similar screen to my - click the **Get started for free** button. 

3. On this window there's several quick start templates.

We're learning about Python, working in that ecosystem requires one or two installations to access the programming language.  

The templates we can see exist to streamline all the downloads or dependencies we'd ordinarilly need to get up and running in some of the popular languages used.

4. Our environment is going to be fairly straight forward, we'll be using the **blank template** and please just click on the **use this template** button. 

So now we're really in codespaces, this window is basically where a code will live. On the left hand side is space for our file structure and in the middle is where we'll write our code. 

On the right hand side there's a panel for **build with agent**, we can close that as it's not going to helpful to us today. 


5. Let's create our first file, in the **explorer panel** to the left, click the **“new file”** icon.

It's convention in Python to name the entry point **main**, so I'm going to create a file, called **main.ipynb**. The extension **ipynb** tells codespace the contents of what we're writing. 

*CREATE CELL*

Ordinarilly Python files just have the extension **py** but by using **ipynb** we can create little code cells which is really nice for using the language for the first time and seperating our code. 

We'll start where most people do when using a language and that's outputting the message "Hello World" to the console. 

Lots of programmes fundamentally are used to see or display information and in Python the most universal way to do that is with a function called print. 

**CELL 1**
```python
print("Hello World")
```
Functions are bits of code which perform a given task. We can often identify functions by the brackets or parenthesies which follow their name. 

In prints case, we need to provide it with some content to log to the console. 

*RUN CELL*

Please join me in writing and running our first Python code. 

6. You should hopefully see a little pop up, what it's telling us is that Python isn't installed to run in this codespace and that we need to install it. 

I'll click on the install option and after a while I think it'll ask us to choose an environment.

I don't want to dwell on this too much but Python as most languages change over time, we should select a Python environment and then a specific version of Python to use as for our file. 

I think version 3.12 is the latest available. 


7. Let's try running the cell again and we should see our data logged to the console.


We're going to look at the different data types in more detail shortly but right now we've logged text.

Python refers to text based data as strings and the same way we can identify functions by their parenthesies, we can identify strings because they're wrapped in double or single quotes. 





## 🧩 Topic 1 — Introduction to Python & Programming Concepts

Python is known for being an accessible language. As we've said it's supposed to be readable. 

Part of that ease is due to it being what we call **interpreted**, by that I mean it runs code line by line, from top to bottom

If I update my code cell with a new line 

**main.ipynb**
```python
print("Hello World")
# NEW CODE
print("Goodbye World")
```
And run my code again...

*RUN CELL*

The "hello world" message will always be displayed before "goodbye world"

So when looking at code for the first time, start at the top and trace what's happening down a file. 

---

### Using Variables and Input

Right now we've provided some data, our string "hello world" to our print function which logs the message. 

The code never stores the string data, we pass it directly to the function. 

Very quickly the ability to store data becomes important so we can retain information and the way we store information is through variables.

We can think of them as containers or buckets which are associate with the actual data. 

Create a new cell with me

*CREATE CELL*

Our data was the string

**main.ipynb**
**CELL 2**
```python
"Hello World"
```

What I want to do is assign the data to a variable which I can refer to throughout the program. 

I'm going to choose a variable called 'greeting'

**main.ipynb**
**CELL 2**
```python
greeting = "Hello World"
```

That equals sign is called an **assignment operator**, we're taking the string data and passing or assinging it to the variable greeting. 

Now throughout the rest of the program we can use the variable name instead of the data directly.

If I want to print the string I can target the variable name. 

**main.ipynb**
**CELL 2**
```python
greeting = "Hello World"
print(greeting)
```

*RUN CELL*


Same output but we've put the message "Hello World" into a variable and then given the variable to our **print() function** instead. 

This process of variables holding different pieces of data makes things easier. 

So far we've stored a fairly simple string but if we were writing python code for, let's say, dealing with data for a customer, that's going to be much more complex. There is a datatype which can handle that fairly well which we'll look at, but if we can assign that complex data for a variable called **customer**, then it's much easier to move that data around a file and use it when we wish. 

I want to introduce you to another function in Python.

Print is all about logging data, showing it. Technically we refer to this operation as **output** 

Sometimes our scripts need to consume data or recieve **input** and there's a function called this. 

Let's create a new cell

*CREATE CELL*

**main.ipynb**
**CELL 3**
```python
name = input()
```

Let's run the cell

*RUN CELL*

On my screen a little window has popped up and it's requesting I type something in.

If I quickly type something and press enter it goes away.

Let's also use our print function again as well so there's input and output.

**main.ipynb**
**CELL 3**
```python
name = input()
# NEW CODE
print(name)
```
Run the code and type your name
*RUN CODE*

What's happening is the first line is taking an input, whatever I type is then passed to the name variable as a string, that value is passed to the print function which returns it back to us. 

We've seen with our print function, we passed some inforamtion inside it, whether it was our string or a variable which referened a string. 

We'll talk more about this later but these values we give to functions are called arguments.

Our input function also has the ability to take an argument, a string. 

What we type is going to be the message presented to us when we run the code. 

**main.ipynb**
**CELL 3**
```python
# UPDATED CODE
name = input("Enter your name")
print(name)
```
I'll run the code and we should see the new message

*RUN CELL*

I'm going to add another argument to the print function, I want to not only output my name, but also a little greeting

**main.ipynb**
**CELL 3**
```python
name = input("Enter your name")
# UPDATED CODE
print("Good morning", name)
```

In functions we seperate arguments with commas and the result it should print the two strings together. 

*RUN CELL & TYPE NAME*

The first string was passed directly into the print function and the second string we passed from the input function via the name variable. 


This works and is quite nice when we have a small output, one which involves a variable in a larger string like now.

If I wanted to get further input about my age and location, or anything else and print a longer string, something like: "Good morning Emile, you are 34 and living in London?" then this way of having lots of different arguments becomes convoluted. 


---

### Introducing f-Strings

There's a way in Python we can write formatted strings which take broader text and inject variables inside. 

They're called **f-strings**, short for formatted strings. 

I'll show you an example

*CREATE CELL*

I'll define a normal string and assign it to a variable
**main.ipynb**
**CELL 4**
```python
location = "Victoria"
```

If we wanted to output this normally, we'd simply pass the variable name as an argument to the print function. 

With formatted strings we still can, but we need to use a specific syntax.

**main.ipynb**
**CELL 4**
```python
location = "Victoria"
# NEW CODE
print(f"")
```

We're still passing a string as the argument, but with an 'f' infront so it's interpreted differently. 

Now if we want to inject a variable into the wider string we can by wrapping the variable in **curly braces**

**main.ipynb**
**CELL 4**
```python
location = "Victoria"
# UPDATED CODE
print(f"{location}")
```

*RUN CODE*

I appreciate that probably doesn't feel any better than what we've done before, but now I can wrap text around this variable and be a little more dynamic about string creation with other data. 

**main.ipynb**
**CELL 4**
```python
location = "Victoria"
# UPDATED CODE
print(f"The LaFosse office is in London near {location}.")
```

*RUN CODE*

## TASK 5 Minutes

I want you to apply this to a short program you'll write yourself.


`SLIDE 5`


---

## ⚙️ Topic 2 — Why Python is Used in Engineering Contexts

I want us to jump forward a little bit and look at a software application which could be genuinely useful. 

Python as a programming language is versitle and you'll see it used in many different industries and for different reasons. 

It can easily connect to external servers, it's great for generating data visualisations and manipulating data.

I know part of VMO2's tech operations is to process data and extract usful information about different pieces of infrastructure. 

I don't have access to that data but there's a few publically available APIs which I can connect to, use their data, and show you a more extensive program. 

I'll paste some code into a new cell and the first thing I want to say is, don't worry about the complexity. Over the next two sessions we're going to spend time looking at all the elements of this script. 

But I want to show you a potential end goal.

*CREATE CELL*

**main.ipynb**
**CELL 5**
```python
import requests

lines = ["Bakerloo", "Central", "Circle", "District", "Jubilee", "Metropolitan", "Northern", "Piccadilly", "Victoria"]


key = "c4cf7abec78c403aaa2fbd8fbe41fa05"

for line in lines:

    response = requests.get(f"https://api.tfl.gov.uk/Line/{line}/status?app_key={key}")
    
    if response.status_code == 200:
        data = response.json()
        service = data[0]['lineStatuses'][0]['statusSeverityDescription']
        
        print(f"{line} line has {service}")
    else:
        print(f"{line} returned status code {response.status_code}.")
```

In very broad terms, this is a script which tells me the status of the London tube lines, as they are right now. 

*HIGHLIGHT IMPORTS*

We've seen Python has built in functions already, but it doesn't make every tool accessible straight away, some things we have to import

*HIGHLIGHT LINES*

This is another data type and it contains a list of the London underground lines. 

*HIGHLIGHT KEY*

This is a key for the TFL API, an API is essentially software running on servers which exposes functionality or data. In this case, live information about the London underground. It costs them money to host the servers so TFL have a rule that we need a key to athenticate ourselves. 

*HIHGLIGHT  LOOP AND REQUESTS.GET*

This is where most of the magic happens, for every line in the lines list we send a request to the TFL API saying can I GET information about that specific line. 

*HIGHLIGHT STATUS_CODE 200 AND REST OF SCRIPT*

If we've successfully got back information, convert that data into Python code.

We get back quite a large object, so we go into the data and extract only the information we care about, store it to a variable and print it from within an f string.

This only happens if we get a status code of 200 or if things go well. You may have heard of a 404 too, 'NOT FOUND'? If things don't go well, we print another message telling us the errornous code. 

I just want to emphasise, this isn't the level of code we're expecting you to produce. Throughout the next two morning's we'll be looking at the different components which enable us to create a script like this and replicate to a smaller degree ourselves.

*RUN CELL*


Let's take a break and when we come back we'll start exploring some of the different elements of that code. 

**BREAK**

---

## 🔢 Topic 3 — Data Types & Variables

Welcome back.

We introduced some new concepts before the break which won't make sense right now. 

This next part of the session is going to be looking at some of the different data types. 

### Strings

So far we've had a look at strings. 

They're good when we're handling text based data:
- names
- addresses
- copy for online news

There's a lot we can do just with strings.

We've got hands on with two built in functions already, **print()** and **input()**. There's lots more built in functions which work with specific types of data. 

Let's create a new cell and define a variable for the city your in, I'll use London. 

*CREATE CELL*

I want you to write the city entirely in lower case and print it on the next line

**main.ipynb**
**CELL 6**
```python
city = "london"
print(city)
```

To use string methods we take our string, add a dot and then call our method name. I'm going to write a method called **upper()**

**main.ipynb**
**CELL 6**
```python
# UPDATED CODE
city = "london".upper()
print(city)
```

*RUN CELL*

I hope that's fairly self explanitory as to what we've done. 

The **upper()** method, works on text based data and capitalises each character.

In this example we've added it directly to the string before we assign the value to the variable.

We could also assign it to the variable if we choose. 

Let's cut the method from the string and place it onto the variable on the line below. 

**main.ipynb**
**CELL 6**
```python
city = "london"
# UPDATED CODE
print(city.upper())
```

*RUN CELL*

Most programming languagues have this type of built in functionality across different data types to help you with common tasks. 

If we were having this session a couple of years ago and you were looking to find a built in method, you'd use Google, look at Python's official documentation. Now, it looks like the most used choice is using a Large Language Model like CoPilot or ChatGPT. 

If we didn't want to capitalise the entire string and just the first character, there's a method for that as well. 

**main.ipynb**
**CELL 6**
```python
city = "london"
# UPDATED CODE
print(city.title())
```

*RUN CELL*

We're able to actually chain multiple functions together. 

If you can, update your original string to have "city" or "town", maybe "village" on the end. 

**main.ipynb**
**CELL 6**
```python
city = "london city"
print(city.title())
```

*RUN CELL*

So title, as we can see is finding each new word within the string and capaitalising that first character. 

Perhaps a few years from now, I want to move to Glasgow. There's a **replace()** method which attaches onto a string and accepts two arguments. 
1. The part of the string I want to replace
2. What I want to replace it with

I've got a mini quiz for you. 

I'm going to add two more cells and incorporate this replace method twice. I want you to have a think about which one will give me the desired result. 

*CREATE TWO CELLS*

**main.ipynb**
**CELL 7**
```python
city = "london city"
print(city.replace("london", "glasgow").title())
```

**main.ipynb**
**CELL 8**
```python
city = "london city"
print(city.title().replace("london", "glasgow"))
```

**ASK**
Which one will output 'Glasgow City' but the G and C capitalised?

*RUN BOTH CELLS*

It's the first one, the functions execute from left to right, meaning the replace function on the top cell first changes "london" to "glasgow" then capitalises the first characters. 

**ASK**

With that information, can anyone think why the second cell is still returning "London City"?

**ANSWER**

Well, we capitalise the "L" in London first, then the first argument in the replace method doesn't match anymore. 

## Ints & Floats

The next data type I want to look at is **numeric data**.

Strings are for text.

**Ints** and **Floats** are for numbers and the process is the same for assinging and reading.

*CREATE CELL*

**main.ipynb**
**CELL 9**
```python
speed = 200
cost = 34.50
print(f"The internet speed is {speed}Mbs and costs £{cost}")
```

*RUN CELL*

Unlike strings, there's less built in methods with **integers** and **floats**.

A lot of the time we're comparing values or performing different operations with them. 

I'm going to write out some common mathematical operators. 

Feel free to join me.

*CREATE CELL*
**main.ipynb**
**CELL 10**
```python
sum = 2+2
subtract = 8-4
multiply = 2*2
divide = 8/2
modulo = 9%5

print(sum)
print(subtract)
print(multiply)
print(divide)
print(modulo)
```

*RUN CELL*

All the results are 4 but notice, when we divide we always return a **float**. This is just the inbuilt functionality and perhaps the expection that division will more commonly return a number with a decimal place.

The percentage symbol or modulo at the bottom divides the two numbers but returns the remainder back to the variable. So 5 only divides into 9 neatly, once, then leaves a remiander of 4. 

We can also perform operations on our variables which hold numeric information as well. 

**main.ipynb**
**CELL 10**
```python
sum = 2+2
subtract = 8-4
multiply = 2*2
divide = 8/2

# UPDATED CODE
print(sum + subtract)
```

*RUN CELL*

Both variables reference the value 4 and we can add them together.

All of these operations are great, they'd be used in the software of a self service checkout at Tesco all the way to the calculator on your phone. 

It's at this stage I want to introduce logic into the conversation. 

Aside from the TFL programme, all of our cells are going to behave the same way, regardless of how often I run them. 

What makes software applications more advanced is the ability to have conditions and make decisions.

For this we need to be able to compare data and make decisions based on it.

*CREATE CELL*

**main.ipynb**
**CELL 11**
```python
bigger = 10 > 8
bigger_or_equal = 6 >= 6
equal = 5 == (2+2)
not_equal = 3 != 2

print(bigger)
print(bigger_or_equal)
print(equal)
print(not_equal)
```
*RUN CELL*

### Booleans

This leads us into Booleans - a concept which is fiarly universal across all programming laguages. 

From the output we can see based on the comparison, something is either True or False. 

Booleans are used heavily in any logical decisions programms take. 

We do this if something is true or we do something else if it's false. 

We can assign boolean values to variables as well but also note that values can be considered Truthy and Falsey.

No need to code along with this but some things are obviously true. 

*CREATE CELL*

If I define a variable and assign the value True, then it stands to reason it's True.

**main.ipynb**
**CELL 12**
```python
boolean_value = True
```

The same thing works with False and as you've seen, when we use comparison operators we get boolean values of true and false as well. 

However some data is considered to be truthy or falsey.

Take a string

**main.ipynb**
**CELL 12**
```python
truthy = "Hello World"
```

The string "Hello World" is truthy because it's considered to have value

**main.ipynb**
**CELL 12**
```python
truthy = "Hello World"
also_truthy = 12
```

Again, the int, 12 is also truthy. 

It's easier to actualy learn what's not truthy, or considered falsey. 

- 0 is considered falsey as an int. 0.0 is also falsey as a float
- An empty string is considered falsey and other datatypes we've not looked at yet, if they're empty they're falsey

If something doesn't seem to have a value, it's most likely a falsey.

Practically this helps us to write some interesting code

#### and

*CREATE CELL*

Imagine we're running an e-commerce site as an online florist 

It stands to reason that for an order to be valid a couple of things have to happen
1. They need to have provided payment information
2. Added an item to the basket

We can convert this logic into Python using different operators and our knowledge of Truthy and False values

**main.ipynb**
**CELL 13**
```python
items = "12 Tulips"
payment_information = True


valid_order = items and payment_information

print(valid_order)
```

We know items should be Truthy as it has value and we have boolean true

What's new is the **and** operator. This will resolve to either true or false based on the conditions either side.

*RUN CELL*

Because 'items' and 'payment_information' are both truthy, valid_order will have a truthy value. 

Interestingly, if I swap 'items' and 'payment_information' around.

**main.ipynb**
**CELL 13**
```python
items = "12 Tulips"
payment_information = True

# UPDATED CODE
valid_order = payment_information and items

print(valid_order)
```

*RUN CELL*

We get our string printed back. 

This is because Python is trying to execute the code efficiently as possible.

We could be in the position where for the condition to return true, we'd need:
- a valid phone number
- an email
- and address
- payment information
- and items in the basket

We'd chain all of those together using the **and** operator between each one. 

Python tries to save time by evaluation from left to right.

*"Do we have a valid phone number... check. Do we have a valid email... check* 

If it fails at any point, there's no point checking about the address information because we've stipulated we need everything. So if any part of the condition returns falsey, the entire thing is false.

The reason we see '12 tulips' is because its the last condition and at that stage it's the only one which matters so we return that.

Because '12 tuplips' is truthy the entire expression is truthy. 

#### or

Our logic wont always be that we need everything truthy in order to carry about an action. 

If we revisit our florist, perhaps we can have a valid order if the customer has provided an address or said they'll collect - we don't need both.

I'll show you how we can program that. 

*CREATE CELL*

We'll no longer us the **and** operator, this time it'll be **or**

**main.ipynb**
**CELL 14**
```python
collection = False
delivery = True

valid_order = collection or delivery

print(valid_order)
```

*RUN CELL*

With the **and** operator, everything needed to be true for the expression to be true. 

Using the **or** operator on the other hand, only one part of the expression needs to be true, therefore developers tend to out the part of the expression they most likely expect to be true on the left hand side. 


### If/Else

*RESHOW THE TFL CODE*

The most common place we'll actually cosume these booleans is where you see the keywords **if** and **else**.

The easiest way to read this is basically, "if this condition is true do this, else do that"

**main.ipynb**
**TFL CODE**
```python
import requests

lines = ["Bakerloo", "Central", "Circle", "District", "Jubilee", "Metropolitan", "Northern", "Piccadilly", "Victoria"]


key = "c4cf7abec78c403aaa2fbd8fbe41fa05"

for line in lines:

    response = requests.get(f"https://api.tfl.gov.uk/Line/{line}/status?app_key={key}")
    
    if response.status_code == 200:
        data = response.json()
        service = data[0]['lineStatuses'][0]['statusSeverityDescription']
        
        print(f"{line} line has {service}")
    else:
        print(f"{line} returned status code {response.status_code}.")
```

In this code we checked if something had the value 200, if that was true then we printed some information. 

We'll write our own control flow in a moment but there's two things I want you to observe. 

Firstly, at the end of our condition we have a colon. That shows the end of our condition, then following that we indent 4 white spaces. 

This is to define a code block, essentually the code we want to run if the condition is true. 

Let's create a new cell and write some code the judge internet speed

*CREATE CELL*


**main.ipynb**
**CELL 15**
```python
speed = 300
```

So if the internet speed is above 1000, let's assume the units are megabytes per second, that is very fast. 

**main.ipynb**
**CELL 15**
```python
speed = 300

# NEW CODE
if speed > 1000:
    print("Very Fast")
```

If I run my code, nothing will happen

*RUN CELL*

However if there's binary choices we can add an else.

**main.ipynb**
**CELL 15**
```python
speed = 300

if speed > 1000:
    print("Very Fast")
else:
    print("Not very quick")
```

*RUN CELL*

Because the condition of our **if statement** didn't return true, the **else** executed. 

We didn't need to write a condition on the else, it's always going to be one or the other. 

If we need more nuance, we can add that in. 

I'm going to stack different conditions ontop of one another 

**main.ipynb**
**CELL 15**
```python
speed = 300

if speed > 1000:
    print("Very fast")
elif speed > 200:
    print("Fast")
elif speed > 100:
    print("Quick")
else:
    print("Not very quick")
```

The **else** becomes our catch all

*RUN CELL*

Also, notice even though one other could potentially return true, how we only have one output. 

We assess going down and once one condition is true, we run the code block which corresponds with that statement and then forget the rest.  

What goes between the **if** keyword and colon is Python so we can use multiple conditions if we like. 

I'll update my speed and create a new variable for being a special customer. 

**main.ipynb**
**CELL 15**
```python
# UPDATED CODE
speed = 1300
# NEW CODE
vip_customer = True

# UPDATED CODE
if speed > 1000 and vip_customer == True:
    # UPDATED CODE
    print("Premium user, very fast internet")
elif speed > 200:
    print("Fast")
elif speed > 100:
    print("Quick")
else:
    print("Not very quick")
```

### Task

I'm going to add some code to a new cell and I want you to try and use a series of if statements to write your own control flow. 

*CREATE CELL*

**main.ipynb**
**CELL 16**
```python
import datetime

current_month = datetime.datetime.now().month
print(current_month)
```

We import a bit of functionality from Python and all this does is print off the number of the month we're currently in. 

*RUN CELL*

I want you to spend around 5-10 minutes to write a little program which checks if it's January through to December and if it is prints a message that relates to you, it could be a message saying "Happy Birthday Mum" or "World Cup starts" I don't mind but play around, check every month and have a unique statement for each month.  

*BREAK*



## Lists

I want to move onto some more complicated data types. We'll start with lists. 

I implimented one earlier, it was our list of London tube lines. The syntax we used were square brackets.

*CREATE CELL*

**main.ipynb**
**CELL 17**
```python
cities = []
```

We want to keep related information in a list and one important thing to remember, the order of the list is what matters. 

Let's all add a few cities to our list. 

Even though the datatype is a list, the items or elements inside a list can be any other data type, even other lists but let's stick with strings. 

I'll just add some of the larger cities in Europe

**main.ipynb**
**CELL 17**
```python
# UPDATED CODE
cities = ["London", "Paris", "Berlin", "Edinburgh", "Madrid"]
```

We can print our list

**main.ipynb**
**CELL 17**
```python
# UPDATED CODE
cities = ["London", "Paris", "Berlin", "Edinburgh", "Madrid"]
print(cities)
```

Our variable again is just a reference to the collection of data

One common reason why lists are usful is the ability to pull out individual elements of a list and if there's one takeaway, remember that when dealing with software we count from 0. 

Let me show you what I mean. 

If I want to access the first element in the list, we use something called square bracket notation. We've said that the position of the elment is what's important when working with lists so to pull out London, we'd write some code like that. 

**main.ipynb**
**CELL 17**
```python
cities = ["London", "Paris", "Berlin", "Edinburgh", "Madrid"]
print(cities[0])
```

*RUN CODE*

So, square brackets and then a number. 

Because we start at zero, London is the element which is returned. 

To target Paris then, we'd pass 1.

**main.ipynb**
**CELL 17**
```python
cities = ["London", "Paris", "Berlin", "Edinburgh", "Madrid"]
print(cities[1])
```

*RUN CODE*

If we need to add an element to the list, there's a built in function called append.

**main.ipynb**
**CELL 17**
```python
cities = ["London", "Paris", "Berlin", "Edinburgh", "Madrid"]
# NEW CODE
cities.append("Oslo")
# UPDATED CODE
print(cities)
```

*RUN CODE*

Then we can update specific elements on a list as well. If I wanted to change "Oslo" to "Lisbon" we can. 

**main.ipynb**
**CELL 17**
```python
cities = ["London", "Paris", "Berlin", "Edinburgh", "Madrid"]
cities.append("Oslo")
print(cities)

# Oslo would now be in the 5th position
cities[5] = "Lisbon"
print(cities)
```

*RUN CODE*

Reassining the element inside a list is simply targetting an already existing element and assinging a new value. 

There's other common methods which are worth knowing which interact perdominatnly with lists.

Do we want to know how long our list is?

**main.ipynb**
**CELL 17**
```python
cities = ["London", "Paris", "Berlin", "Edinburgh", "Madrid"]
cities.append("Oslo")
print(cities)

# Oslo would now be in the 5th position
cities[5] = "Lisbon"
# UPDATED CODE
print(len(cities))
```

*RUN CELL*

Let's all create a list of flowers

*CREATE CELL*

We're at a point now where avenues start to open up. We're combing two data types, strings inside a list. 

**main.ipynb**
**CELL 18**
```python
flowers = ["Tulips", "Sunflowers", "Roses", "Daisies"]
```

Imagine this was a shopping cart, I can make statements like, "if the length of the cart is above 3 items, add complimentary 'orchids' to the list and make it all upper case, so it's brought to their attention"

**CELL 18**
```python
flowers = ["Tulips", "Sunflowers", "Roses", "Daisies"]
if len(flowers) > 3:
    flowers.append("Orchirds")
    flowers[4] = flowers[4].upper()

print(flowers)
```

*RUN CELL*

I knew how long my list was, in order to target the orchids but if I didn't I can always target -1

**main.ipynb**
**CELL 18**
```python
flowers = ["Tulips", "Sunflowers", "Roses", "Daisies"]
if len(flowers) > 3:
    flowers.append("Orchirds")
    # UPDATED CODE
    flowers[-1] = flowers[-1].upper()

print(flowers)
```

### Task

I want you to get hands on again, I've got a **list** with quite a few issues and I want you to write a some code to fix the issues.


*CREATE CELL*

**main.ipynb**
**CELL 19**
```python
continents = ["africa", "Africa", "north murica", "South America", "Antartica", "europe"]
```

I want you to copy this out and use some of the techniques we've seen and fix this list
- Some elements aren't title case
- Some have spelling mistakes
- Potentially missing one continent

Spend 5 or so minutes trying to fix this, you should be done when you can write a print statement and see the full correct list. 

**SOLUTION**
**main.ipynb**
```python
continents = ["africa", "Africa", "north murica", "South America", "Antartica", "europe"]
continents[0] = continents[0].title()
continents[2] = "North America"
continents[5] = continents[5].title()
continents.append("Australia")

print(continents)
```

## Loops

We're about the unmask the full potential of lists. 

In our TFL example we saw our first **loop**.

They're designed to interate over collections of data like lists and perform the same action on every item. 

For tfl the action was to pull information about the service of the line and we wanted to do that for every line in our list. 

Automating repetitive tasks makes coding readbale and much more easier to beug. Thinking back to the Zen of Python, that's no bad thing whatsoever. 

Loops are ubiquitous and most of the web uses them to construct different interfaces. 

I've found an example from VM02's site: https://news.virginmediao2.co.uk/news-views/

We can see different news articles. 

They're all styled consistently, each of them have a:
- date of the press release
- title text
- image

I can almost gaurentee behind the scenes there's a list of data. Not about flowers or continents but each item containing data about each news article, the:
- date
- title
- image
Then you loop over that list and for each one create a UI. 

Not only is everything unifom but it was have saved the developer a lot of time. 

Let's create a loop together

*CREATE CELL*


We'll start off with a list of devices. 

**main.ipynb**
**CELL 20**
```python
devices = ["Router", "TV Box", "Phone", "Smart Speaker"]
```

Then our for loop

**main.ipynb**
**CELL 20**
```python
devices = ["Router", "TV Box", "Phone", "Smart Speaker"]

# NEW CODE
for device in devices:
```

The keyword is 'for' and following that we need to choose the name of every item inside the list. 

Well for us our list has a pluralised name, 'devices' so it makes sense that every single item should be a singular 'device'. 

Because of that it's quite common to pluralise list names and then if your looping over that list use the singular. 

We don't have to though, but to complete the syntax it's `for` item name and then `in` followed by the name of the collection or list. 

We have a colon again which always means the beginning of a code block.

**main.ipynb**
**CELL 20**
```python
devices = ["Router", "TV Box", "Phone", "Smart Speaker"]

for device in devices:
    # NEW CODE
    print("Checking connection to:", device)
```

*RUN CELL*

All we're doing is going through the devices list, one at a time and executing the code block. 

On the first iteration of the loop, the string "Router" passes into the loop taking on the variable **device**, once the code block has completed, it'll restart but with "TV Box" instead.

Let's combine some more things

**main.ipynb**
**CELL 20**
```python
devices = ["Router", "TV Box", "Phone", "Smart Speaker"]
checked_count = 0  
vip_customer = False

for device in devices:
    print("Checking connection to:", device)
    checked_count += 1 

if checked_count >= 4:
    vip_customer = True

print("Total devices checked:", checked_count)
print("VIP status is:", vip_customer)
```

*RUN CELL*

I like this code, the `+=` sign adds and then assigns the value of the right to the variable on the left. 

The result is basically a counter for how many times this loop runs. 

Then if it runs four or more times we give the vip_customer variable the boolean value True.

By itself, fine, it doesn't do much, but integrated into a large code base it can be quite powerful. 

When you see different codebases, they are quite intimidating but look for the smaller pieces of code and things will be easier to digest. 

### Range

If we know we just want to loop a certain number of times, instead of over a list, that's doable

*CREATE CELL*

**main.ipynb**
**CELL 21**
```python
for i in range(5):
    print(i)
```

*RUN CELL*

range() again is a built in method that generates a sequence of numbers.

If we pass in one number, that value means the length. 

We count from 0 so it stops before 5. 

If we pass in two arguements though, things change. 

**main.ipynb**
**CELL 21**
```python
for i in range(2, 10):
    print(i)
```

*RUN CELL*

2 is the value at which we start
10 is the value we go up to but don't reach.

The final think regarding loops I'll show you is a third argument. 

**main.ipynb**
**CELL 21**
```python
# UPDATED CODE
for i in range(2, 10, 2):
    print(i)
```

The first two arguments are the same but the third argument stipulates to increments to get between the first around second. 

*RUN CELL*

Starting at 2, going up until but not inclusive of 10 in steps of 2. 

**main.ipynb**
**CELL 21**
```python
# UPDATED CODE
for i in range(2, 10, 3):
    print(i)
```

We'll take a break in a moment, but before that I've got two challenges. 

I want you to create a loop which will count down from 10 to 1, inclusive of both numbers and after one, print "Lift off"

If you do that or it feels too easy, there's a very common challenge for new developers called Fizz Buzz. 

You loop through numbers, 1 to 30 inclusive, and as you do if a number is divisable by 3 you print Fizz, if it's divisable by 5 you print Buzz, if it's divisable by 3 and 5 you print FizzBuzz. 


---

## 📘 Topic 7 — Dictionaries and JSON

We've just a couple more things to look at before we wrap up. 

Let's start with our final datatype today called **Dictionaries**

Potentially the most important data type, they store information in **key-value pairs** — like a contact book where each name maps to a phone number. 

They’re ideal for configurations, API responses, and structured data.  

Let's all create a dictionary together. 

*CREATE CELL*

We'll assign this dictionary to a variable let's just call ours 'myself' and we use curly braces

**main.ipynb**
**CELL 22**
```python
myself = {}
```

Our lists contained lots of different data and we accessed them by position. 

Dictionaries on the other hand we access through their name, so data always relates to a name or specifically a key.

Our first key will be name.

**main.ipynb**
**CELL 22**
```python
myself = {
    # NEW CODE
    "name":
}
```

Keys are always strings and we assign a value to a key, not with an equals sign but with a colon. following that colon we add any datatype as a value against that key. 

It makes sense to use a string, so add your name as a string as the value. 

**main.ipynb**
**CELL 22**
```python
myself = {
    # UPDATED CODE
    "name": "Emile"
}
```

If we then want to add more keys, we add a comma at the end of the value and go again. 

I'd like you to add a key for your age with an int value and also a key for your any cities you've lived in, as a list. I'll do the same.

**main.ipynb**
**CELL 22**
```python
myself = {
    "key": "Emile",
    "age": 34,
    "cities": ["London", "Wolverhampton", "Colchester"]
}
```

Now the question is how do we access that data.

We still use square bracket notation, like we did with lists but instead of the position, we provide the key name.

If I wanted to extract my age I'd target the variable customer, define square brackets and then the key for my age with is 'name'.

Let me do that. 

**main.ipynb**
**CELL 22**
```python
myself = {
    "key": "Emile",
    "age": 34,
    "cities": ["London", "Wolverhampton", "Colchester"]
}

print(myself["age"])
```

*RUN CELL*

Data often arrives in a dictionary like this and can be nested a few layers deep. 

If I wanted to pull out information about the cities I've lived in, in my print statement I'd swap the key of age to cities.

**main.ipynb**
**CELL 22**
```python
myself = {
    "key": "Emile",
    "age": 34,
    "cities": ["London", "Wolverhampton", "Colchester"]
}

print(myself["cities"])
```

But then if I specifically wanted to extract Wolverhampton, I'd see it's indexed at position 1 which I can tag onto the end of the print statement. 

**main.ipynb**
**CELL 22**
```python
**main.ipynb**
**CELL 22**
```python
myself = {
    "key": "Emile",
    "age": 34,
    "cities": ["London", "Wolverhampton", "Colchester"]
}

print(myself["cities"][1])
```

*RUN CELL*

All these different methods between teh datatypes fit together. I can append an item to the cities list if I moved somewhere new.

In a years time I'll be 35, that's fine.

**main.ipynb**
**CELL 22**
```python
myself = {
    "key": "Emile",
    "age": 34,
    "cities": ["London", "Wolverhampton", "Colchester"]
}

# NEW CODE
myself["age"] = myself["age"] + 1
print(myself["age"])
```

*RUN CELL*

On the right hand side of the assingment operator, `myself["age"]` basically references an integer, 34. I do a mathematical operation and then reassign that new value to the key of age. 

### Task

I've got another challenge now which incorporates most of what we've done today. 

There's a list of customers and each customer itself is a dictionary. 

I want you to write a small program which loops over each customer and basically identifies if they're eligable for a speed increase.

For that eligibility they must have been a customer from at least 2020 and currently have a speed lower than 200.

If they are eligable for a speed increase, just print the message from inside the loop saying the name is eligable. 

*CREATE CELL*

**mmain.ipynb**
**CELL 23**
```python
customers = [
    {
        "name": "Alex Turner",
        "age": 34,
        "member_since": 2019,
        "current_speed": 150,
        "devices": ["router", "TV box", "smartphone"]
    },
    {
        "name": "Priya Shah",
        "age": 28,
        "member_since": 2021,
        "current_speed": 150,
        "devices": ["router", "tablet"]
    },
    {
        "name": "Michael O'Connor",
        "age": 45,
        "member_since": 2017,
        "current_speed": 500,
        "devices": ["router", "laptop", "WiFi booster"]
    },
    {
        "name": "Sophie Williams",
        "age": 31,
        "member_since": 2016,
        "current_speed": 180,
        "devices": ["router", "games console"]
    }
]
```

**SOLUTION**


**mmain.ipynb**
**CELL 23**
```python
customers = [
    {
        "name": "Alex Turner",
        "age": 34,
        "member_since": 2019,
        "current_speed": 150,
        "devices": ["router", "TV box", "smartphone"]
    },
    {
        "name": "Priya Shah",
        "age": 28,
        "member_since": 2021,
        "current_speed": 150,
        "devices": ["router", "tablet"]
    },
    {
        "name": "Michael O'Connor",
        "age": 45,
        "member_since": 2017,
        "current_speed": 500,
        "devices": ["router", "laptop", "WiFi booster"]
    },
    {
        "name": "Sophie Williams",
        "age": 31,
        "member_since": 2016,
        "current_speed": 180,
        "devices": ["router", "games console"]
    }
]

for customer in customers:
    if customer["member_since"] <= 2020 and customer["current_speed"] < 200:
        print(f"{customer["name"]} is eligable for a speed increase")
```

---

## 🧮 Topic 8 — Functions

The last topic for today is going to be functions, we've been using functions but they've been built in, so let's create our own. 

Functions organise code into reusable blocks which is good for a few reasons.
- They improve readability and reduce repetition - there's a principle of DRY code, which stands for Do not Repeat Yourself
  - No only is it wasteful of time but also increases the chance for us to make mistakes
  - If we write functions to achieve commonly done tasks then to opportunity for mistakes is lower and we also have fewer places to debug when things go wrong

Let's stub out the basic syntax of a function together. 

*CREATE CELL*

**main.ipybn**
**CELL 24**
```python
def say_hello():
```


So we use the **def** keyword, give our function a name. Def is short for definition.

Following that there's some parenthesies and space for something called **parameters**. 

They're often referred to as arguments. We've used arguments before whether is was passing a string inside the parenthesies of a print function. 

Parameters are how a function internally refers to values which it recieves. 

They're important because they allow us to change how our function behaves when executed, by passing in different values. 

Finally just note the colon which signifies the corresponding code block.

I'm going to give this function a parameter called name. 

**main.ipybn**
**CELL 24**
```python
# UPDATED CODE
def say_hello(name):
```

Then I'm going to just use that parameter and print whatever's passed as part of an f string.

**main.ipybn**
**CELL 24**
```python
def say_hello(name):
    # NEW CODE
    print(f"Hello {name}")
```

That's our first function, now we can call it. 

**main.ipybn**
**CELL 24**
```python
def say_hello(name):
    print(f"Hello {name}")

say_hello("VMO2")
```

*RUN CELL*

So far so good. 

Most of the time we're not going to print information from functions, we'll actually want to generate new data and return that data to variables. 

If we can all remove the print statement and return the f-string instead

**main.ipynb**
**CELL 24**
```python
def say_hello(name):
    # UPDATED CODE
    return f"Hello {name}"

greeting = say_hello("VMO2 Function")

print(greeting)
```

*RUN CELL*

The output is similar but now when the function runs, we pass in the string "VMO2 Function" as an argument. 

The function takes that argument under the name parameter and returns the combined f string back to the function which we then assign to the greeting variable. 

A lot of reading and understanding software and being able to have those conversations is following a flow of data through a file and within different functions. 

I've got another funciton I'm going to copy onto the screen and I want to look through what's happening together. 

*CREATE CELL*

**main.ipynb**
**CELL 25**
```python
def monthly_bill(speed, is_vip):
    base_price = 40.0 
    if speed > 350:
        base_price += 10
    if is_vip == True:
        base_price -= 5  
    return base_price  

price = monthly_bill(400, True)

print(price)
```

*RUN CELL*

We've got our function called `monthly_bill` and there's room for 2 arguments:
1. speed
2. is_vip

When we run the function, `speed` takes the value 400 and `is_vip` takes the value True. 

We then actually define a variable inside the function called `base_price` of 40. 

Hopefully the Python code is fairly readbale to you but we can see, if the speed value is greater than 350, we add 10 to the base price. 

If `is_vip` is a truthy value we then take off 5. 

The two `if` statements are seperate to each other so both can run together which is why the price returns to us and printed is 45. 

As you'd expect, there's no built in Python function to do this, but whether we have 5 or 5 million customers, we could reuse this code to calculate all of their bills quickly and effectively. 

These functions do get quite complex. We started the day speaking about the Zen of Python and ensuring code is easy to navigate.

There is help we can provide in the form of Docstrings and TypeHints. 

Docstrings basically help us annotate functions or files with their intended purpose and type hints tell the user what data types the user of the function is expected to input and recieve. 

Let me copy over an example I've done earlier. 

**main.ipynb**
**CELL 25**
```python
def monthly_bill(speed: float, is_vip: bool) -> float:
    """
    Calculate the monthly bill based on internet speed and VIP status.

    Parameters:
    speed (int or float): The internet speed in Mbps.
    is_vip (bool): True if the customer is a VIP, False otherwise.

    Returns:
    float: The total monthly bill.
    """
    base_price = 40.0  
    if speed > 350:
        base_price += 10  
    if is_vip:
        base_price -= 5  
    return base_price  

price = monthly_bill(400, True)

print(price)
```

Notice that we've updated the parameters with a colon and then the data type which is expected. Also at the end of the parameters we've created a little arrow and written float. 

That's the data type which should be returned to the user. 

The obvious change is the large body of text at the top of the code block.

Three quotation marks to begin and end the DocString

It's information about what it recieves and outputs with a little detail about it's use. 

The very last thing I'll show you is how to utilise the DocString. You could be exposed to a large piece of software with lots of different functions. 

If they've been developed using DocStrings, even if you can't see where the function is define, use to built in method **hrlp()**


**main.ipynb**
**CELL 25**
```python
def monthly_bill(speed: float, is_vip: bool) -> float:
    """
    Calculate the monthly bill based on internet speed and VIP status.

    Parameters:
    speed (int or float): The internet speed in Mbps.
    is_vip (bool): True if the customer is a VIP, False otherwise.

    Returns:
    float: The total monthly bill.
    """
    base_price = 40.0  
    if speed > 350:
        base_price += 10  
    if is_vip:
        base_price -= 5  
    return base_price  

price = monthly_bill(400, True)

print(price)

help(monthly_bill)
```

*RUN CODE*

## Conclusion 

That's us done!

I hope you enjoyed your first taste of Python code this morning. 

We've looked at some of the different data types 
- Seen how to manipulate our scrpts with:
  - control flow
  - loops
  - functions


I've prepared some challenges, all based on what we've learnt today. They get harder as they go so if the first couple are easy, maybe jump ahead a bit. 

There is an accompanying solutions guide as well, if you're struggling, do look at the solutions. Reading code and understanding how it works is often just important as writing it. 

*SHARE*

- CHALLENGES: https://gist.github.com/emilesherrott/034f2c00058fb903f4df86ecd7f38254

- SOLUTIONS: https://gist.github.com/emilesherrott/f6c11b4894c79fe8509644aea49973e2


You're more than welcome to stay on the call, I'll be available to offer any help. 

Otherwise, feel free to stay, cameras off, or leave the call. But let's come back at 12:20 to wrap up the day and we'll talk about the next session. 


## Next Session

**ASK**
How did everyone get on?

**ASK**
Does anyone fancy sharing their screens and talking through some of their code?

Next session we'll be looking at:
- Some more conventions in Python, why we do things a certain way
- Saving data to files, so even after we close of programmes some data remains
- Looking at some more advanced functions, where we can pass in an unknown amount of arguments
- Then the paradim Python was built on, Object Orientated Programming which will be the big one, then seperating code over multiple folders and files. 









# END
---

## ✍️ Topic 9 — Python Style (PEP8) & Docstrings

I'm nearly done speaking for the day, there's just a few things I'd want to stress, especially for people relatively new to coding. 

### Why this matters
Clean, consistent code is easier to read, review, and maintain.  

Regardless of how experienced you are, clean code is readable code, which is good code. 

Development teams can be really large, in some cases working in seperate offices in different cities or even countries. With this in mind, it becomes really important to think about how we write our code so the way I may write code in London is the same as how my colleague may write code in Glasgow. 

There's a few style-guides which help Python developers say aligned on some of these topics:

#### PEP8
Python’s **PEP8 (Python's Enhanced Proposal 8)** defines formatting rules (naming, spacing, indentation) which aims to make everyones code consistent with each other.  

Perhaps the most important aspect of that right now is the indentation we have for our code blocks. We've been using 4 spaces, whether that's following an **if expression**, **loop decleration** or **function**

You'd also notice that when I've been naming variables or functions, if the name spans two words I've been connected those two names with an underscore and everything is lower case. 

This is called **snake_case** and is how Python developers name items. Other languages have different conventions.

There's: 
- **camcelCase**
- **kebab-case**
- **PascalCase**

Python developers are consistent, so if I'm talking to a colleague and say, you need to run the function, **say hello**, there doesn't need to be a follow up as to whether things are capitalised or not



#### Docstrings
Further to this we can help other people in our team using docstrings

**Docstrings** describe what a function does — they serve as built-in documentation.


**main.ipynb**
```python
def monthly_bill(speed, is_vip):
    """
    Calculate the monthly bill based on internet speed and VIP status.

    Parameters:
    speed (int or float): The internet speed in Mbps.
    is_vip (bool): True if the customer is a VIP, False otherwise.

    Returns:
    float: The total monthly bill.
    """
    base_price = 40.0  
    if speed > 350:
        base_price += 10  
    if is_vip:
        base_price -= 5  
    return base_price  

price = monthly_bill(400, True)

print(price)
```

This is the same function as before but with a **Docstring** added, it doesn't change how the function runs in any capacity. We have though noted:
- what the function does
- its parameters
- it's return value

We can take this one final step further and add something called **type annotation**, this gives hints about expected data types, defined directly on the function.

**main.ipynb**
```python
# So we hint that the 'speed' parameter to be given as an argument with the datatype 'float'
# And that the 'is_vip' parameter to be given as an argument with the datatype 'bool'
# Finally the expected return type will also be a float, denotated by '-> float:'
def monthly_bill(speed: float, is_vip: bool) -> float:
    """
    Calculate the monthly bill based on internet speed and VIP status.

    Parameters:
    speed (int or float): The internet speed in Mbps.
    is_vip (bool): True if the customer is a VIP, False otherwise.

    Returns:
    float: The total monthly bill.
    """
    base_price = 40.0  
    if speed > 350:
        base_price += 10  
    if is_vip:
        base_price -= 5  
    return base_price  

price = monthly_bill(400, True)

print(price)
```

These are just **hints**, nothing will break if I pass an **integer** instead of a **float** but it can make collaberation much smoother, especially when functions get more complicated


If this function however, wanted to capitalise a **string** and we passed in a **float** it would then break but not due to the use of **type annotation**, that would be a **type error**

That's us done! 

I hope you enjoyed your first taste of Python code with me.

We'll build on this and layer in some more complexity in the next session. 

As I mentioned at the start, the best way to develop is to do so I've got a list of challenges for you to do in Python.

I'll be here to help if you have any issues, my solutions are also available but that doesn't mean they're the best, I'd encourage you to get stuck and really think about how you can change code before potentially looking at the answer.



---

I've also created a cheat sheet of what we've convered today which hopefully serves you well. 



Next up — **Session 2: Intermediate Applications**, where we’ll explore **file handling**, **packages**, and **classes** for building scalable programs.









# OTHER

## JSON
Refering back to the TFL API, we recieved data as JSON

JSON, or JavaScript Object Notation, is the format commonly used to send data across the internet and if we have a Python application which needs to send data anywhere then converting from **Python dictionaries** to **JSON** is something we'd be doing often. 

Previously we've **parsed** or converted JSON to Python, now we're going to **serialise** or turn Python to JSON. 

**main.ipynb**
```python
import json  # built-in module for working with JSON data

# A dictionary representing a customer record
customer = {
    "name": "Alex",
    "services": ["Broadband", "TV"],
    "speed": 500,
    "address": {"city": "London", "postcode": "E1 6AN"}  # nested dictionary
}

json_data = json.dumps(customer, indent=4)
# json.dumps() converts a Python dictionary into a JSON-formatted string
# indent=4 makes the JSON prettier with indentation of 4 spaces per level of indentation
print(json_data)
```

*RUN CELL*

If we execute the code you'll see the output looks very similar to our original dictionary. That's no accident, the main thing to know is in the output:
- **lists** are now referred to as  **JSON arrays**
- **dictionaries** are now **JSON objects**

We're not going to look at this but if we wanted to send that data to a server across the globe, it's now in a format which could process that request. 

Let's parse some more JSON now

**main.ipynb**
```python
import json

# Example JSON string (as you might receive from a web API)
json_data = '{"name": "Alex", "speed": 500, "services": ["Broadband", "TV"]}'

# json.loads() converts a JSON string into a Python dictionary
loaded_customer = json.loads(json_data)

# Accessing data using dictionary keys
print("Customer name:", loaded_customer["name"])
print("Customer services:", loaded_customer["services"])
```

For anyone with a good memory, you may notice that earlier we parsed JSON from the TFL API using `response.json()`, now we use **json.loads**, the difference is that the `.json()` functionality came from our **import requests** and is used for parsing JSON arriving from a WebAPI. Functionally they behave the same. 

---



NOTES:

UPDATE SLIDEE

Start off by saying aim of the day is to understand some simple python programmes and then hopefully come on to writing programme

Close down agent on right hand side of codespace

When talking about tfl, acknowledge that they won't understand what the program does, say "I'm giving you a big picture understand in the first instance" same when referring to booleans

AFTER SLIDE 2 TALKS ABOUT TFL TOO QUICKY

Not able to type in codespaces, try using chrome

After talking about access to vmo2 systems, say I've had a play around with a public alternative 
- then paste completed code
- run it
- highlight the individual parts
  - highlight lists - "these are the lines we care about"
  - highlight for loop - "this is where we iterate over each tube line in the line and pull in all the data
  - highlight the sequare bracket notation for service variable - "this is where we're pulling out only the information we care about"
  - hightlight the final print statement - "this is where we output that data"


  - tell people when to code or not when to code
  - change language from imporve as a developer, to imporve awareness (course is to empower people as to better conversations)



  ## Other

  **REVISIT**
**DICTIONARIES**
**FUNCTIONS**
**PEP 8**
**CREATE DOCUMENT FOR CHALLENGES**



**main.ipynb**
```python
# Example of different data types in Python

customer_id = 101                  # int (whole number)
customer_name = "Maurice Moss"     # str (text string)
is_vip = True                      # bool (True/False)
broadband_speed = 500.5            # float (decimal number)
packages = ["Broadband", "Mobile", "TV"]  # list (ordered collection)
account_balance = None             # NoneType (represents 'nothing' or 'no value')

print("Customer Name:", customer_name)
print("Data Types:", type(customer_id), type(is_vip), type(packages))
```

*RUN CELL*

At the bottom we can see the data types, **class** is how these data types are constructed - this goes into the inner workings of Python which we'll look at next session. 
