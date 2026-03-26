# Session Notes

Hey everyone, today is going to work slightly different from previous sessions. 

The onus will be on you to create a little application and most importantly, do so in pairs. 

So far you've been working on challenges independantly and that's fine. Practically though as programs grow, it's impossible to manange these applications by yourself. 

Working in pairs isn't always easy though. Collaborating in one file has its complications, if two people are working in a codebase and add code to the same file at the same time, that can often cause what we call merge conflicts. 

A common approach to working in teams is called Pair Programming. 

The idea stems from a movement in software engineering in the late 1990s. It emphasised software quality and adaptability allowing two developers to improve the cadence of new releases. 

This is done through two developers around one work statement. 

There's the idea of a **driver** and a **navigator**

- The driver: writes the code
- The navigator: reviews, thinks ahead, spots issues.

As if you were driving from London to Paris, perhaps you're behind the wheel and someone else would read the map, prepare the snacks etc...

As with a long drive, these roles are supposed to change. If I'm the one writing code into my IDE, that doesn't mean I won't switch with my partner, we should.

You may think if only one person is working, you'd produce code more slowly but many large, successful companies adopt pair programming. 

It's intended to: 
- reduce bugs
- improve design decisions
- and spread knowledge across the team

When I've been writing code across the last two weeks, you've spotted lots of spelling mistakes I've been making and syntax errors. 

It can be really helpful. 

So this concept is really common in agile teams or where a new staff member has joined a team and they're being mentored through a codebase. 

Equally when there's complex code which needs two eyes to break down logic. 

A friend of mine works as a Senior Frontend Engineer at Ford and they had quite a long training session about Mob Programming. 

That's when a whole team of tech professionals work around one computer and there may be testers, developers, software architects, people in operations all contributing to the same team. 

A company like Ford invested in that training, to be more efficient with producing cars with good software built in, even though intuitively, you may think 5 people working on one computer would be slower. 

## Brief

Simon and I are going to work through a little demo just to showcase a little bit of pair programming, before we set you off. 

What I want to do is create a small game. 

I want to get information about different countries and the game is trying to guess the population. 

So if Simon and I are playing, first I'll pick a country. Then we'll both guess the population. The person furthest away, will have the difference added to their score. 

Then the other person will chose a country and we'll go until someone loses. 


## Execution

So what I want to do is actually start driving our application. 

I'm going to write some pseudocode down and whilst I'm doing that, Simon, do you mind finding an API we can use to get the population of different countries?

*Simon*: Yup, I'm on it. 


Alright, let me create a file. I think I can do all this from **main.py**.


**main.py**
```python
# Set player_one score to 0
# Set player_two score to 0

# Ask players for losing score
# Store losing score
```

Now I want my while loop. We only looked at while loops once but they're good when we don't know how many interations of the loop there'll be

My logic is that whilst both players score is less than the losing score the game continues. 

**main.py**
```python
# Set player_one score to 0
# Set player_two score to 0

# Ask players for losing score
# Store losing score

# While player_one and player_two score is less than losing score play game
```

Then within the loop I'm going to ask for both players to pick a country

**main.py**
```python
# Set player_one score to 0
# Set player_two score to 0

# Ask players for losing score
# Store losing score

# While player_one and player_two score is less than losing score play game
   # Get player one country choice
   # Call API to get player one country population

   # Ask both players for guesses

   # Calculate difference both players guesses were from country population
```

Then I think some simple control flow, to see who was further away and then add the difference of the losers score to their score

**main.py**
```python
# Set player_one score to 0
# Set player_two score to 0

# Ask players for losing score
# Store losing score

# While player_one and player_two score is less than losing score play game
   # Get player one country choice
   # Call API to get player one country population

   # Ask both players for guesses

   # Calculate difference both players guesses were from country population
   # If player one lost
      # Add to their score tally
   # Else
      # Add to player two tally
```

So after a round of the game, I want to print the scores and then check if anyone has lost. 

If they have break the loop and then announce the winner. 

If not, change the guesser for the next round.

*ASK SIMON*

By the way Simon, do you mind giving a little google to see if there's a way we can delay the terminal from spitting out output so it flows a bit more cleanly. 

