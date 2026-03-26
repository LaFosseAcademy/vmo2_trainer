
# Advanced Python — Day 3

## What Is an API? (Trainer Notes)

**Target delivery time:** ~ 1 Day  
**Purpose:** Build a clear, non-technical-first understanding of APIs before introducing HTTP, requests, or frameworks.  
**Trainer mindset:** Keep this conceptual and concrete. If learners understand *why* APIs exist, the technical details land easily later.

---

### Learning Outcomes
By the end of this section, learners will be able to:
- Explain what an API is using everyday language and analogies.
- Describe why APIs exist and what problems they solve.
- Explain the client–server relationship.
- Describe the request–response cycle at a high level.
- Recognise common data formats such as JSON and XML.
- Identify real-world examples of APIs they already use.

---
# Pre-Training

Load Slidee **Day 3**


# Training Session

`SLIDE 1`


Hello, good morning again, I hope you've all had a good afternoon and evening yesterday. The topics we're going to be looking at over the next couple of days are going to be about receiving information from external sources. 

So far, all the data we've been working with or manipulating has been defined from inside our application, we've:
- written our own Python data and stored them to variables
- or we've created mock data and stored it in a file ourselves.

For those who weren't on the first part of the training, don't worry, either today or tomorrow we'll definitely get to write and read from files. 

### What Is an API?

The predominant way we're going to receive information though, is going to be throgugh what's called an API. 

It's an acronym, if you haven't heard about them already, you're going to start hearing about them all the time in many different contexts. 


### Plain-English Definition
So what is an API?

An API (or Application Programming Interface) is usually referred to, as a **contract**, a contract that allows one piece of software to talk to another in a controlled way.

An API is useful when we have one system or computer, which needs asks another system to do something — without needing to know how it works internally.

Basically an API is there to expose functionality. 

There's lots of different types of APIs, our browsers often have lots of different apis which can reveal functionality which exposes:
- information from the computers battery
- or your geolocation

You may have seen it, an example I've seen would be if I'm trying to download a large file onto my compter and I get a warning saying your battery is low, please plug in a charger or some type of warning.

Equally, if I'm trying to watch American TV, without a VPN Google will know I'm not in the USA.

These are APIs, they expose functionality and information in a consistent way, in those cases, between my computer and my browser.

The most common type people will be familiar with are WebAPIs. 

Jeff Bezoz is often suggested to have caused the wave of API adoption with Amazon. 

- https://tailcall.run/blog/api-strategy/
*SCROLL DOWN*

What we can see is Amazon's big mandate in 2002, the gist of it is that all the different teams in Amazon must expose data through APIs and no direct connection to a database. 

The overarching goal was to force Amazon to operate as a set of independant services. 

At the bottom of this picture it says **No exceptions**, the legend is that the memo ended, essentially saying anyone who doesn't follow these rules will be sacked.

Stepping back a moment, API's are used by every type of business these days, regardless of size. If I want to see the weather, I'll be using an API. If I want to see the TV schedule for the Winter Olympics, I'll be using an API. 

This gets down to the nitty gritty of how the internet works as a whole. 

I want to show you a website: https://www.submarinecablemap.com/

*Click*: https://www.submarinecablemap.com/

What we're seeing here are the underwater cables, this is the infrastructure which accomodates around 98% of internet traffic. 

If you're streaming an American Football match on Netflix, those data packets travel under the Atlantic ocean and treverse the internet to arrive on your television or computer. 

If you're sending an email to family in Australia, the same thing. It's these cables which connect us globally. 

`SLIDE 2`

What we're seeing on the screen now is one of those cables. Really important pieces of infrastructure. 

Interestingly many financial institutions deliberately place their offices close to where major undersea cables come ashore in order to minimise latency. 

Latency is the time it takes for internet signals to travel through a network, and when it comes to financial trading, being able to react to international market changes are really important. 

You may have heard different news outlets talking about Russian submarines and the risk in the North Atlantic, a lot of that stems around these cables and if they're cut, the ability for Europen countries to communicate with the US would be heavily restricted and there's obviousl consequences. 

So these if these cables are like the roads which connect us, we need to talk about TCP, IP and HTTP. 

`SLIDE 3`

We can compare the way data travels around the world and the protocols used, similar to how one may send a letter. 

The first thing neccessary to send a letter from Manchester to London are the roads which connect the two cities - they're like the underwater internet cables. 

Then the delivery mechanism is TCP (Transmission Control Protocol) that's like our postal worker, they makes sure the data arrives in order without any loss and confirms it's arrived.

IP or (Internet Protocol) is similar to an addressing system. Where does this data need to get to.

Finally HTTP (or HyperText Transfer Protocol) is the language the letter is written in. 

If I'm recieving a letter from friends in Manchester, that letter would be written in English - that's similar to HTTP, it's a manner in which computers expect to send a recieve data packages across the web. 

It's this underlying technology which allows us to recieve and sent data around the globe. 


---

`SLIDE 4`

So if the Post Office is how the internet works, an API is there to determine what the letter contains or what information is passed in each direction. 

For this we'll pivot to another analogy and the most common one, is that of ordering food at a restuarant. 

If we want to order food from a restuarant there's some limitations in place. 

Conventially, we're not allowed to go into the kitchen and speak to the chef directly to order sushi. Especially if we're at an Italian restaurant. 

We have a menu which we use to see what the options are. 

Then we speak to a waiter which is like our API.

It's the API which tells us what's available, what the prices are. 

Then the API or waiter goes into the kitchen and tells the chef what we want and after a short wait, the waiter the waiter will return with what looks like plain pasta. 

Within this analogy
- The customer, is a client or computer making a request information
- Waiter is the programme which reveals what information or data is available
- The API takes a request and sends it to another computer somewhere else in the world
- That computer processes the request
- Sends a response

That response is often data, information about a battery, our the TFL tube lines or the weather in Cornwall 

`SLIDE 5`

---

### Why APIs Exist

The reasons APIs are so popular are because they allow systems to:
- Evolve independently
  - APIs can be focused so in a banking system for example, there maybe an API which soley deals with sending emails to customers when terms and conditions change 
  - That allows other APIs which manage the sending and recieving of money to work independently from other systems
- Share data safely
  - When people programme APIs they control what data is sent so we expose only what we intend to
  - We can also choose who has access to that information 

---

### Client–Server Relationship

We describe all of these actions as a **Client Server relationship**

- Client asks for data or action
- Server owns data and decides what to return

---

### Request–Response Cycle

That's coupled with the **request / response cycle**. We used an API to make a request, maybe it's for data, potentially a request to try and login.

If my work give me a new computer, and I log in to check my emails for the first time, I'm making a request and that request contains data about my email and password, the response I get is the data of all my emails in my inbox. 

When I go to look at the news, the same thing happens. My computer makes a request to an API which returns the news.

1. Client sends request  
2. Server processes that request
3. Server sends response  

