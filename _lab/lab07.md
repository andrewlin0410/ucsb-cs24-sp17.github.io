---
layout: lab
num: lab07
ready: false 
desc: "Recursion"
assigned: 2017-05-23 09:00:00.00-7
due: 2017-05-23 23:59:59.00-7
---

# Goals for this lab

By the time you have completed this lab, you should be able to

* Recognize key features of recursive solutions
* Write simple recursive functions
* Extend/modify recursive functions

# Step by Step Instructions

Step 1: Create a lab08 directory (in the first pilot's account)

First get together with your lab partner. If your regular partner is more than 5 minutes late, ask the TA to pair you with someone else for this week.

Select a pilot, log in, create a ~/cs24/lab08 directory, and make it your current directory.

Step 2: Get a copy of the necessary program files

There are just two required files to copy from the class account this week. You can copy them both at once as follows:

-bash-4.3$ cp ~cs24/labs/lab08/*.cpp ~/cs24/lab08/
-bash-4.3$ ls
alph.cpp  triangles.cpp
Step 3: Learn the features of a recursive function

Every recursive function must (a) have a base case; (b) have recursive calls that converge on the base case; and (c) actually solve the given problem. In this lab step, you will learn about a recursive printing function with two base cases; later you will write similar functions.

Examine the completed function, alph, in alph.cpp. Then answer the following questions about this function, jotting down your answers on paper (or at least being sure to remember them).

What are the two base cases?
How can you be sure that every recursive call gets closer to the base case(s)?
Does this function actually solve the problem - for example, will alph('d') print "abcd" as it should?
Compile and run it to test (as usual, user input is bold):

-bash-4.3$ make alph
g++     alph.cpp   -o alph
-bash-4.3$ ./alph
enter letter:
k
abcdefghijk
Before continuing, test boundary and null cases such as alph('a') and alph('B'), respectively. Any others?
Step 4: Implement three similar recursive functions

Now - one at a time - implement the other three functions in alph.cpp. All must be done using recursion (you may not use any loop structures).

ralph - prints the alphabetic sequence in reverse, starting with the character passed to it, and ending with 'a' (all of these functions do nothing if the argument passed is not a lower case character).
zalph - prints the alphabetic sequence that starts with the character passed to it, and ends with 'z'.
zralph - prints the alphabetic sequence in reverse, starting with 'z' and ending with the character passed to it.
Here is a complete run from our solution - functions are called in this order: alph, ralph, zalph, zralph
-bash-4.3$ ./alph
enter letter:
r
abcdefghijklmnopqr
rqponmlkjihgfedcba
rstuvwxyz
zyxwvutsr
Step 5: More recursive functions, and using one to help another one

First: switch roles between pilot and navigator if you did not already do that.

You must use recursion for all of the following tasks - no loop structures at all. Check the results of each part before going on to the next part.

Turn your attention now to the other program skeleton, triangles.cpp. When you finish implementing all three functions, your results should match the following (if user enters 3):

-bash-4.3$ ./triangles
enter size:
3
***
**
*
*
**
***
It is a crude print drawing of two triangles, each of the size specified by the user. Here is a run with size 20.
Implement function stars first. This function should print a star (actually an asterisk, '*'), and call itself as many times as necessary to print exactly the number of stars specified in the initial call. If you don't change main yet, then compile triangles.cpp and run it, your output should match the following runs:

-bash-4.3$ make triangles
g++     triangles.cpp   -o triangles
-bash-4.3$ ./triangles
enter size:
7
*******-bash-4.3$ ./triangles
enter size:
4
****-bash-4.3$
Don't worry about the lack of a newline, as that will be handled by the other functions.
Now implement triangle to print n rows of stars, the first row has n stars, the second has n-1, and the last row has one star. Use the stars function to print each row, and then print a newline at the end of the row.

To test it, edit the main function of triangles.cpp by deleting (or commenting out) the call to stars. Then remove the // from in front of the call to triangle, and recompile. Your results should match the top half of the complete results above.

Finally, implement rtriangle to print the rows of stars in reverse order, one star first, and n stars last. Match the bottom half of the complete results. To test, remove the // from in front of the call to rtriangle in main and compile again.

Step 6: Submit your revised alph.cpp and triangles.cpp

Submit Lab08 at https://submit.cs.ucsb.edu/, or use the following command from a CS terminal:

~submit/submit -p 599 alph.cpp triangles.cpp
If you are working with a partner, be sure that both partners' names are in a comment at the top of the source code files, and be sure to properly form a group for this project in the submit.cs system.

50/50 is a perfect score.

Evaluation and Grading

Each student must accomplish the following to earn full credit [50 total points] for this lab:

[25 points] alph.cpp is saved, it has your name(s) in a comment at the top, all of the required functions are implemented recursively, it compiles and executes properly, and scores 25 on the submit.cs system tests.
[25 points] triangles.cpp is saved, it has your name(s) in a comment at the top, all of the required functions are implemented recursively, it compiles and executes properly, and scores 25 on the submit.cs system tests.
[-0 to -50 points, at the TA's discretion] The student arrived on time to their lab session, and worked diligently on CS24-related material until dismissed.
This lab is due by 11:59 pm tomorrow night.
Optional Extra Challenge

Don't change triangles.cpp, but copy it to another file (e.g., tri2.cpp), and make some changes to the copy, such as the following:

Make an improved version of stars named chars that takes two arguments, the character to print (not always just an asterisk) and the number of such chars to print. Test it by replacing the calls to stars in one of your triangle implementations.
Improve the triangle functions to take those same two arguments, and thereby print triangles made of any character, not just asterisks.
Assuming you already made the first two changes above, change main to get the character to print from the user, and then test the entire system.
Can you figure out how to change the triangle functions so the triangles are right-justified instead of left as in the following?
***
 **
  *
  *
 **
***
Do you have to use some iteration instead of just recursion to make this work, or at least must you add additional parameters to the triangle functions?
Prepared by Michael Costanzo.