**main.py**
```python
# 1. Get both player names
# 2. Set both scores to zero
# 3. Ask for the losing score
# 4. While game is live, let one player choose a country
# 5. Check the country is valid
# 6. Get the real population
# 7. Both players guess the population
# 8. Measure how wrong each guess is
# 9. The player who is more wrong gets penalty points
# 10. Show the updated scores
# 11. Swap turns
# 12. Keep going until someone reaches the losing score
# 13. The player with the smaller score wins
```

I think I'm ready to code this out. 

**main.py**
```python
player_one = input("Player one, enter your name").title()
player_one_score = 0

player_two = input("Player two, enter your name").title()
player_two_score = 0

losing_score = input("What should the losing score be? ")

# 4. While game is live, let one player choose a country
# 5. Check the country is valid
# 6. Get the real population
# 7. Both players guess the population
# 8. Measure how wrong each guess is
# 9. The player who is more wrong gets penalty points
# 10. Show the updated scores
# 11. Swap turns
# 12. Keep going until someone reaches the losing score
# 13. The player with the smaller score wins
```

*SIMON SAYS*: Remember to wrap the input with the **int()** function to convert the input into a integer

**main.py**
```python
player_one = input("Player one, enter your name").title()
player_one_score = 0

player_two = input("Player two, enter your name").title()
player_two_score = 0

losing_score = int(input("What should the losing score be? "))
```


Alright! Let's get into the while loop.

**main.py**
```python
player_one = input("Player one, enter your name").title()
player_one_score = 0

player_two = input("Player two, enter your name").title()
player_two_score = 0

losing_score = int(input("What should the losing score be? "))


while player_one_score < losing_score AND player_two_score < losing_score:

# 4. While game is live, let one player choose a country
# 5. Check the country is valid
# 6. Get the real population
# 7. Both players guess the population
# 8. Measure how wrong each guess is
# 9. The player who is more wrong gets penalty points
# 10. Show the updated scores
# 11. Swap turns
# 12. Keep going until someone reaches the losing score
# 13. The player with the smaller score wins
```

Now that I'm here, I'm actually struggling to think of a way, in the first game, I pick a country and then in the second round, Simon picks a country. 

Simon, sorry, do you mind find a way I can do that?

Also did you find an API I can use to find the population of different countries?

*SIMON*: I did! It's actually the API you used earlier in the week. 

*SIMON* Let me just paste that into the chat. 

*SIMON* The population is fairly deeply nested but assuming you'll parse from JSON, I'll also add in how you can dig into the data object. 

*SIMON SHARE*
```
https://restcountries.com/v3.1/name/{country}
```

```python
response = requests.get(f"https://restcountries.com/v3.1/name/{country}")
if response.status_code = 200:
    data = response.json()
    population = data[0]["population"]
```

Thanks Simon!

Ok, so that's pretty helpful. Instead of me having to stop my thought process, Simon's navigated through that potential blocker and found out how I can implement part of our project. 

I'll do this whilst hopefully Simon finds a way we can change the person to guess between each round. 

**main.py**
```python
player_one = input("Player one, enter your name").title()
player_one_score = 0

player_two = input("Player two, enter your name").title()
player_two_score = 0

losing_score = int(input("What should the losing score be? "))


while player_one_score < losing_score and player_two_score < losing_score:

    # NEW CODE
    country = input("What country are you selecting? ")
    response = requests.get(f"https://restcountries.com/v3.1/name/{country}")
    if response.status_code == 200:
        data = response.json()
        population = data[0]["population"]

    player_one_guess = input(f"{player_one}, what do you think the population of {country} is?")
    player_two_guess = input(f"{player_two}, what do you think the population of {country} is?")

    # 8. Measure how wrong each guess is
    # 9. The player who is more wrong gets penalty points
```

Slowly getting closer to the end goal. 

So to measure how wrong each guess is I basically need to take the population away from both answers. 

I showed you the **abs** method before, which returns the absolute value or any number flipped to positive. I'm using that because if I overestimate the population of a country or guess to low, that distance should always be a positive integer. 