---

Let me show you an API request now

*IN TERMINAL RUN:* `curl https://catfact.ninja/fact`

The first part of this command I've written is **curl**. Curl stands for **client url** and it basically allows me to send or recieve data using urls. 

It's made a request to receive or **GET** data from a specific end point using **HTTP**. We'll eventually have to make these requests in Python but this command is essentially saying. 

"Return information from catfact.ninja/fact" and then we have this response displayed. 

Let me make another request

*IN TERMINAL RUN:* `curl https://catfact.ninja/breeds`

What we can see is now data being returned about the different breeds of cats. 

We're still trying to request data but we're now trying to request data from a different endpoint and we get a different response as a result. 

`SLIDE 6`

So my computer, **the client** makes a request to the endpoint and that endpoint is associated with a certain response which is sent back to me. 

There's a few things also happening under the hood. 

The type of request is called a **GET** request, that's specifically to retrieve or **get** information and then my response has come through with a **status code** of 200 which means whatever you've tried to do, you've done successfully. 

Let's talk through both of these things one at a time. 

It's often the case, that the main purpose of a request isn't to retrieve information, a lot of the time we want to post it. 

`SLIDE 7`

A lot of the internet is comprised of sending data:
- Sharing images online
- Submitting an insurance form

For this we don't specifically want to **GET** data but we **POST** data.

In this case a **username** and **password**. 

If you're posting a tweet, the same thing applies and we'll also go through the **request / response** cycle give us some information about the action. 

The status code **201** means you've successfully created something. 

These numbers are giving information about the request, information we can use in a progammatic way to choose what happens next. 

We often link this in to Python with **control flow** or **if / else statements**: "If this request returns a status code of 200, render this page, if it returns a status code of 404... do this instead"

### Data Formats

On thing which is relatively consistent between these requests is way the data is returned. 

It takes a format called JSON which stands for JavaScript Object Notation, most of us have seen it before and it looks very similar to a Python dictionary. 

*IN TERMINAL MAKE REQUEST:* `curl https://catfact.ninja/fact`


### JSON (Most Common)

JSON is the most common way data is shared across the internet. The format is familiar to lots of developers and it's considered lightweight so it can traverse the internet quickly.

**main.py**
```json
{
  "city": "London",
  "temperature": 18,
  "condition": "Cloudy"
}
```

### XML (Older)

*IN TERMINAL MAKE REQUEST:* `curl https://httpbin.org/xml`

Another approach way data is sent is XML. 

XML stands for **eXtensible Markup Language** and looks a llot like other markup languages like HTML if anyone has done frontend development. 

XML is considered a bit of an older, dated approach to send data. 

All data is treated like strings and people judge it to be harder to read. However it does handle complex data structures a little better. 

```xml
<weather>
  <city>London</city>
  <temperature>18</temperature>
  <condition>Cloudy</condition>
</weather>
```

---

## Real-World Examples

I just want to reiterate how much of our lives, undereath the hood depend on APIs
- It's estimate around 80-90% of internet traffic is API-based communication between services:
  - mobile apps calling servers
  - websites loading data
- And over 90% of devlelopers use APIs in their application
- Most modern apps have between 10-30 apis. 

---


*BREAK*

We'll get to write out some code very soon



Before this, I just want to talk a little more about HTTP

It's the **set of rules** that defines how clients and servers talk to each other over the web.


