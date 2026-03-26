
# Advanced Python — Day 6

## What Is Data? (Trainer Notes)

**Target delivery time:** ~1–1.25 hours  
**Audience:** Learners with Python and API experience, new to databases and SQL  
**Purpose:** Establish a shared, concrete understanding of what “data” means before introducing databases and SQL.  
**Trainer mindset:** Ground abstract ideas in familiar, real-world examples. This is conceptual groundwork for everything that follows.

---

### Learning Outcomes
By the end of this section, learners will be able to:
- Explain what “data” means in a software context.
- Distinguish between structured and unstructured data.
- Describe rows, columns, and tables in plain language.
- Recognise common real-world data models such as customers, orders, and student results.
- Understand why databases exist to manage data at scale.

---

# Pre-Training

- Load Slidee Day 6


# Training

`SLIDE 1`

Hello everyone! I hope you're all had a good weekend! We're going into our final week of training and the first part of this week we're going to be looking data. 

## What Is Data?

It's reasonable to ask, *what is data?*, I've been talking about data since the very first day, so it hardly seens like the time to explain what it is for the first time. 

### Plain-English Definition

If I were to consult the Oxford English Dictionary which I did, it'd read: 

`SLIDE 2`

*information, especially facts or numbers, collected to be examined and considered and used to help decision-making, or information in an electronic form that can be stored and used by a computer:*

To add more meat to the bone, so to speak, data is **recorded information** that software can perform different actions on:
- Store data
- Read data
- Transform or manipulate data
- and Analyse it


---

### Data vs Information
Before we progress, there's a difference between how we've been dealing with data so far. 

We've looked at storing information in JSON or XML files. 

There's nothing wrong with this, but it's best used when there's a small dataset or we're storing things like configuration.

They're quick to create and human readable. All very real advantages of saving data to files we create. 

The problem arises though when we have lots of that data and we need to ascertain information from that data. 

`SLIDE 3`

- **Data** → data is like our raw facts, contains everything we know but when it grows in size it can lose it's meaning  
- **Information** → data with meaning becomes information, it's information businesses want, so they can use it to make decisions, having that data inside a DB makes it much easy to access and interpret.  

As I've said, we've been playing around with it all week. 

**main.py**
```python
{"score": 83}
```

This is some simple data, imagine we were an examinations board for students sitting their A-Levels or GCSEs, we'll have hundreds of thousands of people sitting exams. With all this information we want to have information:
- how many students passed their exam
- how many school boys passed their exam
- how many school girls passed their exam

When we have lots and lots of data, then it becomes harder and importantly slower to use files and then Python to query and filter that data.

The threshold is fairly subjective but if you have around 50+ mega bytes of data or in the thousands or millions of data entries, holding this information in a DB starts to become more efficient. 

---


## Structured vs Unstructured Data

Before we get into actually looking at code I want to talk about **structured** and **unstructured data**

I know a couple of you have said you've got some experience with SQL before. 

The **S** in SQL stanrds for **structured**, and by that we mean:

- Rows and columns of data
- Easy to query
- the structure of the data is accessible and imortantly predefined 

Things like:
- Spreadsheets
- Database tables
- Even looking the Premier League table or a TV schedule

There all examples of data with a clear structure

---

### Unstructured Data
Unstructred data on the other hand:
- data with no fixed schema
- Free-form

- Emails
- Images
- PDFs

---

## Rows, Columns, and Tables

So SQL makes use of rows and columns, defined on tables

`SLIDE 4`

### Columns
Columns represent attributes like:
- name
- gender
- score

I want to highlight the first column and this is the ID. 

With any data, it's important for a column to exist which has an entry unique to that row of data. 

With this example, we could have many students with the:
- same name
- or the same score
- definitely the same gender or subject
- Having a column with a unique value, usually an ID allows us target specific information.

If this was a table for customers of VMO2, it's likely that each account will have to have a unique email address and the same email address wouldn't be allowed used to create multiple accounts. In that case, an email column may serve as that unique entry.

If a customer calls up a help desk and said I've got some issues with my account, it's critical that we can pull that customers data, we can't garauntee there won't be two people called Emile Sherrott so having a column of unique data becomes important like an email. 

