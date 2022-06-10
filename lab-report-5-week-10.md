# Lab Report 5: Comparing MarkdownParse Implementations 

In lab 9, you experimented with the many tests provided under the test-files/ folder. For this lab report, choose any two tests from the 652 tests where your implementation (or a representative implementation from your group) had different answers than the implementation we provided for lab 9. The tests with different answers should correspond to different bugs – that is, you couldn’t easily fix both with one code change.

Note : 
Please use the command line to run MarkdownParse/tests instead of  the VSCode play button 
MarkdownParse.java in the code provided for lab 9 is not 100% correct and may have tests where expected output is different from actual output

&nbsp;

Explain:
How you found the tests with different results (Did you use vimdiff on the results of running a bash for loop? Did you search through manually? Did you use some other programmatic idea?)

Provide a link to the test-file with different-results (in the provided repository or your repository , either is fine)

For each test:
Describe which implementation is correct, or neither if both give the wrong output
Indicate both actual outputs (provide screenshots) and also what the expected output is (list the links that are expected in the output).

For the implementation that’s not correct (or choose one if both are incorrect), describe the bug (the problem in the code) in about 2-3 sentences. You don’t have to provide a fix, but you should be specific about what is wrong with the program, and show the code that should be fixed (Provide a screenshot of code and highlight where the change needs to be made).


**Test 1**
Used vimdiff on the results of running a bash for loop to find tests with different results. (Note: the bash script for my implementation led to an infinite loop for more than one of the tests, so the results.txt file did not include the results for all the test files).   

[Test-file 12 link](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/12.md)

Expected output: No links detected

<a href="https://ibb.co/Qjw8sy1"><img src="https://i.ibb.co/JFJxXDM/Screen-Shot-2022-06-09-at-5-03-40-PM.png" alt="Screen-Shot-2022-06-09-at-5-03-40-PM" border="0"></a> 

&nbsp;

Output from my implementation:

<a href="https://imgbb.com/"><img src="https://i.ibb.co/vmqv4Gk/Screen-Shot-2022-06-09-at-5-32-15-PM.png" alt="Screen-Shot-2022-06-09-at-5-32-15-PM" border="0"></a>

&nbsp;

Output from provided implementation:

<a href="https://imgbb.com/"><img src="https://i.ibb.co/Wky9BKm/Screen-Shot-2022-06-09-at-5-32-24-PM.png" alt="Screen-Shot-2022-06-09-at-5-32-24-PM" border="0"></a>

&nbsp;


The implementation provided for lab 9 is correct, since there are no links in the test file.

My implementation leads to an index out of bounds exception, so no links are generated and only one print statement shows. The reason for this is the program does not take into account the case where a closing parentheses after a "decoy" set of closing parentheses does not exist (We define decoy closing parentheses as closing parentheses which are not at the end of the markdown file or which are not followed by a newline character). So when it tries to add a substring from the previous open parentheses to the closing parentheses, which doesn't exist, it ends up calling the substring function from a valid index to -1, an invalid index.

What I should have done was check if the closeParen index was >= 0 before adding the substring containing that index to the return string. If not, then break out of the while loop, since no link can exist, unless there were brackets preceding it and which enclosed characters.
In fact, a better way would be to check for the existence of brackets before checking for the existence of parentheses. If no brackets exist, then we can skip forward, since no link can exist without brackets preceding parentheses. 

The replacement would have to be at line 80. 

<a href="https://ibb.co/v4TrL5c"><img src="https://i.ibb.co/d4V3k9f/Screen-Shot-2022-06-09-at-5-31-10-PM.png" alt="Screen-Shot-2022-06-09-at-5-31-10-PM" border="0"></a>

The larger change would have to be made after finding the bracket indices, but before finding the parentheses indices.

<a href="https://ibb.co/PrQjxtL"><img src="https://i.ibb.co/dfgMB7T/Screen-Shot-2022-06-09-at-5-51-11-PM.png" alt="Screen-Shot-2022-06-09-at-5-51-11-PM" border="0"></a>


&nbsp; 

&nbsp; 



**Test 2**

Used vimdiff on the results of running a bash for loop to find tests with different results. 

[Test-file 14 link](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/14.md)

Expected output: No links detected

<a href="https://ibb.co/p0y0KmP"><img src="https://i.ibb.co/Rvyv65S/Screen-Shot-2022-06-09-at-5-57-44-PM.png" alt="Screen-Shot-2022-06-09-at-5-57-44-PM" border="0"></a> 

&nbsp; 

Output from my implementation:

<a href="https://ibb.co/ZB2Sjt2"><img src="https://i.ibb.co/pfhQ7Gh/Screen-Shot-2022-06-09-at-5-59-49-PM.png" alt="Screen-Shot-2022-06-09-at-5-59-49-PM" border="0"></a>

&nbsp; 

Output from provided implementation: 

<a href="https://ibb.co/HYK2gZ6"><img src="https://i.ibb.co/QnJcm0L/Screen-Shot-2022-06-09-at-6-00-03-PM.png" alt="Screen-Shot-2022-06-09-at-6-00-03-PM" border="0"></a>

&nbsp; 

Neither implementation is correct. 

My implementation leads to an infinite loop. The provided implementation detects one link, when in fact no links exist.

The problem: The program never reaches the end of the markdown file. What I should have done was check if an initial open parentheses exists before checking for a closing parentheses, since a half pair of parentheses cannot enclose anything. And if it doesn't exist, this means either it doesn't exist, or the program did not recognize another existing open parentheses as a valid one. It keeps passing the index of the first open parentheses as -1.  

<a href="https://ibb.co/8YczhN2"><img src="https://i.ibb.co/fDv8cqt/Screen-Shot-2022-06-09-at-6-29-14-PM.png" alt="Screen-Shot-2022-06-09-at-6-29-14-PM" border="0"></a>

Since the progeram does not find an initial opening parentheses, it keeps passing the index as -1. However, it still searches for a set of closing parentheses. The thing is, when you call the `indexOf(char, startIndex)` function and start searching from an invalid index, it will just look for the character starting from the beginning. And it does in fact find the closing parentheses index.  

So when the substring function is later called from the index of the open parentheses plus one, or 0, and ending at the closing parentheses, it keeps returning the same string again and again without advancing forward. The value of the open parentheses index remains -1, meaning the while loop condition continues to be true.     


