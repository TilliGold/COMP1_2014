#Task Sheet 1 - Validation Improvements

##Introduction
This series of tasks focuses on validation i.e. ensuring that the values entered by the user are correct and that the interface of the program is user friendly.

##Task 1 - Improving card selection input
The function **`GetChoiceFromUser()`** is responsible for asking the user to decide whether the next card is going to be higher than the current card. The user enters either **y** or **n** as their choice.

Currently the program will not except **Y**, **Yes**, **yes**, **N**, **No** or **no** as acceptable input:

![][1]

**Improve** the function so that all of these additional values are considered as acceptable input.

![](https://www.dropbox.com/s/4ugdh9vc2isv87q/s1.PNG?dl=1)

![](https://www.dropbox.com/s/lc9puhe7m4q1ssu/s3.PNG?dl=1)

##Task 2 - Improving menu choice input
The function **`GetMenuChoice()`** is responsible for asking the user to enter their choice from the main program menu. Only the **first character** of this input is required as the available choices are:

- q
- 1
- 2
- 3
- 4

Currently the program will reject the user entering **Q** or **Quit** for instance. **Improve** this function so all of these values are recognised as being equivalent to **q**.

![](https://www.dropbox.com/s/x8sqbrexl38edmi/s2.PNG?dl=1)

![](https://www.dropbox.com/s/wl9gqveogcksyh3/s4.PNG?dl=1)

##Task 3(a) - Validating the name for a recent score
When you complete a game you will be asked to add your score to the list of most recent scores. To do this you need to enter your name - the program **should** work as follows:

![][2]

1. The user is asked for their name.
2. If they attempt to leave the name blank they are then prompted repeatedly, until they enter something as their name.

###Questions
**Answer** the following questions:

1. Which function is responsible for getting the name from the user? **GetPlayerName**
2. How will you ensure that the user is asked for the name repeatedly? **By using a while loop that continuously asks for the players name until one is entered.**
3. What additional variable will you need and what will its datatype be? **A second PlayerName variable, with string datatype.**

###Pseudo-code
Write the function identified above in pseudo-code with the improvements necessary to prevent the user leaving their name blank.

Input PlayerName

while user has not entered name

  print "You must enter something for your name"
  
  input PlayerName
  
Return PlayerName

###Program code
Use the pseudo-code created above to help you improve the actual program code.

![](https://www.dropbox.com/s/5e2nwt1ovtz8zmb/hww.PNG?dl=1)

![](https://www.dropbox.com/s/fn5qrjs23yno3w9/s5.PNG?dl=1)

##Task 3(b) - Deciding whether you want to add your name to the recent score table
Some users are not keen on adding their name to high score tables - they want to play the game but remain anonymous. Before being asked for their name they should be allowed to decide whether they want to add their name to the recent score table:

![][3]

###Questions
**Answer** the following questions:

1. Which function is responsible for adding scores to the table? **UpdateRecentScores**

###Program code
**Improve** the function identified above so that the user has the choice of whether to add their name to the high score table or not.

![](https://www.dropbox.com/s/6qibg3xn3kuigow/s6.PNG?dl=1)

![](https://www.dropbox.com/s/aljfix5w8dkuvhr/s7.PNG?dl=1)

##Task 4 - Formatting the recent score table
Currently the formatting of the recent score table is quite poor:

![][4]

It would be better if it looked like this:

![][5]

**Find** the function responsible for generating the recent score table and **improve** it so that the scores are displayed in a clear tabular format.

![](https://www.dropbox.com/s/2m26nn5tksmfadu/s8.PNG?dl=1)

##Task 5 - Adding a date to the recent scores
One improvement that we can make is to record the date a high score was achieved. This will involve making changes in **four** functions of the program and **importing** an additional module.

###Questions
**Answer** the following questions:

1. What additional module will you need to import into the program? **import datetime**
2. Identify the four functions that will require changes. **ResetRecentScores, DisplayRecentScores, UpdateRecentScores, PlayGame**
3. How do you convert a string in the format DD/MM/YY (e.g. 14/08/93) to a **date** type in Python? **dob = 18/03/1998 datetime.strptime(dob, "%d,%m,%Y")**

###Program code
**Make** the necessary changes to the program so that the date can be stored along with the rest of the of the recent score details. **Ensure** that when the score is displayed that it is in the **format DD/MM/YY**.

![](https://www.dropbox.com/s/fw7pj23p4sg0z2y/s9.PNG?dl=1)

![](https://www.dropbox.com/s/78os3807b2awmha/s10.PNG?dl=1)

##Additional Task - Variable roles
Section B of the COMP1 exam focuses on your understanding of the program source code. Often the questions will focus on the **role of variables** in the program. There are several different roles that a variable can have: they are described on **page 66** of the AS textbook.

###Questions
**Answer** the following questions:

1. Describe each variable role in **your own words**.

|**Variable role**|**Description**|
|-----------------|---------------|
|Fixed value|A variable initialised with ay calculation and without being changed (eg remembering the number of array elements in use).|
|Stepper|A variable going through a series of systematic, predictable values (eg during iteration a variable used to keep pcount of a number of repetiitions).|
|Most recent holder|A variable holding the latest value encountered when processing a series of unpredictable values or the latest value obtained as input.|
|Gatherer|A variable accumulating the effect of individual values (eg when calculates a new set of values, it keeps a running total of all values added so far).|
|Transformation|A variable that always gets its ew value from a fixed calculation of values of other variables (eg storing the result of a measurement conversion).|
|Follower|A variable that gets its new value from the old value of another data item.|
|Temporary|A variable holding some value for a short time only.|

2. Give an example of variable from the program code for each variable role.

##Additional Task - Functions and parameters
When **binding** arguments to parameters they are passed into the function either *by value* or *by reference*. In some programming languages you can specify which method to use but in Python this is done automatically for you. Some values are passed by value and others by reference - it depends on the value's **data type**.

|**Data Type**|**Passing Mechanism**|
|-------------|---------------------|
|Integer|by value|
|Float|by value|
|String|by value|
|Boolean|by value|
|List|by reference|
|Record|by reference|

The AS textbook has a good section on passing by value and passing by reference on **pages 63 to 65**.

##Questions
**Answer** the following questions:

1. Describe the difference between passing by value and passing by reference in **your own words**. **Passing by value is where a copy of the original value of the variable is stored in memory, whereas passing by reference is where the actual value of the variable is stored in memory.**
2. For each function in the program identify the mechanism using to pass each parameter. **Note**: this task will take a while but it will improve your understanding of the program and be useful for the exam.

|**Function**|**Mechanism**|
|------------|-------------|
|RankNo|by value|
|SuitNo|by value|
|LoadDeck|by reference|
|ShuffleDeck|by reference|
|DisplayCard|by reference|
|GetCard|by reference|
|IsNextCardHigher|by value|
|DisplayEndOfGameMessage|by value|
|DisplayCorrectGuessMessage|by value|
|ResetRecentScores|by value|
|DisplayRecentScores|by value|
|UpdateRecentScores|by value|
|PlayGame|by value and by reference|


##Next
This task sheet has focused on **validation**, the next set of tasks will involve making improvements to the actual game.




[1]: images/valid_yes_no_input.png
[2]: images/high_score_name.png
[3]: images/ask_for_name.png
[4]: images/high_score_table_old.png
[5]: images/high_score_table_new.png