In my experience, even with unique data entry points that like, they'll be a specific ID column which suits that purpose. 

### Rows
Then the rows, represent individual records.

### Tables
All of this lives on a table and the table is what groups the related rows together.

Then, it's not something we'll cover yet but we have multiple tables which can all be queried together. 

---

## Real-World Examples

### Customers
So for our customers we could have information about their

ID, name, email, signup date

### Orders
If we had a table about orders, we could store the:

Order ID, customer ID, product, price

---

## Why Databases Exist

Databases exist to provide:
- Fast searching
- Reliability
- Especially at scale

We probably need to know how many customers have a certain package, where our customers are. Or generally, any break down of that wider information. 

---

## Micro Exercise

I think before we start creating and querying data from a live database, it's important to actually think about the data we need to keep. 

We'll move onto to defining our own databases this week and it's always the first thing you need to do. 

If we're, let's say a working bring a new supermarket to the highstreet, a rival of Tesco, we'd probably need a database about all the produts we have. We could store information like the:
- name of a product
- the cost
- the supplier

They'd be a phase where we just need to discuss as a team the data we need and that conversation would sit alongside the need for insights, which we want to get from that data.

So structure is important, so we have information relevant for us to make business decisions. 


---


## Activities (10–15 mins)

### Spreadsheet Exploration
What I'd like is for everyone to imagine they're living a new life as a florist and we've identified that all of our competitors in the area don't have an online presence. 

We want to be able to offer our customers the ability to see what flowers we have in stock before they come to our store and before they are potentially dissapointed. 

I don't want to give you to much, but what data would be helpful for us to store? Maybe the flower name?

**ASK**
What else?

**ANSWER**
- colour of the flower
- the quantity in stock
- the supplier maybe or where the flower comes from
- the genus of the flower
- maybe an image of the flower?

Once we've identified that columns for our data, there's secondary questions we need to ask:
- “Which columns must always have a value?”
  - We've all filled in forms where some entries are optional and others not
- “Which columns could be optional?”
- “Which columns could serve as good IDs?”

I've got a slide of a potential table for orders

`SLIDE 5`

There's some terms like:
- Prmary key
- Real

Which we've not seen before but we'll see all these later.

What's good about this table is all the data is consistent. The dates are formatted the same way, the prices are all numeric and we have an id of unique values. 



---

This leads us closer to what a database actually is compared to an excel spreadsheet.


`SLIDE 6`

A database is a **system for storing and managing structured data** so it can be:
- Queried efficiently
- Updated safely

That's the hard and fast of it. 
 
“A database is a spreadsheet that’s been engineered for scale, safety, and speed.”

This is a common mistake people make when thinking about databases. That they were essentially posh spreadsheets. 


### Similarities
Databases and spreadsheets both:
- Store data in rows and columns
- Organise data into tables
- Represent real-world entities


---

### Key Differences

`SLIDE 7`

| Spreadsheet | Database |
|------------|----------|
| Manual editing | Programmatic access |
| Single-user focus | Multi-user by design |
| Easy to break | Enforces rules |
| Limited size | Scales to millions of rows |
| No query language | SQL for querying |

It's unlikely people have met this threshold but modern excel allows for just over 1 million rows of data.

That's good. Not if we're a company with more than a million customers. 

SQLite which we'll look at has 2 to the power 64. Which is over 281 terabytes of information.

`SLIDE`

Explain:
- Spreadsheets are great for humans but require consistent attention as well
- Databases are built for software and data at scale

---

I'm sure a lot of you are familiar with excel or other spreadsheet programmes

They struggle when:
- Multiple people edit at once
- Data volume grows
- Consistency matters
- Automation is required

You can probably imagine a spreadsheet which has information about dates, and someone's inputed the date as the 20th September as text and someone else has inputted the date as 20/09/2026 and the consistency is all off. 

We can programme a DB so that doesn't happen. 

There's an expression that: “Spreadsheets fail quietly. Databases fail loudly — and that’s good.”

We should know immediately when something's not right.


---