**main.py**
```python
player_one = input("Player one, enter your name").title()
player_one_score = 0

player_two = input("Player two, enter your name").title()
player_two_score = 0

losing_score = int(input("What should the losing score be? "))


while player_one_score < losing_score and player_two_score < losing_score:

    country = input("What country are you selecting? ")
    response = requests.get(f"https://restcountries.com/v3.1/name/{country}")
    if response.status_code == 200:
        data = response.json()
        population = data[0]["population"]

    player_one_guess = input(f"{player_one}, what do you think the population of {country} is?")
    player_two_guess = input(f"{player_two}, what do you think the population of {country} is?")

    # NEW CODE
    player_one_round_score = abs(player_one_guess - population)
    player_two_round_score = abs(player_two_guess - population)

    print(f"The population of {country} is {population}")

    if player_one_round_score > player_two_round_score:
        print(f"{player_one} loses")
        player_one_score += player_one_round_score
    else:
        print(f"{player_two} loses")
        player_two_score += player_two_round_score


    # 10. Show the updated scores
    # 11. Swap turns
    # 12. Keep going until someone reaches the losing score
    # 13. The player with the smaller score wins
```

We're getting closer working through this psedudo code. Showing the scores is relatively easy. 


**main.py**
```python
player_one = input("Player one, enter your name").title()
player_one_score = 0

player_two = input("Player two, enter your name").title()
player_two_score = 0

losing_score = int(input("What should the losing score be? "))


while player_one_score < losing_score and player_two_score < losing_score:

    country = input("What country are you selecting? ")
    response = requests.get(f"https://restcountries.com/v3.1/name/{country}")
    if response.status_code == 200:
        data = response.json()
        population = data[0]["population"]

    player_one_guess = input(f"{player_one}, what do you think the population of {country} is?")
    player_two_guess = input(f"{player_two}, what do you think the population of {country} is?")

    player_one_round_score = abs(player_one_guess - population)
    player_two_round_score = abs(player_two_guess - population)

    print(f"The population of {country} is {population}")

    if player_one_round_score > player_two_round_score:
        player_one_score += player_one_round_score
        print(f"{player_one} loses")
    else:
        player_two_score += player_two_round_score
        print(f"{player_two} loses")


    # NEW CODE
    print(f"{player_one}'s current score is: {player_one_score}")
    print(f"{player_two}'s current score is: {player_two_score}")

    # 11. Swap turns
    # 12. Keep going until someone reaches the losing score
    # 13. The player with the smaller score wins
```

Now I need to think about the end game logic. 

So if either score is greater than the losing_score then the game is over. 

Our loop actually handles that logic so I'll print the winner outside the loop

**main.py**
```python
import requests

player_one = input("Player one, enter your name ").title()
player_one_score = 0

player_two = input("Player two, enter your name ").title()
player_two_score = 0

losing_score = int(input("What should the losing score be? "))


while player_one_score < losing_score and player_two_score < losing_score:

    country = input("What country are you selecting? ").lower()
    response = requests.get(f"https://restcountries.com/v3.1/name/{country}")
    if response.status_code == 200:
        data = response.json()
        population = data[0]["population"]

    player_one_guess = int(input(f"{player_one}, what do you think the population of {country} is? "))
    player_two_guess = int(input(f"{player_two}, what do you think the population of {country} is? "))

    player_one_round_score = abs(player_one_guess - population)
    player_two_round_score = abs(player_two_guess - population)

    print(f"The population of {country.title()} is {population}")

    if player_one_round_score > player_two_round_score:
        player_one_score += player_one_round_score
        print(f"{player_one} loses round")
    else:
        player_two_score += player_two_round_score
        print(f"{player_two} loses round")

    print(f"{player_one}, your score is {player_one_score}")
    print(f"{player_two}, your score is {player_two_score}")

    # 11. Swap turns
    # 12. Keep going until someone reaches the losing score

# NEW CODE
if player_one_score > player_two_score:
    print(f"{player_two} is the winner!")
else:
    print(f"{player_one} is the winner!")
```

Ok, so I think that looks pretty good! 

