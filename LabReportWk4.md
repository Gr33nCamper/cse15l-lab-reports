Create another page in your lab report repository, like you did for lab report 1, and write your report there.

Pick three code changes that your group worked on in lab 3 in order to fix a bug; these should be stored as commits on someone’s repository. Fork the repository so you have your own copy with all the work your group did if you haven’t already.

For each of the three code changes:
Show a screenshot of the code change diff from Github (a page like this)

Link to the test file for a failure-inducing input that prompted you to make that change

Show the symptom of that failure-inducing input by showing the output of running the file at the command line for the version where it was failing (this should also be in the commit message history)

Write 2-3 sentences describing the relationship between the bug, the symptom, and the failure-inducing input.


You will submit this to the Lab Report 2 - Week 4 assignment on Gradescope, which will have a similar process to the first lab report for grading.

*Code Change 1 (Fixing output for empty test file)*

<a href="https://ibb.co/Prx3qD2"><img src="https://i.ibb.co/dfB18mN/Screen-Shot-2022-04-24-at-8-40-07-PM.png" alt="Screen-Shot-2022-04-24-at-8-40-07-PM" border="0"></a>
  
Additional condition added for the while loop to execute. 

&nbsp;

[Link to testing file for failure-inducing input](https://github.com/R3dbAbyVamp/markdown-parser/blob/main/testing3.md)

&nbsp;

<a href="https://ibb.co/zZfRz8k"><img src="https://i.ibb.co/bXdBkHf/string-index-OOB-error-for-empty-test-file.png" alt="string-index-OOB-error-for-empty-test-file" border="0"></a> 

Symptom: Running program throws StringIndexOutOfBoundsException  

Relation between bug, symptom, and failure-inducing input: The bug is that there is no code in the program to handle the case when the markdown file has no links at all (when the indices of the parentheses and brackets are all -1). So when the substring function is called, it tries to get a substring from 0 to -1 (the open parentheses index + 1 to the closing parentheses index). However, since all the indices must be at least 0 in java, -1 is considered out of bounds, resulting in the exception being thrown when calling MarkDownParse on the blank markdown test file.    

&nbsp;

*Code Change 2*


*Code Change 3*
