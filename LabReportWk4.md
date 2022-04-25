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
  
(Added Condition: markdown file must contain open bracket for the while loop to execute) 

  
[Link to testing file for failure-inducing input](https://github.com/R3dbAbyVamp/markdown-parser/blob/main/testing3.md)

  
<a href="https://ibb.co/zZfRz8k"><img src="https://i.ibb.co/bXdBkHf/string-index-OOB-error-for-empty-test-file.png" alt="string-index-OOB-error-for-empty-test-file" border="0"></a> 

Symptom: Running program throws StringIndexOutOfBoundsException  

Explanation: The bug is that there is no code in the program to handle the case when the markdown file has no links at all (when the indices of the parentheses and brackets are all -1). So when the substring function is called, it tries to get a substring from 0 to -1 (the open parentheses index + 1 to the closing parentheses index). However, since all the indices must be at least 0 in java, -1 is considered out of bounds, resulting in the exception being thrown when calling MarkdownParse on the blank markdown test file.    

&nbsp;

*Code Change 2: Fixing output for parentheses inside parentheses*

[Link to testing file for failure-inducing input](https://github.com/R3dbAbyVamp/markdown-parser/blob/main/testing2.md)

<a href="https://ibb.co/GCqVDwt"><img src="https://i.ibb.co/r5VZhPc/Screen-Shot-2022-04-24-at-11-08-12-PM.png" alt="Screen-Shot-2022-04-24-at-11-08-12-PM" border="0"></a>

Symptom: Running program does not print out the first link fully

Explanation: The bug is that the program mistakes the earliest closing parentheses (of the parentheses embedded in the main parentheses) as the actual closing parentheses. However, there are actually more characters following that closing parentheses, which are skipped over when the program looks for the opening bracket after finding what it thinks is the closing parentheses. That is why calling MarkdownParse on the file with a link containing parentheses within parentheses results in an incomplete parse.  

*Code Change 3*

[Link to testing file for failure-inducing input]()
