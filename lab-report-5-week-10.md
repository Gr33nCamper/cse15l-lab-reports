# Lab Report 5: Comparing MarkdownParse Implementations 

**Test 1 (Markdown file with a long chain of various symbols)**

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

&nbsp;

The problem with my implementation: index out of bounds exception.

My program did not take into account the case where a closing parentheses after a "decoy" set of closing parentheses does not exist (We define decoy closing parentheses as closing parentheses which are not at the end of the markdown file or which are not followed by a newline character). So when it tries to add a substring from the previous open parentheses to the closing parentheses, which doesn't exist, it ends up calling the substring function from a valid index to -1, an invalid index. Accordingly, no links are generated, only a print statement is shown as output.

What I should have done was check if the closeParen index was >= 0 before adding the substring containing that index to the return string. If not, then break out of the while loop, since no link can exist, unless there were brackets preceding it and which enclosed characters.
In fact, a better way would be to check for the existence of brackets before checking for the existence of parentheses. If no brackets exist, then we can skip forward, since no link can exist without brackets preceding parentheses. 

The replacement would have to be at line 80. 

<a href="https://ibb.co/v4TrL5c"><img src="https://i.ibb.co/d4V3k9f/Screen-Shot-2022-06-09-at-5-31-10-PM.png" alt="Screen-Shot-2022-06-09-at-5-31-10-PM" border="0"></a>

The larger change would have to be made after finding the bracket indices, but before finding the parentheses indices.

<a href="https://ibb.co/PrQjxtL"><img src="https://i.ibb.co/dfgMB7T/Screen-Shot-2022-06-09-at-5-51-11-PM.png" alt="Screen-Shot-2022-06-09-at-5-51-11-PM" border="0"></a>


&nbsp; 

&nbsp; 



**Test 2 (Markdown file with escape characters, but this time specifically to make other markdown modifiers invalid)**

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

&nbsp;

The problem with my implementation: The program never reaches the end of the markdown file.   

Since the progeram does not find an initial opening parentheses, it keeps passing the index as -1. However, it still searches for a set of closing parentheses. The thing is, when you call the `indexOf(char, startIndex)` function and start searching from an invalid index, it will just look for the character starting from the beginning. And the program does in fact find the closing parentheses index as 53. This is shown in the debugging print statements below. 

<a href="https://imgbb.com/"><img src="https://i.ibb.co/CsrM3hL/Screen-Shot-2022-06-09-at-6-26-36-PM.png" alt="Screen-Shot-2022-06-09-at-6-26-36-PM" border="0"></a>

&nbsp;

So when the substring function (see screenshot below) is later called from the index of the non-existent open parentheses plus one (equivalently, 0), and ending at the closing parentheses, it keeps returning the same string again and again without advancing forward. The value of the current index remains less than the markdown file length, so the while loop condition continues to be true. 

<a href="https://ibb.co/3v70LcC"><img src="https://i.ibb.co/cw1N7Qr/Screen-Shot-2022-06-09-at-6-29-57-PM.png" alt="Screen-Shot-2022-06-09-at-6-29-57-PM" border="0"></a>

&nbsp;

What I should have done was check if an initial open parentheses exists before checking for a closing parentheses, since a half pair of parentheses cannot enclose anything. And if it doesn't exist, this means either it doesn't exist, or the program did not recognize another existing open parentheses as a valid one. If it doesn't exist, the program should break out of the while loop. The additional if-statement should be added before the highlighted line looking for the closing parentheses index.

<a href="https://ibb.co/8YczhN2"><img src="https://i.ibb.co/fDv8cqt/Screen-Shot-2022-06-09-at-6-29-14-PM.png" alt="Screen-Shot-2022-06-09-at-6-29-14-PM" border="0"></a>


