# Lab Report 3: Code Snippets and Testing

Three code snippets
Add test for each to your own code and the one you reviewed
Determine expected output
Comment if short code change could be made to fix problem

&nbsp;

Links: 

[my markdown-parse repository](https://github.com/R3dbAbyVamp/markdown-parser)

[reviewed markdown-parse repository](https://github.com/lithicarus/markdown-parser) 

&nbsp;



**1. MarkdownParseTest.java Test for Parsing First Snippet**

Test for my implementation:

<a href="https://ibb.co/dcfxMNK"><img src="https://i.ibb.co/fSXLF30/Screen-Shot-2022-05-30-at-4-24-15-PM.png" alt="Screen-Shot-2022-05-30-at-4-24-15-PM" border="0"></a>

&nbsp;

-------Results-------

<a href="https://ibb.co/1Z1xMKH"><img src="https://i.ibb.co/312HvWt/Screen-Shot-2022-05-30-at-4-12-03-PM.png" alt="Screen-Shot-2022-05-30-at-4-12-03-PM" border="0"></a>



My code failed.
&nbsp; 

I do not believe there could be a small code change that would make the program work for snippet 1 and all related cases. While there is the most obvious case where everything is enclosed with backticks, and thus there cannot be a link, there are numerous additional edge cases (e.g. case where only the closing bracket is enclosed with backticks, which is enough to invalidate the link, and two backticks are in between the brackets and parentheses, which also invalidates the link). 

&nbsp;



Test for reviewed implementation:

<a href="https://ibb.co/thW2hjy"><img src="https://i.ibb.co/qnPgnqb/Screen-Shot-2022-05-30-at-4-24-06-PM.png" alt="Screen-Shot-2022-05-30-at-4-24-06-PM" border="0"></a>

&nbsp;

-------Results-------

<a href="https://ibb.co/TwcbmtQ"><img src="https://i.ibb.co/ZfdYWxQ/Screen-Shot-2022-05-30-at-4-12-15-PM.png" alt="Screen-Shot-2022-05-30-at-4-12-15-PM" border="0"></a>

This code did not pass the test 

&nbsp;

&nbsp;



**2. MarkdownParseTest.java Test for Parsing Second Snippet**

Test for my implementation:

<a href="https://ibb.co/FxkLQDZ"><img src="https://i.ibb.co/bWjM4Kw/Screen-Shot-2022-05-30-at-2-02-40-AM.png" alt="Screen-Shot-2022-05-30-at-2-02-40-AM" border="0"></a>


-------Results-------

<a href="https://ibb.co/3S6gkL7"><img src="https://i.ibb.co/9yKQGCN/Screen-Shot-2022-05-30-at-1-58-14-AM.png" alt="Screen-Shot-2022-05-30-at-1-58-14-AM" border="0"></a>

My code failed.
&nbsp; 

I do not believe there could be a small code change that would make the program work for snippet 2 and all related cases. While my code accounts for nesting brackets within brackets or parentheses within parentheses, it does not account for nesting a link inside another link. This would require checking if there is a character (e.g. close bracket) after the closing parentheses which pairs with an earlier character (e.g. open bracket). While this could perhaps be done with a stack ADT, it is going to take more than 10 lines when you consider storing the indexes of paired parentheses and brackets for tracking and recognizing special combinations where the link will be valid still.         

&nbsp;

Test for reviewed implementation: 

<a href="https://ibb.co/g6sV9Mj"><img src="https://i.ibb.co/XVm8LZ2/Screen-Shot-2022-05-30-at-2-02-51-AM.png" alt="Screen-Shot-2022-05-30-at-2-02-51-AM" border="0"></a>

&nbsp;

-------Results-------

<a href="https://ibb.co/BwhqJX6"><img src="https://i.ibb.co/t308672/Screen-Shot-2022-05-30-at-2-00-40-AM.png" alt="Screen-Shot-2022-05-30-at-2-00-40-AM" border="0"></a>

This code did not pass the test


&nbsp;

&nbsp;


**3. MarkdownParseTest.java Test for Parsing Third Snippet**

Test for my implementation 

<a href="https://ibb.co/CHJWCbC"><img src="https://i.ibb.co/G5sFYWY/Screen-Shot-2022-05-27-at-5-29-27-PM.png" alt="Screen-Shot-2022-05-27-at-5-29-27-PM" border="0"></a>  

&nbsp;

-------Results-------

<a href="https://ibb.co/dDJ1c9R"><img src="https://i.ibb.co/6FJVZhk/Screen-Shot-2022-05-30-at-5-10-25-PM.png" alt="Screen-Shot-2022-05-30-at-5-10-25-PM" border="0"></a>

My code failed. 
It looks like there could be a small code fix. All you would need to do is add a check for if the index immediately after a newline character is followed by one more newline character, since two or more consecutive newlines automatically invalidates the link.


&nbsp;

Test for reviewed implementation

<a href="https://ibb.co/qdnXKHM"><img src="https://i.ibb.co/PNY3K2Z/Screen-Shot-2022-05-27-at-5-50-32-PM.png" alt="Screen-Shot-2022-05-27-at-5-50-32-PM" border="0"></a>

&nbsp;

-------Results-------

<a href="https://ibb.co/C242FZK"><img src="https://i.ibb.co/m8d87w5/Screen-Shot-2022-05-30-at-2-16-32-AM.png" alt="Screen-Shot-2022-05-30-at-2-16-32-AM" border="0"></a>

This code did not pass the test

&nbsp;


Decide on what it should produce (i.e., expected output) by using either VScode preview or the CommonMark demo site
Showing the code in MarkdownParseTest.java for how you turned it into a test
For your implementation, the corresponding output when running the tests; if it passed, say so. If it didn’t pass, show the specific part of the JUnit output that shows the test failure.
For the implementation you reviewed in Week 7, the corresponding output when running the tests; if it passed, say so. If it didn’t pass, show the specific part of the JUnit output that shows the test failure.
Answer the following questions with 2-3 sentences each:
Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks? If yes, describe the code change. If not, describe why it would be a more involved change.