Databases exist to solve a lot of those issues, limiting:
- Data duplication
- Data inconsistency
- Slow searching
- Lost or corrupted files
Then allowing safe
- Concurrent access


Databases are about trust. 

---

So we've said that databases are interacted with via software. 

This course is predominantly about Python, as we know but we don't use Python directly on a database. 

We need to use another language called SQL. 


SQL (Structured Query Language) is a **language for asking questions about data** stored in a database.

- SQL is not Python
- SQL describes *what* you want, not *how* to get it

We'll come onto specific SQL syntax soon but the type of queries we write will read similar to statements like:

- “Show me all customers.”
- “Find orders from last week.”
- “Which students scored above 70?”


---

## What Is SQLite?

SQL comes in many different formats though. 

It's a language yes, structured querying langauge, but take English.

How someone from the south coast speaks is different to how a Yorkshireman speaks or a Glasweigan. 


We're specifically going to be looking at SQLite which is an accent of the language.

If we learn British English, we'll be able to understand other engines, although where I say pavement, our American cousins may say sidewalk. 

So... SQLite

SQLite is a **lightweight relational database** that stores data in a **single file**.

We can say it's a database you can carry around in your pocket. 

Rather than storing information on large computers with massive amounts of storage, it lives closer to home. 

I just want to emphasise the distinction between SQL and SQLite. 

SQL is the language, the syntax we use to write, read and query data. 

You may have heard of SQLite, PostgreSQL or MySQL. These are pieces of software which run on conputers which actually creates the DB and lets SQL interact with it. 

To use my previous analogy, SQL is English, PostgreSQL could be Australian English and MySQL, American english. 

All are English

---

### Key Characteristics
SQLite like all SQL software or engines
- Is relational (tables, rows, columns)
- Uses SQL
Unlike other SQL engines though, it:
- Stores everything in one file
- Runs inside your application

Less setup and less configuration.

PostgreSQL for example requires a seperate computer to host the DB. This is often quite beneficial when the software requires many connections at once. 

Any social media platform or online retailer would require users to all be able to pull information from a shared database. 

If I went onto YouTube and searched for football highlights, the database would be accessible by all there users, over the internet. 

---


SQLite isn't that, it's commonly used for:
- Small to medium applications
- Local tools and scripts
- Desktop apps
  - On my computer I have a note making application called BearNotes and it's really good for writing and storing all the technical concepts I cover. 
  - I can filter the notes, find notes with certain key words
  - This could use SQLite, data needs to be stored and queried but there's no requirement for external access


If you’ve ever used a phone app which keeps data, you’ve probably used SQLite.

---

So conversely, SQLite is not a great fit when:
- Many users write at the same time
- Data size is extremely large
- You need advanced user management

- This is not a failure — it’s a design choice

---

So what do I mean when I say, a **file based** database.

A file-based database:
- Lives in a single `.db` file
- Can be copied, moved, backed up easily which is all to our benefit
- It also persists data between program runs

Just to offer that comparison, other SQL engines require a connection string, and similar to our API requests, uses TCP, or our internet roads to trasmit data between computers. 

We don't have to be worried about that though, we'll see things like:
- `customers.db`
- `tickets.db`
- `weather.db`

That does pose the risk though: Delete the file, we delete the database.

---

You may be thinking, Emile, we've spent a lot of time looking at storing data in files.
- XML / JSON / CSV.

It does sound like the same thing.

Additionally

Take our JSON files:
- They also store data
- No querying
- No constraints on the data

SQLite:
- Structured tables
- Queryable with SQL, which is new
- Enforces rules

So there's trade offs but when there's those large datasets we need to gain insights from, SQLite is the way to go. 

---

We're close to writing our first SQL code together but there's a few more conceptual elements I'd like to discuss 

We describe SQLite as **"No server"**

SQLite:
- Does not run as a separate process
- No ports, no services
- Accessed directly by your program

I've mentioned before that we could compare an IP address to a real address and it's part of the delivery system which allows data to reach different computers accurately. This is what the PostgreSQL and MySQL engines depend on.

If I extend the analogy of sending a latter. 

Each house with an address is found through the IP address.

What if our address is a block of flats, in that situation, the PORT is the specific residence within the flat. 