HTTP is:
- Ubiquitous (every device supports it)
- Stateless ( which means each request stands alone and a previous request/response cycle doesn't impact further requests)

And our APIs, use HTTP to communicate that data between clients and servers. 

---

Within this training we'll be consuming APIs rather than building our own


We've taken a quick look at two different HTTP methods (**GET & POST**)

And these methods describe **intent**, not implementation.

They answer the question:
“What do I want to do with this resource?”

---

### Common HTTP Methods

`SLIDE 8`

- **GET** — retrieve data  
- **POST** — create something new  
- **PUT** — replace something  
- **PATCH** — update part of something  
- **DELETE** — remove something  

The method is the *verb* of the request.

 Let's actually start using GitHub Codespaces now. 

We can, if we wanted to, write some really complicated code which will be able to make a request to an API.

If you remember back to OOP yesterday, we spoke about **abstraction**, hiding the details of a more complex implimentation. We can do this with our requests as well. 

The `requests` library, which we can import, does a lot of the heavy lifting for us:
- Wraps HTTP in a clean Python interface
  - Underneath the hood Python handles the **sockets**, which refers to a connection being open and closed
  - Decoding any responses
- What we want to do is think about GETting data or POSTing data, not the underlying functionality. 

---

**main.py**
```python
import requests
```

*INSTALLATION MAY ALREADY BE DONE IN MANAGED ENVIRONMENTS. DON'T DETAIL THE SESSION ON TOOLING*


---

## Making Your First Request

### Basic GET Request

**main.py**
```python
import requests

response = requests.get("https://catfact.ninja/fact")
```

Explain:
- `requests.get` triggers a HTTP GET request to the location we pass as the argument
- The return value is a **response object**
- No data has been processed yet

---

### The Response Object

**main.py**
```python
import requests

response = requests.get("https://catfact.ninja/fact")

print(type(response))
```


- *RUN* `python main.py`

  
Explain:
- The response contains *everything* about the server’s reply
- Data, status, headers, metadata


We can think of the response object as the envelope — not just the letter.

---


So how do we go about handling the **response**, we're not yet in the position to see the cat fact. 

### Status Codes First
We always check *what happened* before using data. This will be consistent. 

**main.py**
```python
import requests

response = requests.get("https://catfact.ninja/fact")

# NEW CODE
print(response.status_code)
```

- *RUN* `python main.py`

Explain:
- `200` usually means success
- Other codes, especially for a GET request often mean something went wrong (or different)


It's important to never assume success we'll be successful.

---


### Reading Text Content

**main.py**
```python
import requests

response = requests.get("https://catfact.ninja/fact")

print(response.text)
```

- *RUN* `python main.py`

This prints exactly what the server sent, before Python tries to interpret or structure it. 

It can be helpful to look at the raw text when a request fails unexpectedly or the response isn't what you expected. 

We also may not know what type of data the response is going to be either:
- JSON
- XML
- HTML

So it's useful to get a glimpse. 

To me it looks like this response has come through as JSON, I assume this firstly because it's the format the vast majority of data is sent and also we can see the curly braces and key's as strings. 

If it looks like a Python dictionary then it's probably JSON. 

---

### Parsing JSON Responses

Similar to our session when we read and wrote to different files, the first step is always converting the data into Python


**main.py**
```python
import requests

response = requests.get("https://catfact.ninja/fact")

# NEW CODE
data = response.json()
print(data)
```

- *RUN* `python main.py`

**response.json()** will take a JSON object and parse it to Python so we can work with it further. If it's not valid JSON that this script will fail. 

**ASK**
“What Python datatype do you expect `data` to be?”

**ANSWER**
Converts from JSON to a Python Dictionary

**main.py**
```python
import requests

response = requests.get("https://catfact.ninja/fact")

data = response.json()

# UPDATED CODE
print(type(data))
```

- *RUN* `python main.py`



---

## A Safe Pattern for Requests

### Recommended Minimal Pattern

Let's impliment a safer alternative to the script, with soem control flow. 

**main.py**
```python
import requests

response = requests.get("https://catfact.ninja/fact")

if response.status_code == 200:
    data = response.json()
    print(data)
else:
    print("Request failed:", response.status_code)
```

- *RUN* `python main.py`

Hopefully this is a little clearer, especially if the status code, isn't 200. We can log it and actually get some information as to why things are going wrong. 


---


`SLIDE 9`

Internet infrastructure is fairly resiliant. Outages do happen though. 

I don't know where the server is for **catfact**, it could be down the road or across the ocean. I can't gauruntee that we recieve the information we hope back.  

These things do happen and we need to be ready to handle these issues. 

**ASK**
In our response though we can see there's information saying **Response 200**, what does that mean?

**ANSWER**
Our request resolved well. 

With this in place we can now progress with confidence that we can convert the JSON response to Python. 


So if we're succesful let's proceed with doing something the the JSON we consume


We mow have access to that infomraiton in Python as a dictionary, we know how to manipuate that information now. 

### Challenge

I want you to spend 5 minutes and I'd like you to define a variable called **fact** which extracts the information held on the key of **fact** in our dictionary. 

Then I'd like you to use that **fact** variable and print an **f string** with a sentence like: *"An interesting fact about cats is: {fact}"*

**SOLUTION**
**main.py**
```python
import requests

response = requests.get("https://catfact.ninja/fact")

if response.status_code == 200:
    data = response.json()
    fact = data["fact"]
    print(f"An interesting fact about cats is: {fact}")
else:
    print("Request failed")
```

- *RUN* `python main.py`

Let's work with another endpoint with more complicated data being returned. 

**main.py**
```python
import requests

# NEW ENDPOINT
response = requests.get("https://catfact.ninja/breeds")

if response.status_code == 200:
    # CONVERT FROM JSON TO PYTHON
    data = response.json()
    # PRINT DATA
    print(data)
else:
    print("Request failed")
```

- *RUN* `python main.py`

So we've got a lot more data now. 

The data type is a dictionary, I can tell because of the opening curly brace `{`

My objective is to display a series of strings, like:
*"This Abyssinian cat is from Ethiopia country and has a short coat"* 

The issue is how to use Python to take those actions on this data

I can see this information exists within the **dictionary** on the key of **data**.

I can pull out values from keys as we would any other data in Python

**main.py**
```python
import requests

response = requests.get("https://catfact.ninja/breeds")

if response.status_code == 200:
    data = response.json()
    # NEW CODE
    data_list = data["data"]
    # UPDATED CODE
    print(data_list)
else:
    print("Request failed")
```

- *RUN* `python main.py`

Now I have access to the **list**. 

Each item in the list looks like another dictionary and I know I can target elements in a list by their indexed position. 

**main.py**
```python
import requests

response = requests.get("https://catfact.ninja/breeds")

if response.status_code == 200:
    data = response.json()
    data_list = data["data"]
    # UPDATED CODE
    print(data_list[0])
else:
    print("Request failed")
```

- *RUN* `python main.py`

Perhaps you can tell the direction of travel we're headed right now. 

I'll show you one more thing before I set you off. 

So for one cat I can pull out the data values by their keys and return a relatively nice message about the cat.

**main.py**
```python
import requests

response = requests.get("https://catfact.ninja/breeds")

if response.status_code == 200:
    data = response.json()
    data_list = data["data"]
    # NEW CODE
    single_cat = data_list[0]
    # NEW CODE
    print(f"The cat breed {single_cat["breed"]} comes from {single_cat["country"]} and has a {single_cat["pattern"]} {single_cat["coat"]} coat.")
else:
    print("Request failed")
```

- *RUN* `python main.py`

The final thing I'll tidy up is just the issue I have with "Ticked" and "Short", those shouldn't be title case. Perhaps my English teacher would tell me I've got a poor grasp of the language but I'll use a string method just to make those lower case. 

**main.py**
```python
import requests

response = requests.get("https://catfact.ninja/breeds")

if response.status_code == 200:
    data = response.json()
    data_list = data["data"]
    single_cat = data_list[0]
    # UPDATED CODE
    print(f"The cat breed {single_cat["breed"]} comes from {single_cat["country"]} and has a {single_cat["pattern"].lower()} {single_cat["coat"].lower()} coat.")
else:
    print("Request failed")
```

- *RUN* `python main.py`

### Challenge
From this starting point, I want you to try and loop through our `data_list` and print a string for each cat using the f-string we've written together.


**SOLUTION**
**main.py**
```python
import requests

response = requests.get("https://catfact.ninja/breeds")

if response.status_code == 200:
    data = response.json()
    data_list = data["data"]
    # NEW CODE
    for single_cat in data_list:
        print(f"The cat breed {single_cat["breed"]} comes from {single_cat["country"]} and has a {single_cat["pattern"].lower()} {single_cat["coat"].lower()} coat.")
else:
    print("Request failed")
```
---

One thing we've not touched upon but is worth highlighting is that the way the data is sent, that's both:
- whether its sent as JSON or XML
- and also how that data looks, the keys, the datatype of the values

It shouldn't and they don't change very often. 

We ought to be in the position that if we were to revisit this API in 6 months time, they'll be an expectation that if we hit the /breeds endpoint, the data will still have a key of **data**, which will hold a list of dictionaries and in each dictionary, we'll have information on the keys:
- **breed**
- **country**
- **pattern**
- etc.. 


*BREAK*

## RESTful Routing

The way APIs are structured does vary quite a lot

Each approach tries to have a sensible design regarding how to reach certain data. 

We've seen our current endpoint for cats looks like this:


`SLIDE 10`

### Endpoint Breakdown

If we look at this endpoint there's a few features to acknowledge

- Firstly the verb is **GET** meaning we're trying to retrieve information
- The next part is the protocol HTTPS
  - We've discussed that this is the shared language which both my computer and the server which catfact.ninja runs 
- Then we have the Domain
  - This is designed to be a human friendly name which people can recognise
    - bbc.co.uk
    - netflix.com 
    - amazon.com 
  - Whenever we make a request, a Domain Name System converts that to an IP address
  - It's that IP address which is basically the location of the computer which hosts the API
- Finally there's the resource **"breeds"**
  - This is the information we specifically want from the API
  - We've seen before we can replace **breeds** with **fact** and it'll return different information to us. 

The **protocol** and **domain** will often stay the same, everything else is likely to change dependant on the request. 

If I want to target one specific breed of cat ordinarilly I should be able to extend the endpoint to something like this. 

`SLIDE 11`

This is hinting towards one of the most common API design patterns called RESTful Routes. 

APIs should be an often are focused on certain resources, it's also to everyone's benefit that there's a clear and structured way to interact with those resources. 

`SLIDE 12`

This table here shows the most prominent RESTful routes. 

#### Index

The most common route and the one we've used ourselves is the **index** route

The HTTP Method or verb is **GET** and the endpoint is pluralised and the action we expect is to return all breeds which is what we've seen. 

#### Show

The next route is called **show**, it also used a **GET** method and the main difference is the endpoint has changed. We've become more specific with our request to target a single breed and as we can see the desire is to reveal information about a single cat breed. 

#### Create

Underneath we have **create**, this route is for adding new data to an API or database. 

We can see it now uses a **POST** method in order to send data, but the endpoint is the same as our **index** route. 

The differentiating factor is what we're trying to do, send or receive. 

#### Update

**Update** uses the HTTP method **patch** and needs a specific cat breed in the endpoint. 

Whether we have the **cat name** or not in the endpoint, really depends specifically, if we're targetting an individual cat, already defined in the data, as part of the request

#### Destroy

This leads us onto **destroy**

This one uses the HTTP method **delete** and also targets a specific cat breed in the endpoint. 

This enables the use of fairly similar endpoints, but the action we take is dictated by the method. 


To **show** a cat or **update, delete** by it's very nature suggests we need to know what the cat is in the first place. 

However listing all cats or creating a cat does not. 

I can show you practically how the **index** and **show** routes often appear functionally. 

*CLICK* https://www.o2.co.uk/shop/brand/apple?cnd=new

So this site an returning the response from an **index** request, showing all the Apple products available and a little bit of information on all of them. 

I'd ask you to see the url, at the end we can see **apple**, that's the resource we're seeing information about now.

*CLICK ON ONE PRODUCT*

Now the response from the **show** route is being displayed. Information about one product, but there's a lot more information about that product. 

One of the reasons why these RESTful routes like **index** and **show** are well known, is firstly because if I  were to leave LaFosse and join the team which created this site now, I'd understand the architectural pattern which is being used and that helps everybody. 

But also there's a very real cost to sending more information that what's necessary. There's far more information being displayed in the **show** route, because we've clicked on it, we've suggested we're interested in the product. 

If we go back a page.

*GO BACK*

It's to O2's advantage to share smaller piecies of information:
- firstly it looks a little more manangable
- but it's much quicker for our browser, to recieve smaller pieces of information to build this UI
- it'll also cost less, if O2 use a cloud service like AWS or Azure to host their API, they'll often charge per GB to send data out




### Parameters

One of the things you may notice in the Url is something called query parameters. 

This is another approach to seperating out resources via an API.

`SLIDE 13`

They're used to modify or refine a request without changing which resource you're accessing. 

We can think of endpoints including both the **path** and **query parameters**

- The **path** is what you want
- The **query parameters** is how you want it

This example is suggesting we want to receive information about cat breeds, but specifically some the second page of data and a maximum of 25 cats. 

The **ampersand** **&** seperates two query parameters

### Documentation

The main thing to acknowledge though is there's no getting around the fact that when you're dealing with an API, you can hope for RESTful routing which gives you a sense of how APIs are structured but what you really have to do, and it's important to say a lot of developers don't enjoy doing this, is reading the documentation the creators of APIs write so you understanding how to use it.

---

## Status Codes

Following every request as we've seen there's status codes returned to us. 

They as we've said give information about responses and are used by developers to react to different situations.

They are part of every HTTP response.

---

I'd like to show you another cat themed page which relates to HTTP status codes. 

*CLICK THE LINK*: https://http.cat/ 

### Common Status Code Groups

- **2xx** — indicate success  
- **4xx** — inidcate a client error  
- **5xx** — indicate a server error  

“2 means ‘you’re good’. 4 means ‘you messed up’. 5 means ‘we messed up’.”

The 100's and 300's are less common to see but:
- 100 range means informational
- 300 means redirection

---

### Common Examples

The most common ones you'll see are:

- `200 OK` — success  
- `201 Created` — resource created  
- `400 Bad Request` — invalid input, imagine you're writing a tweet and haven't added any text  
- `401 Unauthorized` — missing/invalid auth, logging in without a username or email entered
- `404 Not Found` — resource doesn’t exist  
- `500 Internal Server Error` — server failure  

---

These things matter because they're used heavily to:
- Drive client behaviour, if a browser receives a 401, suggesting you've not logged in, how do we handle that logic:
  - do we block future attemps
  - or send them an email to provide a new password
  - depending on whether you work for a bank where security is crucial or if you made software for a local village group where there was no senstive data being kept, just how well someone's prize marrow is doing - you're response to a 401 status code would be different. 

Beyond that though, it makes APIs predictable and there's enough technical confusion in tech, without every API having it's own process to indicate success or failure. 

---

## Bringing It All Together

A full request conceptually includes:
- Method (what you want to do)
- URL / endpoint (what you’re acting on)
- Query parameters (how you want it filtered)
- Headers (context and permissions) which we've not looked at yet. 

---

## Activity (10–15 mins)

### Part 1 — Decode URLs
Given the following URLs, identify:
- Endpoint
- Query parameters
- What the request is likely doing

`SLIDE 14`

---

### Part 2 — Design Endpoints

1. Pick a domain (e.g. library, shop, service desk).
2. Design endpoints for:
   - Listing items
   - Getting one item
   - Creating a new item
   - Deleting an item

Do this on GitHub Codespaces and make a fictional GET request to it

`SLIDE 15`

---

## Wrap-up (2 mins)

Reinforce:
- HTTP is about intent and structure
- Methods are verbs, endpoints are nouns
- Status codes tell you what happened
- APIs become predictable when HTTP is used well


---







### Introduction to Postman

We can see there's quite a few complexitites to dealing with API's and all the different requests which may or may not be possible to create. 

Fortunatunatly there are several tools which are designed to make ths process a little easier and I want to show you one of them. 

It's called **Postman**


Developers used it to test api's quickly and explore unfamiliar endpoints. 

If you're a backend developer and building APIs yourself, it's also really helpful to test, if a request is made to a certain endpoint, the data you expect to be returned is returned. 

Let me share the link with you

*CLICK LINK:* https://www.postman.com/

Then click on the button to create a free account

Once you've done that click on:
- Workspaces
- Blank Workspace
- Name: Countries
  - Leave the rest blank and create


Now we're basically in a position to make lots of API requests and inspect the data which comes back

I want to introduce you to a new API

RESTcountries. 

I should apologise as well.

The vast majority of APIs in the world are either private or paid for and the free, publically available ones are generally quite weird or they don't conform the REST principles.

Let me share the link with you. 

https://restcountries.com/

What we're seeing is the documentation, this is what I mentioned people don't enjoy reading.

I can see though, it says *Get country by name* so I'm just going to copy that endpoint and make a request to it. 

### Show

- Create a new request
  - **GET**: `https://restcountries.com/v3.1/name/peru` 

**ASK**
What type of RESTful request is this?
**ANSWER**
**show**


**ASK**
What does a status code of **200** mean?
**ANSWER**
OK

- Alright I'll name this **show peru**

This platforms help us making requests without code, we can see the type of data returned to us before we take it to Python

Let me trigger another request for a country which doesn't exist. 

**ASK**
What Http status code should I get if I search for a country called Emile?

**ANSWER**
**404**

*CREATE NEW REQUEST AND MAKE A GET REQUEST TO*: ` https://restcountries.com/v3.1/name/emile`

### Filtered Data

Let's go back to our documentation and see what other data we can pull out

https://restcountries.com/

At the top of the code cell, we can get all countires, filtered by fields. 

Let's create a new request and add this in:

- `https://restcountries.com/v3.1/all?fields=name,capital,currencies`

So now we're pulling in information about all countries, name, capital and currency. 

How do you think we could combine to the two, so we could only see information about, let's say Peru's capital.

**ASK**
Any ideas?

**ANSWER**
`https://restcountries.com/v3.1/name/peru?fields=capital`

We use the endpoint for a specific country and then combine the fields of our earlier request. 


### End of day challenge

I want you to spend some time with this API before the end of the day. I'll be here to support you but please, stay with Postman for a little while and make different requests to see what data is available and how you can filter. 

Then I want you to make a decision about some information, you think is interesting. On the documentation you'll see all the different fields which you can search for. 

There's information on:
- what side of the right they drive on
- a countries borders
- timezones

Ultimately, I'd like you to end up with a programme which firstly takes an **input**, a country name and then returns information you've chosen about that country. 

I've defined a solution again, but I'd encourage you to play around with this one. 

I'd encourage you to define the fields you want information in, on that endpoint. What this will do is ensure the data sent over is as lightweight as possible and bring in less data to our program. 
















# Friday

## Pre-Training

- Load Slidee Day 5

- `SLIDE 1`

## Training

Good morning again. I hope everyone is doing well. 

We're at the end of our first week and I wanted to tie a few things together before we go into the weekend. 

Over the course so far we've looked at the Python fundamentals:
- variables
- data types
- control flow
- loops
- functions

Then on the first part of the course we looked at writing and reading from JSON and CSV files before this part of the course and we've added in OOP and making requests to APIs. 

That's going to be the end goal but before we do that I want to show you how to handle XML, which I believe VMO2 uses. 


XML (eXtensible Markup Language) is a **text-based, hierarchical data format**.

In a few ways it's similar to JSON, we can use to share information across the internet but unlike JSON:
- It's structure is expressed through *tags*
- Everything has explicit opening and closing elements

 
XML is very explicit about where data starts and ends.

---

### Basic XML Example

`SLIDE 2`

```xml
<customer>
  <name>Alex</name>
  <age>32</age>
  <active>true</active>
</customer>
```

Explain:
- Tags define structure
- Data lives between tags
- Nesting shows hierarchy

So we can see that:
- name
- age
- active 

All belongs to the specific **customer**

---

We can extend this to involve larger data sets

`SLIDE 3``

```xml
<order>
  <customer>
    <name>Alex</name>
  </customer>
  <items>
    <item>
      <name>Router</name>
    </item>
    <item>
      <name>Mobile</name>
    </item>
  </items>
</order>
```

With this XML there's a:
- Strong tree structure
- One root element
- Clear parent–child relationships which we see through nesting

**ASK**
Can anyone tell this about the information in this data?
**ANSWER**
It shows the order of a customer called Alex and the two items involved in the order, a: router and mobile

---

### Attributes (Light Touch)

One thing which seperates XML or information held in a Markup format compared to others is the idea of attributes. 

`SLIDE 4`

```xml
<device type="router" status="online" />
```

Explain:
- Attributes are metadata on a tag
- It can help reduce nesting - which is useful if the data starts to become more complex. 
- Not as commonly seen but it's another way to present information

Attributes are a common source of confusion.

---

Let's take a look at how we can actually covert XML to Python. 

Without an API publically available to give us good XML, we'll define our own but the techniques will be the same. 

### Standard Library: `xml.etree.ElementTree`
As with CVS or JSON. Python includes built-in XML parsing tools.

**main.py**
```python
import xml.etree.ElementTree as ET
```

Despite the import looking more confusing, essentially there's an **xml** import, which is an object, then we just dig into the object and pull out the ElementTree and rename is as ET. 

We could just import xml, but if we know there's only a subseciton of the the import we need, we can just go for that instead. 

---

### Parsing XML from a String

Let's go ahead and define some XML, it's in the GitHub Gist as well if you wish to copy it out. 

**main.py**
```python
import xml.etree.ElementTree as ET

xml_data = """
<customer>
  <name>Alex</name>
  <age>32</age>
</customer>
"""

root = ET.fromstring(xml_data)
```

So this maybe how we'd receive XML data from an API, it arrives as a string and part of the syntax are the three quotation marks either side of the XML.

At the bottom, we can see we have a new variable **root** and the value assigned to it is what we get when we pass out XML data into a function, from string. 

Basically, it's converting or parsing our XML string into an ElementTree object.

This initially is confusing but basically, we receive one string from an API, what's helpful to us, is the structure XML so we can start actually reading the data. 
- `root` represents the top-level element
- Everything else hangs off it

**main.py**
```python
import xml.etree.ElementTree as ET

xml_data = """
<customer>
  <name>Alex</name>
  <age>32</age>
</customer>
"""

root = ET.fromstring(xml_data)

print(root)
```

- *RUN* `python main.py`

We can see it's an element, which is the language we use when referring to XML and the element is regarding a **customer**, the rest is the location in memory. 

Everything in Python is generated from a class, so we know we're not handling Python data just yet. 

Let's look at accessing some of the information. 

In this example, the root element is **customer**, so when we refer to root, we can dig into this data from that point. 

---

### Accessing Child Elements

```python
import xml.etree.ElementTree as ET

xml_data = """
<customer>
  <name>Alex</name>
  <age>32</age>
</customer>
"""

root = ET.fromstring(xml_data)

# NEW CODE
name = root.find("name").text
age = root.find("age").text

print(name, age)
```

Explain:
- `.find()` searches direct children
- `.text` extracts the value as a Python string

**ASK**
What datatype is `age` right now?

**ANSWER**
string

From this point we have flexibility. 

A lot of the time we'll request data, that could be as XML or JSON and the first action we want to take it to convert it into Python so we can manipulate it with our scripts. 

**main.py**
```python
import xml.etree.ElementTree as ET

xml_data = """
<customer>
  <name>Alex</name>
  <age>32</age>
</customer>
"""

root = ET.fromstring(xml_data)

name = root.find("name").text
age = root.find("age").text

# NEW CODE
customer = {
    "name": name,
    "age": int(age)
}

print(customer)
```

- *RUN* `python main.py`

From this point I could send the data or to a database which we'll look at in a few sessions time. I can persist in a JSON file.

We've already converted XML to Python, now we'd need to serialise that dictionary to JSON.

**main.py**
```python
import xml.etree.ElementTree as ET
# NEW CODE
import json

xml_data = """
<customer>
  <name>Alex</name>
  <age>32</age>
</customer>
"""

root = ET.fromstring(xml_data)

# NEW CODE
name = root.find("name").text
age = root.find("age").text

customer = {
    "name": name,
    "age": int(age)
}

# NEW CODE
with open("customer.json", "w", encoding="utf-8") as f:
    json.dump(customer, f, indent=4)
    
print("JSON file created")
```

*RUN CODE*

There's also the possibility that we'll receive data whether it be JSON or XML and we want to persist it locally as an XML file. 

It's a little bit more hands on so let's look at it. 

Remember, the first thing we need to do is convert to Python then from that point we have our flexibility, so I'll start with our **customer dictionary**

**main.py**
```python
import xml.etree.ElementTree as ET

xml_data = """
<customer>
  <name>Alex</name>
  <age>32</age>
</customer>
"""

root = ET.fromstring(xml_data)

name = root.find("name").text
age = root.find("age").text

customer = {
    "name": name,
    "age": age
}
```

As we've seen, we describe elements as having a parent / child relationship

In this example, we've got our data as Python code, where we received that from is irrelevant but it could have arrived as JSON, CSV, XML or even, Python code we've internally created. 

**main.py**
```python
import xml.etree.ElementTree as ET

customer = {
    "name": "Alex",
    "age": 32
}
```

So now we need to create the XML structure, it almost feels like we're doing this in reverse. 

We'll start by creating the root element, we'll call this **customer**, again, this is going to be the parent element. 

Because our variable in Python is called customer. It makes sense that that is what the data relates to so we'll pass that in as a string. 

**main.py**
```python
import xml.etree.ElementTree as ET

customer = {
    "name": "Alex",
    "age": 32
}

# NEW CODE
root = ET.Element("customer")
```

Then we fall into the process of having to create **sub elements** or child elements on the root. 

You'll see the pattern develop but, if our XML, stores data inside elements, it's those elements which give meaning to the data.

In regular Python, it's the key name's which give our data meaning. 

But for now, I need to create two sub elements.

**main.py**
```python
import xml.etree.ElementTree as ET

customer = {
    "name": "Alex",
    "age": 32
}

root = ET.Element("customer")

# NEW CODE
name_element = ET.SubElement(root, "name")
name_element.text = customer["name"]
```

**ET.Subelement** takes two arguments, the parent element it attatches to and then the key element name. 

I've stored it into a variable, so we can later refer to it and give it a text value. 

### Micro Challenge

Try and do the same, create an element for age. I'll be doing it on screen, if you want, but use the pattern from earlier.  


**main.py**
```python
import xml.etree.ElementTree as ET

customer = {
    "name": "Alex",
    "age": 32
}

root = ET.Element("customer")

name_element = ET.SubElement(root, "name")
name_element.text = customer["name"]

# NEW CODE
age_element = ET.SubElement(root, "age")
age_element.text = customer["age"]
```

Once we've got our XML structure, the way we want it. We then actually need to convert that string, into pure XML, what we call a tree.

From that point we can save it to a file. 

Before we do that, though. We have one issue.

In my data I've got an int but XML only deals with strings. It's one of the reasons, it's not the most popular format, but I need to turn our age value into a string but adding it as text.

**main.py**
```python
import xml.etree.ElementTree as ET

customer = {
    "name": "Alex",
    "age": 32
}

root = ET.Element("customer")

name_element = ET.SubElement(root, "name")
name_element.text = customer["name"]

age_element = ET.SubElement(root, "age")
age_element.text = str(customer["age"])
```

**main.py**
```python
import xml.etree.ElementTree as ET

customer = {
    "name": "Alex",
    "age": 32
}

root = ET.Element("customer")

name_element = ET.SubElement(root, "name")
name_element.text = customer["name"]

age_element = ET.SubElement(root, "age")
age_element.text = str(customer["age"])

tree = ET.ElementTree(root)
tree.write("customer.xml", encoding="utf-8", xml_declaration=True)
```

- *RUN* `python main.py`

---

### Looping Through Elements

I think that was fairly technical and we can probably agree the data wasn't that complex. 

Let's look at dealing with some more deeply neested XML

**main.py**
```python
import xml.etree.ElementTree as ET

xml_data = """
<items>
    <item>Router</item>
    <item>Mobile</item>
    <item>Laptop</item>
</items>
"""

root = ET.fromstring(xml_data)
```

We'll start off by parsing to Python.

With this XML we have here, the main difference is we don't have one **name** tag and one **age** tag but three of the same tags and that presents a little bit of a challenge. I have an initial question.

**ASK**
What datatype in Python do you think would best suit this XML?

**OPINION**
Our root is **items**, that's fine, but if we were to employ the same tactic of accessing the individual **item** tags we'd run into an error.

 I think a list

 If we employed our previous tactic of finding a child by name, let's see what happens. 

**main.py**
```python
import xml.etree.ElementTree as ET

xml_data = """
<items>
    <item>Router</item>
    <item>Mobile</item>
    <item>Laptop</item>
</items>
"""

root = ET.fromstring(xml_data)

# NEW CODE
item = root.find("item").text

print(item)
```

*RUN CODE*

It only finds the first instance of the **item** element

What we need to do is grab all instances of the **item** elements and we do that with a new XML method

Fortunately, it's called **findall** and it returns a list type object.

What I'll do, is make some changes to the code base and loop over that list object and print the values we have. 

**main.py**
```python
import xml.etree.ElementTree as ET

xml_data = """
<items>
    <item>Router</item>
    <item>Mobile</item>
    <item>Laptop</item>
</items>
"""

root = ET.fromstring(xml_data)

# NEW CODE
for item in root.findall("item"):
    print(item.text)
```

- *RUN* `python main.py`

Now we're working in Python, we have options.

**main.py**
```python
import xml.etree.ElementTree as ET

xml_data = """
<items>
    <item>Router</item>
    <item>Mobile</item>
    <item>Laptop</item>
</items>
"""

root = ET.fromstring(xml_data)

# NEW CODE
items = []

for item in root.findall("item"):
    # UPDATED CODE
    items.append(item.text)
    
print(items)
```

- *RUN* `python main.py`

Let's work the other way and convert a Python list to an XML file.

We have to inverse what we've done and loop through our list and convert back into XML.

**main.py**
```python
import xml.etree.ElementTree as ET

items = ["Router", "Mobile", "Laptop"]
```

We'll start off by creating a root of the XML data

**main.py**
```python
import xml.etree.ElementTree as ET

items = ["Router", "Mobile", "Laptop"]

# NEW CODE
root = ET.Element("items")
```

Now I want to loop through my **items** list and create child elements for every one.

**main.py**
```python
import xml.etree.ElementTree as ET

items = ["Router", "Mobile", "Laptop"]

root = ET.Element("items")

# NEW CODE
for item in items:
    item_element = ET.SubElement(root, "item")
    item_element.text = item
```

The syntax is exactly the same but now we do it in a loop. 

We started the week, just revisiting our Python fundamentals and I do believe, if you want to continue getting better, knowing what you can do with vanilla Python is the way forward.

Let's create our XML tree and save it to a new file. 

**main.py**
```python
import xml.etree.ElementTree as ET

items = ["Router", "Mobile", "Laptop"]

root = ET.Element("items")

for item in items:
    item_element = ET.SubElement(root, "item")
    item_element.text = item

# NEW CODE
tree = ET.ElementTree(root)
tree.write("items.xml", encoding="utf-8", xml_declaration=True)
```

- *RUN* `python main.py`


---

### Nested Searching

I want to show you another piece of XML which is nested even further and what I want to convey is that XML navigation is a step-by-step process. 

**main.py**
```python
import xml.etree.ElementTree as ET

xml_data = """
<order>
    <items>
        <item>
            <name>Router</name>
        </item>
        <item>
            <name>Mobile</name>
        </item>
        <item>
            <name>Laptop</name>
        </item>
    </items>
</order>
"""
```

We've got our root: **order**, that has one child **items** which in turn has three **item** children, each of them has a **name** child. 

Again I do want to reiterate that most modern applications prefer JSON over XML because XML is considered more difficult to work with - however lots of big companies with legacy code still use XML, what I mean to say is don't worry if this looks tricky, because it is. 

But let's try and extract some data again. 

**main.py**
```python
import xml.etree.ElementTree as ET

xml_data = """
<order>
    <items>
        <item>
            <name>Router</name>
        </item>
        <item>
            <name>Mobile</name>
        </item>
        <item>
            <name>Laptop</name>
        </item>
    </items>
</order>
"""

# NEW CODE
root = ET.fromstring(xml_data)
```

We've seen that **root.find()** only returns one single element, where: **root.findall()** returns all elements with that name.

I want to interact with the **item** element but specifically, all of it's children, the **items** element. I can chain these methods together to loop over both to dig into the data. 

**main.py**
```python
import xml.etree.ElementTree as ET

xml_data = """
<order>
    <items>
        <item>
            <name>Router</name>
        </item>
        <item>
            <name>Mobile</name>
        </item>
        <item>
            <name>Laptop</name>
        </item>
    </items>
</order>
"""

root = ET.fromstring(xml_data)

# NEW CODE
root.find("items").findall("item"):
```

This code, returns the list type object of all the **item** elements, and it's that data I'd like to loop over. 

**main.py**
```python
import xml.etree.ElementTree as ET

xml_data = """
<order>
    <items>
        <item>
            <name>Router</name>
        </item>
        <item>
            <name>Mobile</name>
        </item>
        <item>
            <name>Laptop</name>
        </item>
    </items>
</order>
"""

root = ET.fromstring(xml_data)

# UPDATED CODE CODE
for item in root.find("items").findall("item"):
```

This is where things get complicated, if not already. 

Each **item element** also has a child element **name**

So within the loop I need to find more information. 

**main.py**
```python
import xml.etree.ElementTree as ET

xml_data = """
<order>
    <items>
        <item>
            <name>Router</name>
        </item>
        <item>
            <name>Mobile</name>
        </item>
        <item>
            <name>Laptop</name>
        </item>
    </items>
</order>
"""

root = ET.fromstring(xml_data)


for item in root.find("items").findall("item"):
    # NEW CODE
    print(item.find("name").text)
```


- *RUN* `python main.py`

The last thing I'll do before setting you off on a little activity is convert this again into a Python dictionary.

What we need to be thinking about is how could the dictionary look like. I don't speak a second language but perhaps conceptually it's similar to working as a translater, taking one sentence in French and think about how we'd construct it in Japanese. 

I can see the object is going to relate to an **order** and there's going to be a key of **items** on that order. 

When I see multiple sibling elements like we have with the three **item** elements, I think of relating data and using a list. 

But because each list item contains information about a **name** I think the **items** list will need to further hold **dictionaries**.

That may sound tricky but what I'd suggest is thinking aloud about the XML.

"We have an order with a series of items and each item has a name"

From that we can substitute "series of items" with **list of items** and then we think about what data type each element in that list should be. 

The reason I'm choosing a dictionary is because there's space for more information in each **item** element.

**main.py**
```python
import xml.etree.ElementTree as ET

xml_data = """
<order>
    <items>
        <item>
            <name>Router</name>
            // NEW CODE             <----
            <price>30</price>
        </item>
        <item>
            <name>Mobile</name>
            # NEW CODE             <----
            <price>700</price>
        </item>
        <item>
            <name>Laptop</name>
            # NEW CODE             <----
            <price>1100</price>
        </item>
    </items>
</order>
"""


root = ET.fromstring(xml_data)


for item in root.find("items").findall("item"):
    print(item.find("name").text)

```


Because of this I personally think the key/pair nature of dictionaries works well but again this is just a choice

*REMOVE **price** elements. 

**main.py**
```python
import xml.etree.ElementTree as ET

xml_data = """
<order>
    <items>
        <item>
            <name>Router</name>
        </item>
        <item>
            <name>Mobile</name>
        </item>
        <item>
            <name>Laptop</name>
        </item>
    </items>
</order>
"""

root = ET.fromstring(xml_data)

# NEW CODE
order_dict = {
    "items": []
}

for item in root.find("items").findall("item"):
    print(item.find("name").text)
```

So I'll start with just the root and I'll create a Python dictionary with a key of items

**main.py**
```python
import xml.etree.ElementTree as ET

xml_data = """
<order>
    <items>
        <item>
            <name>Router</name>
        </item>
        <item>
            <name>Mobile</name>
        </item>
        <item>
            <name>Laptop</name>
        </item>
    </items>
</order>
"""

root = ET.fromstring(xml_data)

order_dict = {
    "items": []
}

for item in root.find("items").findall("item"):
    # UPDATED CODE
    name = item.find("name").text
    # NEW CODE
    order_dict["items"].append({"name": name})

print(order_dict)
```

## Hands-on Exercise (30–40 mins)

This will all take some time getting your self familiar with consuming XML and manipulating it as you wish. 

The main thing to say at this point is when we make requests which return XML, each endpoint should be very consistent, why I mean by that is the relationship the XML has will be consistent between each request.   

With every XML request wouldn't need to write new Python code to parse and manipulate it 

I've got some more XML which we'll pretend is arriving from an API and I've created the skeleton of a Python class which I want you to expand to do three things through three methods.

1. Convert XML into a Python Dictionary
2. Then send that Python Dictionary to a JSON file
3. Also persist the Python dict, to an XML file


**STARTER CODE**
**main.py**
```python
import xml.etree.ElementTree as ET
import json

xml_data = """
<order>
    <items>
        <item>
            <name>Router</name>
            <price>89.99</price>
            <quantity>1</quantity>
            <sku>RTR-001</sku>
        </item>
        <item>
            <name>Mobile</name>
            <price>599.99</price>
            <quantity>2</quantity>
            <sku>MOB-204</sku>
        </item>
        <item>
            <name>Laptop</name>
            <price>1299.99</price>
            <quantity>1</quantity>
            <sku>LTP-550</sku>
        </item>
    </items>
</order>
"""


import xml.etree.ElementTree as ET
import json


class OrderConverter:

    @staticmethod
    def xml_to_dict(xml_string):
        root = ET.fromstring(xml_string)

        order_dict = {"items": []}

        # ADD CODE HERE

        return order_dict



    @staticmethod
    def dict_to_xml_file(data: dict, filename: str):
        root = ET.Element("order")
        items_elem = ET.SubElement(root, "items")

        # ADD CODE HERE

        tree = ET.ElementTree(root)
        tree.write(filename, encoding="utf-8", xml_declaration=True)



    @staticmethod
    def dict_to_json_file(data: dict, filename: str):
        # ADD CODE HERE


python_dict = OrderConverter.xml_to_dict(xml_data)

OrderConverter.dict_to_xml_file(python_dict, "orders.xml")
OrderConverter.dict_to_json_file(python_dict, "orders.json")
```


**SOLUTION**
**main.py**
```python
import xml.etree.ElementTree as ET
import json

xml_data = """
<order>
    <items>
        <item>
            <name>Router</name>
            <price>89.99</price>
            <quantity>1</quantity>
            <sku>RTR-001</sku>
        </item>
        <item>
            <name>Mobile</name>
            <price>599.99</price>
            <quantity>2</quantity>
            <sku>MOB-204</sku>
        </item>
        <item>
            <name>Laptop</name>
            <price>1299.99</price>
            <quantity>1</quantity>
            <sku>LTP-550</sku>
        </item>
    </items>
</order>
"""


import xml.etree.ElementTree as ET
import json


class OrderConverter:

    @staticmethod
    def xml_to_dict(xml_string):
        root = ET.fromstring(xml_string)

        order_dict = {"items": []}

        for item in root.find("items").findall("item"):
            item_data = {
                "name": item.find("name").text,
                "price": float(item.find("price").text),
                "quantity": int(item.find("quantity").text),
                "sku": item.find("sku").text
            }
            order_dict["items"].append(item_data)

        return order_dict

    @staticmethod
    # RECIEVE THE PYTHON DICT AND ADD A FILE NAME
    def dict_to_xml_file(data: dict, filename: str):
        # DEFINE THE ROOT ELEMENT
        root = ET.Element("order")
        # CREATE CHILD OF ROOT CALLED ITEMS
        items_elem = ET.SubElement(root, "items")

        # ITERATE OVER ITEMS LIST
        for item in data["items"]:
            # FOR EACH SINGULAR ITEM CREATED A CHILD ELEMENT FOR ITEMS ELEMEMENT
            item_elem = ET.SubElement(items_elem, "item")

            
            # CREATE A CHILD ELEMENT FOR EACH ITEM ELEMENT
            name_elem = ET.SubElement(item_elem, "name")
            # GIVE TE VALUE TAKEN FROM THE NESTED DICTIONARY KEY
            name_elem.text = item["name"]

            price_elem = ET.SubElement(item_elem, "price")
            price_elem.text = str(item["price"])

            quantity_elem = ET.SubElement(item_elem, "quantity")
            quantity_elem.text = str(item["quantity"])

            sku_elem = ET.SubElement(item_elem, "sku")
            sku_elem.text = item["sku"]

        tree = ET.ElementTree(root)
        tree.write(filename, encoding="utf-8", xml_declaration=True)

    @staticmethod
    def dict_to_json_file(data: dict, filename: str):
        with open(filename, "w") as f:
            json.dump(data, f, indent=4)


python_dict = OrderConverter.xml_to_dict(xml_data)

OrderConverter.dict_to_xml_file(python_dict, "orders.xml")
OrderConverter.dict_to_json_file(python_dict, "orders.json")
```


### Alternative Solution

This works and is fine, the one limitation with my solution is if the amount of data contained inside each **item** element changes, I'd need to change for method **dict_to_xml_file()**

There is another and potentially cleaner approach. 

**main.py**
```python
import xml.etree.ElementTree as ET
import json


xml_data = """
<order>
    <items>
        <item>
            <name>Router</name>
            <price>89.99</price>
            <quantity>1</quantity>
            <sku>RTR-001</sku>
        </item>
        <item>
            <name>Mobile</name>
            <price>599.99</price>
            <quantity>2</quantity>
            <sku>MOB-204</sku>
        </item>
        <item>
            <name>Laptop</name>
            <price>1299.99</price>
            <quantity>1</quantity>
            <sku>LTP-550</sku>
        </item>
    </items>
</order>
"""



class OrderConverter:

    @staticmethod
    def xml_to_dict(xml_string):
        root = ET.fromstring(xml_string)

        order_dict = {"items": []}

        for item in root.find("items").findall("item"):
            item_data = {
                "name": item.find("name").text,
                "price": float(item.find("price").text),
                "quantity": int(item.find("quantity").text),
                "sku": item.find("sku").text
            }
            order_dict["items"].append(item_data)

        return order_dict



    @staticmethod
    def dict_to_xml_file(data, filename):
        root = ET.Element("order")
        items_elem = ET.SubElement(root, "items")

        for item in data["items"]:
            item_elem = ET.SubElement(items_elem, "item")

            # UPDATED CODE
            for key, value in item.items():
                print(key, value)
 
                child_elem = ET.SubElement(item_elem, key)
                child_elem.text = str(value)

        tree = ET.ElementTree(root)
        tree.write(filename, encoding="utf-8", xml_declaration=True)



    @staticmethod
    def dict_to_json_file(data, filename):
        with open(filename, "w") as f:
            json.dump(data, f, indent=4)


python_dict = OrderConverter.xml_to_dict(xml_data)
print(python_dict)
OrderConverter.dict_to_xml_file(python_dict, "orders.xml")
```

This is smarter code becuase if we recieve more data about each item from an API request, this code will still function but something we spoke about earlier in the course is that the best code is readable code for you and that will change overtime but prioritise code which makes sense to you. 

---



End of Day 4 — Error Handling & Debugging APIs.
