# SAS-procs-in-Python
A beginner's attempt at recreating SAS's statistical report generation PROCs in Python amongst others.

# A - 1 Tabulation Function v1.0

This function was created as a way of making the process of creating a pivot table as simple as possible for people who are absolute beginners with Python. I am very well aware that .pivot_table() and crosstab() are already straightforward enough as it is, but in my case I've encountered people who constantly forget how to utilize .pivot_table() (mostly people who are unfamiliar with Pandas or Python in general. I work at a company that heavily relies on SAS). 

My goal is to make it as straightforward as possible for non-Python users to create a pivot table, hence the detailed instructions. That being said, I have also added an extra function in the code that is designed to replicate PROC FREQ if the user inputs a character variable in the row option. 

As of now I haven't fixed a tiny error that I made where it says the user can use multiple columns / indexes when this is obviously not the case. I intend to fix this problem in v2.0.

Besides the aforementioned reasons this function was made as a way to test my own abilities in Python as I'm still very inexperienced.

# A - 2 Tabulation Function v2.0

Major changes:
1. An added list of common misspellings for Yes/No questions and changes to the way the answers for Yes/No questions are interpreted 
2. Added another redirection function to proc freq. Activates when the index and column variables are identical.

Minor changes:
1. Some variable names were changed to accommodate new logic

Planned changes:
1. I apparently forgot to fix the problem where analysis of multiple variables returns an error. I will try to remedy that in v3.0.

# A - 3 Tabulation Function v3.0

Major changes:
1. List of aggregation functions were added to ensure that users are using the correct functions.
2. Added error messages to yes/no questions to ensure that users always answer with a yes or a no.

Minor changes:
1. Made a slight change to the no_answers list to include "NO" as well (was not included in v2.0)

Planned changes:
1. Have yet to make any progress on the multiple variables problem.

# A - 4 Tabulation Function v4.0

Major changes:
1. Added a confirmation option that prints out the final table. Once final table parameters are confirmed, inputting "yes" in the final input window will print the table, whereas if "no" is inputted, the function will restart from the beginning.

Planned changes:
1. Add in the option to analyze multiple variables.
2. Add in a redo function that allows user to restart the function from the beginning if deemed necessary.

# A - 5 Tabulation Function v5.0

Major changes:
1. Added a kill command and redo command for all input windows in the function.
2. Added new lists for new commands.

Minor changes:
1. Re-adjusted message format to make it easier to read.

Planned Changes:
1. Add in the option to analyze multiple variables.

# B. Proc Freq in Python (Current Version: 1.0)

These are very crude functions that I made as early attempts to recreate Proc Freq in Python. Neither of these functions have the capability to replicate some of the more advanced capabilities of Proc Freq which is why I plan on combining these two functions and adding some bells and whistles to the function to get a 1-to-1 replication of Proc Freq in Python. 

