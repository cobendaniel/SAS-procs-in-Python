# SAS-procs-in-Python
A beginner's attempt at recreating SAS's statistical report generation PROCs in Python amongst others.

Function log:
1. Tabulation Function (Current Version: 1.0)

This function was created as a way of making the process of creating a pivot table as simple as possible for people who are absolute beginners with Python. I am very well aware that .pivot_table() and crosstab() are technically much easier than this, but in my case I've encountered people who constantly forget how to utilize .pivot_table() (mostly people who are unfamiliar with Pandas or Python in general. I work at a company that heavily relies on SAS). 

My goal is to make it as straightforward as possible for non-Python users to create a pivot table, hence the detailed instructions. That being said, I have also added an extra function in the code that is designed to replicate PROC FREQ if the user inputs a character variable in the row option. 

As of now I haven't fixed a tiny error that I made where it says the user can use multiple columns / indexes when this is obviously not the case. I intend to fix this problem in v2.0.

Besides the aforementioned reasons this function was made as a way to test my own abilities in Python as I'm still very inexperienced.