So when a big server hosts of PostgreSQL database, we need the IP address to send and recieve information to it. But we then also need to specify a PORT or a specic entry point on that computer which is available to handle those actions. 

That's a more complicated process to set up. 


Our **no server** option means your Python script talks straight to the database file.

PostgreSQL is like sending a letter across the country to a specific flat in a building. 

SQLite is deliverying the same message by speaking across a room. 

- Simpler setup
- Fewer moving parts
- Easier learning curve

Perfect for initially learning SQL.

---

# PRACTICAL START

Let me share a DB file then and we can start querying some data. 

*SHARE DB FILE student_results.db*

This contains mock data regarding student results for a series of examinations. 

Once you've downloaded it, you'll need to drag it into GitHub codespaces on the left hand side, where we've had the **main.py** before. 

*DRAG FILE INTO CODESPACES*

Notice if we try to view the contents of the file we can't see it. It's a binary format, native for computers. 

Far more efficient than our JSON, XML or CSV files. 

The first thing we need to do to get ourselves off the ground is run SQLite against our file. 

We've been running `python main.py` to trigger our Python files. 

Now we need to run the sql command against our new file. 

- *RUN* `sqlite3 student_results.db`

This should take us all into a new view. It's here, we execute further SQL commands against our DB file. 

The first one I'll show you is **.tables**

- *RUN* `.tables`

We said that a database is constructed of rows of information which exist inside tables. 

Our command `.tables` shows us what tables exist inside the database and we should all see just the one. 

Now we're ready to start querying our database. 


With SQL, you describe the result you want — the database figures out how to get it.

---


Think of SQL as:
- Asking questions
- Describing filters
- Requesting summaries

In Python, we were doing things like:
- Writing loops
- Managing memory
- Controlling execution flow

---

Let's start with the simplist query. 

```sql
SELECT * FROM student_results;
```

Important to remember the semi-colon on the end.

- The `SELECT` keyword stipulates what columns you want, the use of an asterix means every column of information
- The `FROM` keyword decides, from which table

 
So we can translate this command as take everything from the student results table. 

So instead of returning everything, we can be a little more selective of our data.

One problem for you, is I've built this DB file and you have no idea what are columns of information are. 

We can change this view though. 

- *RUN* `.headers on`


Then we can just re-run: `SELECT * FROM student_results;`


At the top of the output we should now be able to see the column headings of our data.

**student_id|name|age|gender|school|score**


Let's be more selective about our data.

```sql
SELECT name, score FROM student_results;
```

This is better
- You don't always need the `*` in real systems
- Being explicit improves readability
- It also reduces the amount of data being requested, if we can filter the amount of information being sent, that'll make it all quicker. 

---

The column order also matters. It doesn't change the data but can realign the outputted information. 

Right now our name comes before the score. We could write.

```sql
SELECT score, name FROM student_results;
```

Same information. My assumption would be, this view somehow feels a little less intuitive. But it does allow us to choose a certain heirachy.  

---

Let's expand our SQL grammer. 

I want more ways to filter our information. 

Databases often contain:
- Thousands or millions of rows
- You rarely want all of them

---

We can expand our SQL commands with a new keyword, called **WHERE**, with this we can pass in certain conditions. 

- *RUN* `SELECT name, score FROM student_results WHERE score >= 95;`

Notice how our grammer is always capitalised and then our column headings are lower case. 

Let me clear the output. I also want to show you a better way to write this command. 

We're just getting startd and these query's can grow in length and writing everything on one line can become a barrier for us. 

*RUN*
```sql
SELECT name, score
FROM student_results
WHERE score >= 95;
```

That's better.

SQL doesn't really care about whitespace or new lines so we can write our SQL grammar across several lines

So
- `WHERE` filters rows
- Similar to Python, the conditions we define must evaluate to true

---

Most of the comparison operators are the same as what we'd expect but there's one main point of difference.

**main.py**
```
# - `=` equal
# - `!=` not equal
# - `<`, `<=`, `>`, `>=`
```

In Python a single equals sign is making an assignment. 

That process doesn't exist in SQL so a single equals serves as a comparison of equality. 