Simon, were you able to find a way to switch the person playing the game between each round?

*SIMON* I've done a little digging and it looks like people usually define a variable outside of the loop and then assign a player to that variable. 

*SIMON* Then a little bit of control flow at the bottom, if the value is one person, make it the other and if it's the other person, swap it again. 

Ahh, nice. Thanks Simon!

Let's try and impliment that. 

*SIMON* So after you've taken the input for the player names. I'd define a variable called `chooser` and assign the `player_one` to it. 

*SIMON* You can then use that value when you grab the country you're targetting, just above the API request

**main.py**
```python
import requests

player_one = input("Player one, enter your name ").title()
player_one_score = 0

player_two = input("Player two, enter your name ").title()
player_two_score = 0

losing_score = int(input("What should the losing score be? "))

# NEW CODE
chooser = player_one

while player_one_score < losing_score and player_two_score < losing_score:

    # UPDATED CODE
    country = input(f"{choser}, what country are you selecting? ").lower()
    response = requests.get(f"https://restcountries.com/v3.1/name/{country}")
    if response.status_code == 200:
        data = response.json()
        population = data[0]["population"]

    player_one_guess = int(input(f"{player_one}, what do you think the population of {country} is? "))
    player_two_guess = int(input(f"{player_two}, what do you think the population of {country} is? "))

    player_one_round_score = abs(player_one_guess - population)
    player_two_round_score = abs(player_two_guess - population)

    print(f"The population of {country.title()} is {population}")

    if player_one_round_score > player_two_round_score:
        player_one_score += player_one_round_score
        print(f"{player_one} loses round")
    else:
        player_two_score += player_two_round_score
        print(f"{player_two} loses round")

    print(f"{player_one}, your score is {player_one_score}")
    print(f"{player_two}, your score is {player_two_score}")
    

if player_one_score > player_two_score:
    print(f"{player_two} is the winner!")
```

*SIMON* Then at the end of the while loop, after you've printed both players score, then some control flow. 

*SIMON* If chooser is player one, then make chooser player two, else make chooser player one.

*SIMON* That way the logic updates which each round of the game. 

**main.py**
```python
import requests

player_one = input("Player one, enter your name ").title()
player_one_score = 0

player_two = input("Player two, enter your name ").title()
player_two_score = 0

losing_score = int(input("What should the losing score be? "))

chooser = player_one

while player_one_score < losing_score and player_two_score < losing_score:

    country = input(f"{choser}, what country are you selecting? ").lower()
    response = requests.get(f"https://restcountries.com/v3.1/name/{country}")
    if response.status_code == 200:
        data = response.json()
        population = data[0]["population"]

    player_one_guess = int(input(f"{player_one}, what do you think the population of {country} is? "))
    player_two_guess = int(input(f"{player_two}, what do you think the population of {country} is? "))

    player_one_round_score = abs(player_one_guess - population)
    player_two_round_score = abs(player_two_guess - population)

    print(f"The population of {country.title()} is {population}")

    if player_one_round_score > player_two_round_score:
        player_one_score += player_one_round_score
        print(f"{player_one} loses round")
    else:
        player_two_score += player_two_round_score
        print(f"{player_two} loses round")

    print(f"{player_one}, your score is {player_one_score}")
    print(f"{player_two}, your score is {player_two_score}")

    # NEW CODE
    if chooser == player_one:
        chooser = player_two
    else:
        chooser = player_two
    

if player_one_score > player_two_score:
    print(f"{player_two} is the winner!")
```



*SIMON* I've been thinking and it's also probably worth, wrapping a while loop around the API request, so we only continue the script if we've correctly inputted a country. 

*SIMON* Something like while True, try to make the API request and when you've got the population for a country, then break out of the loop. 

*SIMON* Then define an else block if the population isn't there just to reset to loop. 

