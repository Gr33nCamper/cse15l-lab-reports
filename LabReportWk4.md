# Lab Report 2: Code Changes

Some code changes to fix bugs from Lab 3 follow.

&nbsp;

*Code Change 1 (Fixing output for empty test file)*

<a href="https://ibb.co/Prx3qD2"><img src="https://i.ibb.co/dfB18mN/Screen-Shot-2022-04-24-at-8-40-07-PM.png" alt="Screen-Shot-2022-04-24-at-8-40-07-PM" border="0"></a>
  
(Added Condition: markdown file must contain open bracket for the while loop to execute) 

  
[Link to testing file for failure-inducing input](https://github.com/R3dbAbyVamp/markdown-parser/blob/main/testing3.md)

  
<a href="https://ibb.co/zZfRz8k"><img src="https://i.ibb.co/bXdBkHf/string-index-OOB-error-for-empty-test-file.png" alt="string-index-OOB-error-for-empty-test-file" border="0"></a> 

Symptom: Running program throws StringIndexOutOfBoundsException  

Explanation: The bug is that there is no code in the program to handle the case when the markdown file has no links at all (when the indices of the parentheses and brackets are all -1). So when the substring function is called, it tries to get a substring from 0 to -1 (the open parentheses index + 1 to the closing parentheses index). However, since all the indices must be at least 0 in java, -1 is considered out of bounds, resulting in the exception being thrown when calling MarkdownParse on the blank markdown test file.    

&nbsp;

*Code Change 2: Fixing output for parentheses inside parentheses*

<a href="https://ibb.co/w7SXfwR"><img src="https://i.ibb.co/FX5MF0K/Screen-Shot-2022-04-24-at-11-25-17-PM.png" alt="Screen-Shot-2022-04-24-at-11-25-17-PM" border="0"></a> 

(Added extra if-statement to check if the closing parentheses is actually the closing parentheses of interest)

[Link to testing file for failure-inducing input](https://github.com/R3dbAbyVamp/markdown-parser/blob/main/testing2.md)

<a href="https://ibb.co/GCqVDwt"><img src="https://i.ibb.co/r5VZhPc/Screen-Shot-2022-04-24-at-11-08-12-PM.png" alt="Screen-Shot-2022-04-24-at-11-08-12-PM" border="0"></a>

Symptom: Running program does not print out the first link fully

Explanation: The bug is that the program mistakes the earliest closing parentheses (of the parentheses embedded in the main parentheses) as the actual closing parentheses. However, there are actually more characters after that closing parentheses, which are skipped over when the program looks for the open bracket that follows the "decoy" closing parentheses. That is why calling MarkdownParse on the file with a link containing parentheses within parentheses results in an incomplete parse. 

&nbsp;

*Code Change 3: Fixing infinite loop* 

<a href="https://ibb.co/NS7r5X5"><img src="https://i.ibb.co/xH3YWyW/Screen-Shot-2022-04-24-at-11-57-45-PM.png" alt="Screen-Shot-2022-04-24-at-11-57-45-PM" border="0"></a>

(Added while loop to skip blanks)

<a href="https://ibb.co/dg6S5L6"><img src="https://i.ibb.co/6Bb2W1b/Screen-Shot-2022-04-24-at-11-44-46-PM.png" alt="Screen-Shot-2022-04-24-at-11-44-46-PM" border="0"></a> 


Symptom: Running program results in infinite loop 

[Link to testing file for failure-inducing input](https://github.com/R3dbAbyVamp/markdown-parser/blob/main/testingFive.md)

Explanation: The bug is that the program cannot the first index of the open parentheses since there are many new lines separating the links. Since it cannot find the segment containing the link, it remains stuck at the same index, without appending to the return ArrayList. 