Lets find all the students who had a perfect score

```sql
SELECT *
FROM student_results
WHERE score = 100;
```

Nice and well done to those students. 

If we we're filtering on a string value in SQL though, like a students name or school name, we need to pass in single quotes around it. Not double quotes.

```sql
SELECT *
FROM student_results
WHERE school = 'Greenfield Secondary';
```

- Strings use quotes

This is a good opportunity to think about datatypes in SQLite because they're not all the same. 

`SLIDE`

- Instead of strings, we refer to them as Text.
- Instead of floats we have **reals**
- Null represents no data instead of None. 
- Integers are the one datatype which survive
- Blobs represent other dumped data like images and files

We can see there's no lists or dictionaries which is consistent among all of SQL.

One difference is we don't have Booleans in SQLite. Booleans are stored as integers where 0 is False and 1 is True. 

---

Let's combine two conditions

```sql
SELECT name, score
FROM student_results
WHERE gender = 'M' AND school = 'Greenfield Secondary' AND score >= 85;
```

Once you've learnt one programming language it becomes easier to try and pick up a second. You may assume another filter we can apply and how we can apply it. 

**ASK**
What is this query requesting?

```sql
SELECT name, score
FROM student_results
WHERE gender = 'M' 
AND school = 'Greenfield Secondary' 
AND (score >= 85 OR score <= 50);
```

**ANSWER**
Return the name and score of male students at Greenfield Seconday, where their score is above or equal to 85 and equal or below 50. 

---

We'll keep on adding new vocabularly.

Databases do not guarantee row order unless you ask.

---

### Sorting Ascending (Default)

```sql
SELECT name, score
FROM student_results
ORDER BY score;
```

Unfortunately for Harper, we can clearly see who had the worse score. 

Also notice the default behaviour is ascending order. 


---

### Sorting Descending

We can amend this by defining a new keyword

```sql
SELECT name, score
FROM student_results
ORDER BY score DESC;
```

---

### Sorting by Multiple Columns

If we want to sort by multiple colums we can as well 

```sql
SELECT name, score
FROM student_results
ORDER BY score DESC, name ASC;
```

So we firstly sort by score, from highest to lowest, then if any scores are the same, we sort alpahbetically on the name column. 

---

If someone wants to ask me who were the top 10 performing students, we don't need to manually read the data, we can limit the output. 


Which is useful for performance as well. 

---

### Basic Limit

```sql
SELECT *
FROM student_results
ORDER BY score DESC
LIMIT 10;
```

I'm going to show you just a couple more keywords. 


We can aggregate or combine multiple rows into a single result.

How many students do we have in our table

### COUNT

```sql
SELECT COUNT(*) FROM student_results;
```

- Counts rows
- Ignores column values
Useful if you're interested in seeing how many entries are present. 

---

We can perform more numeric calculations as well. 

### SUM and AVG

```sql
SELECT AVG(score) FROM student_results;
```

So these keywords behave like our functions, they have parenthesies and they make calculations based on the column headers passed into the parenthesis. 

```sql
SELECT SUM(score) 
FROM student_results
WHERE school = 'Greenfield Secondary';
```

- 5371

Let's see if they did better than some of our other schools

```sql
SELECT SUM(score) 
FROM student_results
WHERE school = 'Riverside Academy';
```

- 6554

I hope my fictional children are in the catchment area for Riverside Academy. 


---

Finally I want to look at **GROUP BY**

Grouping lets you:
- Summarise data per category

---

### Example: Average Score Per Course

```sql
SELECT gender, AVG(score)
FROM student_results
GROUP BY gender;
```


It looks like we group the information at the end, what happens is we Group our data first.

As a side, the grouping would happen after we filter our data with WHERE

So we group the rows of information by the gender.

That seperates the data into two blocks. 

Then we calculate the average scores in each group before pulling in or selecting the column information. 



## Putting It Together


```sql
SELECT school, AVG(score)
FROM student_results
WHERE gender = 'M'
GROUP BY school
ORDER BY AVG(score) DESC
LIMIT 3;
```