**main.py**
```python
import requests

player_one = input("Player one, enter your name ").title()
player_one_score = 0

player_two = input("Player two, enter your name ").title()
player_two_score = 0

losing_score = int(input("What should the losing score be? "))

chooser = player_one

while player_one_score < losing_score and player_two_score < losing_score:

    # NEW CODE
    while True:
        country = input(f"{chooser}, what country are you selecting? ").lower()
        response = requests.get(f"https://restcountries.com/v3.1/name/{country}")
        if response.status_code == 200:
            data = response.json()
            population = data[0]["population"]
            # NEW CODE
            break
        # UPDATED CODE
        else:
            print(f"{country.title()} not found, please try again.")

    player_one_guess = int(input(f"{player_one}, what do you think the population of {country.title()} is? "))
    player_two_guess = int(input(f"{player_two}, what do you think the population of {country.title()} is? "))

    player_one_round_score = abs(player_one_guess - population)
    player_two_round_score = abs(player_two_guess - population)

    print(f"The population of {country.title()} is {population}")

    if player_one_round_score > player_two_round_score:
        player_one_score += player_one_round_score
        print(f"{player_one} loses round")
    else:
        player_two_score += player_two_round_score
        print(f"{player_two} loses round")

    print(f"{player_one}, your score is {player_one_score}")
    print(f"{player_two}, your score is {player_two_score}")
    
    if chooser == player_one:
        chooser = player_two
    else:
        chooser = player_one

if player_one_score > player_two_score:
    print(f"{player_two} is the winner!")
```


*SIMON* Actually Emile, looking at the code, one issue is that whoever player one is, will always guess the country first, which may be a disadvantage. 

*SIMON*, I think we could use the chooser logic again

*SIMON* If **chooser == player_one** then make player two guess first and an else statement for when it's not. 


*EMILE* I'm not sure I follow, what do you mean?

*SIMON* So after the inner while loop just write an if statement. 

*SIMON* If chooser == player one then get player two's input first, else first ones. 

*EMILE* Ahh ok, yeah that sounds good. Like this....:

**main.py**
```python
import requests

player_one = input("Player one, enter your name ").title()
player_one_score = 0

player_two = input("Player two, enter your name ").title()
player_two_score = 0

losing_score = int(input("What should the losing score be? "))

chooser = player_one

while player_one_score < losing_score and player_two_score < losing_score:

    while True:
        country = input(f"{chooser}, what country are you selecting? ").lower()
        response = requests.get(f"https://restcountries.com/v3.1/name/{country}")
        if response.status_code == 200:
            data = response.json()
            population = data[0]["population"]
            break
        else:
            print(f"{country.title()} not found, please try again.")

    # NEW CODE
    if chooser == player_one:
        player_two_guess = int(input(f"{player_two}, what do you think the population of {country.title()} is? "))
        player_one_guess = int(input(f"{player_one}, what do you think the population of {country.title()} is? "))
    else:
        player_one_guess = int(input(f"{player_one}, what do you think the population of {country.title()} is? "))
        player_two_guess = int(input(f"{player_two}, what do you think the population of {country.title()} is? "))

    player_one_round_score = abs(player_one_guess - population)
    player_two_round_score = abs(player_two_guess - population)

    print(f"The population of {country.title()} is {population}")

    if player_one_round_score > player_two_round_score:
        player_one_score += player_one_round_score
        print(f"{player_one} loses round")
    else:
        player_two_score += player_two_round_score
        print(f"{player_two} loses round")

    print(f"{player_one}, your score is {player_one_score}")
    print(f"{player_two}, your score is {player_two_score}")
    
    if chooser == player_one:
        chooser = player_two
    else:
        chooser = player_one

if player_one_score > player_two_score:
    print(f"{player_two} is the winner!")
```

That's actually really good. 

Ok! How about the timer thing to delay the output?

*SIMON* Yeah, theres a module called **time** with a method called **sleep** attached, you just need to give a number inside the argument to sleep and that'll be the number of seconds delay. 

*SIMON* I'll add a link to the chat. 

*EMILE OPENS LINK*

https://www.geeksforgeeks.org/python/sleep-in-python/

Ok, that looks good. I reckon I'll use this a few times. So let me actually do this in a function. 

