# SAS procs and other functions in Python
A beginner's attempt at recreating SAS's statistical report generation PROCs in Python amongst others.

# Tabulation Function updates have been stopped in favor of creating the "SAS procs all-in-one" function

# A - 1 Tabulation Function v1.0

This function was created as a way of making the process of creating a pivot table as simple as possible for people who are absolute beginners with Python. I am very well aware that .pivot_table() and crosstab() are already straightforward enough as it is, but in my case I've encountered people who constantly forget how to utilize .pivot_table().

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

# B. Proc Freq in Python v1.0

These are very crude functions that I made as early attempts to recreate Proc Freq in Python. Neither of these functions have the capability to replicate some of the more advanced capabilities of Proc Freq which is why I plan on combining these two functions and adding some bells and whistles to the function to get a 1-to-1 replication of Proc Freq in Python. 

# C. SAS procs all-in-one v1.0

This is a function that is designed to make the production of SAS-style statistics reports as simple as typing in variable names. This function is once again, aimed at assisting SAS Users (specifically my colleagues) in creating SAS-style statistics reports. This version of the function lacks many of the quality-of-life changes that I implemented in Tabulation Function v5.0 such as the redo commands, kill switches, error messages and so forth. All of these will be implemented after I figure out the base functions themselves.

# C-1 PROC MEANS

PROC MEANS is simulated through the use of the .describe() function, albeit with percentiles 10, 20, 30, 40, 50, 60, 70, 80, 90, and 100 enabled. This report is relatively simple to produce so no caveats here.

# C-2 PROC UNIVARIATE

PROC UNIVARIATE is simulated through the use of the .profile_report() function imported from pandas_profiling. The module itself seems to be relatively unknown amongst by colleagues which is why I decided to include a message that tells users to install pandas_profiling. Many thanks to Lukas Frei at Medium for the following article.

https://towardsdatascience.com/speed-up-your-exploratory-data-analysis-with-pandas-profiling-88b33dc53625

The inner workings of .profile_report() is not something that I have worked out for myself, but the use of .profile_report() is relatively straightforward much like .describe(), which is why I will not be going into much detail here.

# C-3 PROC CORR

PROC CORR proved to be a bit trickier than the other functions to create as while plotting a simple correlation matrix is a simple matter using .corr(), replicating PROC CORR's output the way SAS does with Variables, N, Mean, Std, Sum, Min, Max and Correlation to a target variable was not possible using such simple functions which is why I decided to make the function the way I did (as in creating the necessary columns one by one and adding them to the final table). I've also managed to implement a method of taking in numerical variables and dropping character variables from the output table, though the method may require some refinement. 

# C-4 PROC TABULATE

PROC TABULATE is probably the most complicated function to implement in this instance which is why it is currently missing from the code. I will be incorporating the entirety of the previous tabulation function I made while also making some improvements to the overall thing itself. To be fair, it is not the act of creating the table that is complicated but rather the process of making it as easy to use and intuitive as possible that makes it complicated as evidenced in the number of .input() and ifs / elifs that I used in the code. 

# C-5 PROC FREQ

While PROC FREQ was another function that I had to make myself, it was relatively easy to make compared to PROC CORR and PROC TABULATE. This statement only holds true to PROC FREQ for single variables however, which is what I have done up to this point. I plan on adding an option for cross-tabulations in the PROC FREQ section, which will most likely be a modified version of the PROC TABULATE code block. 

# D. Data Selection Function_v1.0

This is a crude variable selection function that I created for fun. It's basically a way of separating variables into numerical and character types. While select_dtype is by far a better choice when it comes to data separation, I simply wanted to know if my method of selecting data was actually possible or not. This logic behind this function is to convert the result of df.dtypes into a dataset (as expressed in code as datatype_1 and datatype_2), filter variables by variable type and use the remaining variables to filter the data table. 

I only had numerical and character variable types in mind when I wrote this function. Options for other datatypes will be added in future updates.