1. We select information about the school and the average score.
2. From the student_results table.
3. Only include rows where the gender is 'M'.
4. Then group the remaining rows by school.
5. Calculate the average score for each school.
6. Sort the results from highest average score to lowest.
7. Return only the top three schools for boys.

On a quick side note, if we're ordering by a column we've run an aggregting function on, selecting 'score' wouldn't make sense, we can see that we need to refer to the function as well as the column as well. 

But this is the grammer of SQL. 

This is a template of the order in which keywords are listed. 

This is similar to grammar in English as well. 

If I said: *The big happy friendly golden retriever in the park*, the order of adjectives makes sense to English speakers. 

If I switch that to: *The friendly happy big golden retriever in the park*, the structure of the adjectives doesn't quite stick. 

The same with SQL, the more your familiar with the language the easier it is. 

I've got one more to show you. 

What if I want to asses whether age has an impact on the scores of our female students. 

A start to answering that question could be to find out the average age of the top 15 female students. Then the age of the lowest 15 students.  

Let's begin with finding the average age of the top 15 females. 

I've not yet shown you the syntax for how we could achieve that. 

It's actually a two step solution

```sql
SELECT age, score
FROM student_results
WHERE gender = 'F'
ORDER BY score DESC
LIMIT 15;
```

*DON'T CLEAR*

Then returns a set of information which is ok for the timebeing. 

I'm still human and a computer can calculate the AVG age for me easier than I can, especially if we have 100 thousand students and I want the average age of the top 1000. 

I can actually wrap another SQL query around the one I've just written. 

The data on the screen now has 2 columns:
1. age
2. score

Well what if I create another SQL query which reads: From this new table of information, selelct the average age. 

It'd look something like this:

```sql
SELECT AVG(age)
FROM (
    SELECT age
    FROM student_results
    WHERE gender = 'F'
    ORDER BY score DESC
    LIMIT 15
);
```

So we pass the resulting table of our inner query as the location for our outter query to perform its operation. 

I can also round this output as well.

```sql
SELECT ROUND(AVG(age))
FROM (
    SELECT age
    FROM student_results
    WHERE gender = 'F'
    ORDER BY score DESC
    LIMIT 15
);
```


# SQL Challenges - 20-30 mins


---

We're about to take a step deeper into the world of SQL

In our table right now there's certain ways to present this information.

- *RUN* `.headers on`
- *RUN* `PRAGMA table_info(student_results);`

Pragma allows us to see information or meta data about specific tables in SQLlite. 

```sql
cid|name|type|notnull|dflt_value|pk
0|student_id|INTEGER|0||1
1|name|TEXT|0||0
2|age|INTEGER|0||0
3|gender|TEXT|0||0
4|school|TEXT|0||0
5|score|INTEGER|0||0
```

The output is information on our table, we've got headings as normal.

- cid: Column index (position in the table, starting at 0)
- name: Column name
- type: Data type
- notnull: Whether NULL values are allowed (1 = NOT NULL, 0 = NULL allowed)
- dflt_value: Default value if none is provided
- pk: Whether the column is part of the primary key (1 = yes)

Our primary key is the unique value our database has to have, as we've mentioned, every entry in the DB needs a unique value to seperate it from other rows of information.

This is the primary key and ours is the student_id.

Tomorrow we're going to look at creating tables ourselves and reading from that table with Python and we'll eventually have to define something similar to what we're seeing here, to give our table a structure. 

It'll be our decision if we're allowed missing data or whether there's a default value. 

This will become even more important when we want two tables to actually be related to each other. 

---

Our one table isn't actually very good with the type of data we've been looking at. 

In the real world, students unfortunately have to sit multiple exams for multiple different subjects. 

As an adult, I genuinely still have dreams that I've woken up and I have a history exam about Stalinist agricultural policy and I've not revised for it. 

I digress, in real life, students will have multiple exams. 

We could if we wanted to keep all this information on one table.

But when tables grow in size, they become harder to read and they actually become wasteful. 

`SLIDE`

What this image is showing, is how our table could grow, where we have duplicate rows of data for each student, only in order to allow a partial difference for each entry.

