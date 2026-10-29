# Lemon Clicker Bug Report

**Name:**
**Tickets solved:** <!-- e.g. 1, 2, 3, 5, 6 (at least five) -->

Copy the template below once for each ticket you solved. 

---

## Ticket <number>: <ticket title>


### Actual cause

<!-- Which file and function was the bug in, and what was wrong with the code?
     Explain why that code produced the behavior described in the ticket. -->

**File / function:**

**What was wrong:**

### Fix

<!-- What did you change, and why does that change fix the problem? -->

### How did you find it?

#### Hypothesis testing

**What hypothesis ultimately led you to identify the buggy code, and why?**

#### Backward tracing

<!-- Start from the symptom you saw and work backwards, one step at a time,
     until you reach the buggy line. For each step, note where you looked
     and what you saw there. Add steps as needed. -->

1. **Symptom:** <!-- what you saw, e.g. text on screen, console error -->
2. **Traced back to:** <!-- where that came from, e.g. a function, a request in the Network tab, a server log -->
3. **Traced back to:**
4. **Buggy code:** <!-- the file, function and line where the trace ended -->

<!-- It is okay to use your judgement here in limiting the number of traceback steps. We want to understand your 
    reasoning for how you discovered where the bug was -->

### Confirming the fix

<!-- How did you confirm the problem is gone? -->

Ticket 1: Stats always say "Stats unavailable"
In MenuScreenController.ts in the function loadStatsFromServer the api was being called wrong
I fixed it by changing it from api/stat to api/stats as that was the typo causing it to be called wrong
I found it by starting at the MenuScreenController and looking through the code, then using ctrl f I looked for the API endpoint and noticed it was mistyped
The API endpoint is being called wrong
I saw the API endpoint referenced in MenuScreenController, I traced it back to the actual API and saw the name was different and then fixed the typo

Ticket 2: Best score always shows 0
In index.ts the the API endpoint for getting the stats, the if statement logic was wrong
I fixed it by changing entries[i].score > best, since when it was the other way around it wasn't comparing the values properly
I found it by starting off at the updateStats function in MenuScreenView.ts and then using ctrl f to find where best was being defined and fixed it fromthere 
The if statement was giving incorrect logic
I saw best being referenced in MenuScreenView.ts and then traced it back to where best was being defined and fixed the if statement logic

Ticket 3: The lemon only lands in four spots
In GameScreenView.ts the randomizelemonposition function wasnt generating random values properly
I fixed it by fixing the parameters for the math.random equation as originally the parameters weren't inside the paranthases so a random value wasnt actually generated
I found it by searching up random as I assumed something was wrong with the math.random line
The math.random function wasn't handling its parameters properly
I realized there was an issue with Math.random so I did ctrl f to find random and found the function that handled randomizing lemon position and fixed the paranthases so the parameters were included

Ticket 4: Stuck on the Game Over screen
In GameScreenController.ts the the function stopTimer wasn't being referenced properly, causing the game to stay stuck on the GameOver screen
I fixed it by adding the () to the this.stopTimer as it is a function so it needs the paranthases
I found it by originally going through the gameOver references to see where it was being called and if it was being called too much, then going through the rest of the code in the file I spotted the syntax error
The function stopTimer wasnt being called properly
I realized there. was an issue with gameOver and looked through the entire file and then spotted the syntax error, and fixed it by adding the paranthases so the function was being called properly

Ticket 5: Leaderboard dates show "undefined"
In index.ts the variable was defined as time where everywhere else it was defined as timestamp causing an error in displaying date andtime
I fixed it by changing the variable time to be called timestamp
I found it by initially going to the ResultScreenView.ts file to find the updateLeaderboard function where it said timestamp, then searching to see where the variable timestamp was even defined and found it wasnt defined anywhere so I found time being defined with the proper date and time
The variable timestamp wasnt defined anywhere
I realized there was an issue with the definition of the date and time processing/displaying, i fixed it by changing the name to timestamp in index.ts so the value was being processed properly