**main.py**
```python
import requests
# NEW CODE
import time

# NEW CODE
def wait(delay):
    print("")
    print("")
    time.sleep(delay)

player_one = input("Player one, enter your name: ").title()
player_one_score = 0

player_two = input("Player two, enter your name: ").title()
player_two_score = 0

losing_score = int(input("What should the losing score be? "))

chooser = player_one

while player_one_score < losing_score and player_two_score < losing_score:

    while True:
        country = input(f"{chooser}, what country are you selecting? ").lower()
        response = requests.get(f"https://restcountries.com/v3.1/name/{country}")
        if response.status_code == 200:
            data = response.json()
            population = data[0]["population"]
            break
        else:
            print(f"{country.title()} not found, please try again.")

    # NEW CODE
    wait(1)
    if chooser == player_one:
        player_two_guess = int(input(f"{player_two}, what do you think the population of {country.title()} is? "))
        player_one_guess = int(input(f"{player_one}, what do you think the population of {country.title()} is? "))
    else:
        player_one_guess = int(input(f"{player_one}, what do you think the population of {country.title()} is? "))
        player_two_guess = int(input(f"{player_two}, what do you think the population of {country.title()} is? "))

    player_one_round_score = abs(player_one_guess - population)
    player_two_round_score = abs(player_two_guess - population)
    
    # NEW CODE
    wait(2)
    print(f"The population of {country.title()} is {population}")

    if player_one_round_score > player_two_round_score:
        player_one_score += player_one_round_score
        print(f"{player_one} loses round by: {player_one_round_score}")
    else:
        player_two_score += player_two_round_score
        print(f"{player_two} loses round by: {player_two_round_score}")

    # NEW CODE
    wait(1)
    print(f"{player_one}, your score is {player_one_score}/{losing_score}")
    print(f"{player_two}, your score is {player_two_score}/{losing_score}")
    
    if chooser == player_one:
        chooser = player_two
    else:
        chooser = player_one

if player_one_score > player_two_score:
    print(f"{player_two} is the winner!")
else: 
    print(f"{player_one} is the winner!")
```

Ok cool, I think that game logic is looking pretty strong. 

Let's try and play it. 

*PLAY GAME*

I actually think it's good. Something I didn't anticipate was that it's actually quite hard to read the numbers as I write them in or see them visualised. 

I do recall seeing a few techniques which will basically format the numbers so they're easier to read, basically adding in a comma after every 3 digits.

It's by adding a colon and a comma, following every integer


**main.py**
```python
import requests
import time

def wait(delay):
    print("")
    print("")
    time.sleep(delay)

player_one = input("Player one, enter your name: ").title()
player_one_score = 0

player_two = input("Player two, enter your name: ").title()
player_two_score = 0

losing_score = int(input("What should the losing score be? "))

chooser = player_one

while player_one_score < losing_score and player_two_score < losing_score:

    while True:
        country = input(f"{chooser}, what country are you selecting? ").lower()
        response = requests.get(f"https://restcountries.com/v3.1/name/{country}")
        if response.status_code == 200:
            data = response.json()
            population = data[0]["population"]
            break
        else:
            print(f"{country.title()} not found, please try again.")

    wait(1)
    if chooser == player_one:
        player_two_guess = int(input(f"{player_two}, what do you think the population of {country.title()} is? "))
        player_one_guess = int(input(f"{player_one}, what do you think the population of {country.title()} is? "))
    else:
        player_one_guess = int(input(f"{player_one}, what do you think the population of {country.title()} is? "))
        player_two_guess = int(input(f"{player_two}, what do you think the population of {country.title()} is? "))

    player_one_round_score = abs(player_one_guess - population)
    player_two_round_score = abs(player_two_guess - population)
    
    
    wait(2)
    # UPDATED CODE
    print(f"The population of {country.title()} is {population:,}")

    if player_one_round_score > player_two_round_score:
        player_one_score += player_one_round_score
        # UPDATED CODE
        print(f"{player_one} loses round by: {player_one_round_score:,}")
    else:
        player_two_score += player_two_round_score
        # UPDATED CODE
        print(f"{player_two} loses round by: {player_two_round_score:,}")

    wait(1)
    # UPDATED CODE
    print(f"{player_one}, your score is {player_one_score:,}/{losing_score:,}")
    # UPDATED CODE
    print(f"{player_two}, your score is {player_two_score:,}/{losing_score:,}")
    
    if chooser == player_one:
        chooser = player_two
    else:
        chooser = player_one

if player_one_score > player_two_score:
    print(f"{player_two} is the winner!")
else: 
    print(f"{player_one} is the winner!")
```