If students each sat 12 exams, we'd need 12 different rows of data per student and despite SQL being an effective way to store lots of data we've got these text and integer values for name, gender and age duplicated more often than necessary.

If data starts looking like this, it's a signal to have another table of informaiton which is related to the first. 


`SLIDE`

In the visualiations we have 2 tables now, one which relates to students and another which solely focuses on student results. 

This is much better because we have more readable data which is additionally more efficient. We're duplicating less information.

Additionally I can query the **student subjects** to find information about average scores for each subject. 

I can also independantly query the **students** table to see the average age of students. 

We'll look at how we can query them both together. 

All tables need a primary key as we've said. 

The **students** table, that's still **student_id** and on the **student_subjects** table, that's **result_id**

I've noticed the column heading on students isn't right, annoyingly. 

One thing which is happening though, is that on the **student_subjects** table, there's a matched column for **student_id**, all with the value 1. 

This is what's known as a **foreign key**.

A **foregin key** is a column on one table which references the **primary key** of another table. It create a relationship between those two tables and helps maintain data integrity. 

We can just read this for now as: *"Alice, with the student_id of 1 has sat 3 exams, Maths, Science and History"*

I've got another DB file which I want to explore. 

*SHARE NEW DB FILE student_results_two_tables.db*

We'll need to run our SQLite command against it the same way. 

- *RUN* `sqlite3 student_results_two_tables.db`

The first thing to inspect are the tables present.

- *RUN* `.tables`

So we've got two tables in this DB:
1. students
2. student_subjects. 

Again I want to inspect the schema of both tables. 

I'll make sure headers are visable.

- *RUN* `.headers on`

Then use the PRAGMA command

- *RUN* `PRAGMA table_info(students);`

Ok, we've got information about the:
- Student ID
- Name
- Age
- Gender
- School

- *RUN* `PRAGMA table_info(student_subjects);`

In our second table we can see:
- Result ID
- Student ID
- Subject
- Score

This is intentially similar as the image I showed you earlier. If you were working with Databases and you weren't the one who designed it, it's worth inspecting the schema before writing your SQL commands. 

But let's do that anyway.


- *RUN* `SELECT * FROM students;`

We still have 500 students

Let's take a look at the new table.

- *RUN* `SELECT * FROM student_subjects;`

If I scroll to the top, we can't even see the top of our output. We've got 2 thousand rows of data and we can see that our second column, which is the foreign key of **student id** is duplicated 4 times. 

What this tells me is every student has sat 4 exams and we've got data on all of those.

I need to introduce something new.

`SLIDE`

What I'm showing you is an ERD or an Entity Relationship Diagram. 

It's how we visualise multiple tables together. 

What we can see is the columns on our two tables and the golden keys are our primary keys. 

The blue key is our indication of a foreign key and the arrow represents the relationship between the two. 

The arrow going from left to right, indicates what we call a **1 to many relationship**. 

By that I mean, 1 student, may have many related entries in the  **student subjects** table.

It's the most common type of relationship but you may see 

`SLIDE`

### 1 to 1 relationships. 
One to one relationships
Where one row in a table would relate to one row in another. 

That could be a staff member, linked directly to another table which contains the individual staff benefits or pay package. 

We want the seperation to avoid really large quries but the data is tied quite closely together. 

`SLIDE`

### Many to Many relationships
Many to many relationships are where many rows in one table relate to many rows in another. 

An example could authors and books.

One author could write many books and a book could be linked to many authors. 

This is showing a JOIN table which is a relatively complicated SQL process but this can have multple rows where an author id or a book id is referenced multiple times. 

I'll be inviting you to create some Entity Relationship Diagrams tomorrow so we'll revisit this. 

*SLIDEE GO BACK TO students - student_subjects ERD*

---

For now, all we care about is trying to retrieve information from both of our tables on Codespace

For that, we have to do a join. 

There's a few types of joins but I'm going to show you the easiest and also the best. 

It's called a LEFT JOIN. 

A left join is when we query a DB and it returns all results from the left table and then only the matching results from the right. 

A RIGHT JOIN does the opposite and an INNER JOIN only shows information when present on both. 

---

Let me show you how we write them.

We've got a lot of information now so I'm going to filter as part of my query to best illustrate this.

The first difference we'll see, is now we have two tables, we have to refer to them every time we reference column headings. 

```sql
SELECT 
    students.student_id,
    students.name,
    student_subjects.subject,
    student_subjects.score
FROM students
LEFT JOIN student_subjects
ON students.student_id = student_subjects.student_id
WHERE students.student_id = 1;
```

We've got even more grammar now, our JOIN comes before WHERE and the other keywords we've used. 

So we're pulling from the students table, the
- student id
- name

Then from the student_subjects table, the:
- subject
- score

When we write `FROM students`, we're stipulating, that this is our main table, either the most complete or holding the most important information. 

Then we have the keyword `LEFT JOIN`, this is saying, bring in information on the **student_subjects** table, when there's a match or corresponding values between the **student id** data in both tables. 


Because we're doing a LEFT JOIN, we'll always bring in the data from the primary table and only when there's corresponding data on the secondary table. 

From this point we can start to introduce more complexity. 

Perhaps I want to see all students who scored above 95 in History

```sql
SELECT students.name, student_subjects.subject, student_subjects.score
FROM students
LEFT JOIN student_subjects
ON students.student_id = student_subjects.student_id
WHERE student_subjects.subject  = 'History' AND student_subjects.score > 95;
```


This is getting very wordy.

Fortunately I can rename our tables so we can refer to them a little easier

```sql
SELECT student.name, exam.subject, exam.score
FROM students as student
LEFT JOIN student_subjects as exam
ON student.student_id = exam.student_id
WHERE exam.subject = 'History' AND exam.score > 95;
```


Potentially I am running a programme for the most gifted students to take them on an open day to a Red Brick University

They need to have scored 90 or above in all their exams and also be under 17 to be eligable. 

```sql
SELECT student.name, exam.subject, exam.score
FROM students AS student
JOIN student_subjects AS exam
  ON student.student_id = exam.student_id
WHERE student.age < 17;
```

So this is returning all our students and their exam results for people who are under 17.

The next filter I want to add is to only return the results where the exam score is greater than 90

```sql
SELECT student.name, exam.subject, exam.score
FROM students AS student
JOIN student_subjects AS exam
ON student.student_id = exam.student_id
WHERE student.age < 17
AND exam.score >= 90;
```

Visually we can see that some of our entries have four rows of data and others have less. 

Logically what I want to do is group the data by name, but only keep the entries which have four rows. 

i.e. Students who scored above 90 in all 4 exams. 

Because we're grouping data I'll only return the **student.name**

 ```sql
SELECT student.name
FROM students AS student
JOIN student_subjects AS exam
ON student.student_id = exam.student_id
WHERE student.age < 17
AND exam.score >= 90
GROUP BY student.name
HAVING COUNT(*) = 4;
 ```

In this code, our first filter is always WHERE, then we GROUP BY certain values. 

The keyword, HAVING adds a filter to our groups and in this use case, only allows groups to remain if there's 4 instances of them.

This isn't easy syntax. 

When we do joins, usually, the expectation is that we're doing relatively narrow queries. 

 ```sql
SELECT student.name, exam.subject, exam.score
FROM students AS student
JOIN student_subjects AS exam
ON student.student_id = exam.student_id
WHERE student.name = 'Chloe Miller';
 ```

This is far more common. 

Let's wrap another request around this to see Chloe's average score. 

```sql
SELECT name, AVG(score)
  FROM (
  SELECT student.name, exam.subject, exam.score
  FROM students AS student
  JOIN student_subjects AS exam
  ON student.student_id = exam.student_id
  WHERE student.name = 'Chloe Miller'
);
```

The last request I'll show you is seeing the average scores for the different schools. 

```sql
SELECT student.school, ROUND(AVG(exam.score), 2)
FROM students AS student
JOIN student_subjects AS exam
ON student.student_id = exam.student_id
GROUP BY student.school;
```

Writing these commands out in the terminal is actually pretty challenging to think about constructing correct grammar. 

I'd recommend doing it seperately, then copying the commands into the terminal for execution. 

I've got a couple more challenges for you before the end of the session. 