*SIMON* Equally Emile you could do the same thing on each input. 

*SIMON* String method replace, where you target a comma and then just remove it

*EMILE* Ahh, that is a good idea

**main.py**
```python
import requests
import time

def wait(delay):
    print("")
    print("")
    time.sleep(delay)

player_one = input("Player one, enter your name: ").title()
player_one_score = 0

player_two = input("Player two, enter your name: ").title()
player_two_score = 0

# UPDATED CODE
losing_score = int(input("What should the losing score be? ").replace(",", ""))

chooser = player_one

while player_one_score < losing_score and player_two_score < losing_score:

    while True:
        country = input(f"{chooser}, what country are you selecting? ").lower()
        response = requests.get(f"https://restcountries.com/v3.1/name/{country}")
        if response.status_code == 200:
            data = response.json()
            population = data[0]["population"]
            break
        else:
            print(f"{country.title()} not found, please try again.")

    wait(1)
    if chooser == player_one:
        # UPDATED CODE
        player_two_guess = int(input(f"{player_two}, what do you think the population of {country.title()} is? ").replace(",", ""))
        # UPDATED CODE
        player_one_guess = int(input(f"{player_one}, what do you think the population of {country.title()} is? ").replace(",", ""))
    else:
        # UPDATED CODE
        player_one_guess = int(input(f"{player_one}, what do you think the population of {country.title()} is? ").replace(",", ""))
        # UPDATED CODE
        player_two_guess = int(input(f"{player_two}, what do you think the population of {country.title()} is? ").replace(",", ""))

    player_one_round_score = abs(player_one_guess - population)
    player_two_round_score = abs(player_two_guess - population)
    
    
    wait(2)
    print(f"The population of {country.title()} is {population:,}")

    if player_one_round_score > player_two_round_score:
        player_one_score += player_one_round_score
        print(f"{player_one} loses round by: {player_one_round_score:,}")
    else:
        player_two_score += player_two_round_score
        print(f"{player_two} loses round by: {player_two_round_score:,}")

    wait(1)
    print(f"{player_one}, your score is {player_one_score:,}/{losing_score:,}")
    print(f"{player_two}, your score is {player_two_score:,}/{losing_score:,}")
    
    if chooser == player_one:
        chooser = player_two
    else:
        chooser = player_one

if player_one_score > player_two_score:
    print(f"{player_two} is the winner!")
else: 
    print(f"{player_one} is the winner!")
```






So that's a little taste of pair programming. It doesn't mean you won't get bugs, nor will it mean you suddenly can build complicated applications in a morning. 

What we've planned for the rest of the day is a hackathon, where you'll be using the TFL api and hopefully creating some files. 

We're going to do this in pairs and actually, it should be really helpful, just to get you talking about code outloud. 

I have two options for you, a beginner option and a more advanced option. 

Both ultimately try to achieve a similar thing but the advanced choice asks you to think a little more about OOP and there's an element of XML in there, which the beginner choice doesn't. 

I'll share the briefs for both of them with you, then I'll take you through them.

Beginner Hackathon MD: https://gist.github.com/emilesherrott/7c9f53be9e9b94fdbcb51d5e5c940019

Advacned Hackathon MD: https://gist.github.com/emilesherrott/63db1896a70368509167ffaf0c349106

*GO THROUGH BRIEFS*

My advice would be if the advanced one sounds difficult, go for the beginner and if you complete that relatively early, you can always try to adapt the program to encorporate some of the advanced features. 

Fair warning, you'll need to read documentation and you'll most likely need to be googling a few things.

Simon and I are here to offer help if needed and I do have a solution for the advanced brief I'll share with the group as well. 

Any questions?

---

Ok, please do structure the time for yourself. We'll come back at 12:00 and maybe, invite anyone to share their code. 
