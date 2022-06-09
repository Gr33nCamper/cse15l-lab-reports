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
Used vimdiff on the results of running a bash for loop. (Note: the bash script for my implementation led to an infinite loop for more than one of the tests, so the results.txt file did not include the results for all the test files).   

[Test-file 12 link](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/12.md) 

The implementation provided for lab 9 is correct, since there are no links in the test file.
My implementation leads to this bug: (prints, but does not terminate loop?)

&nbsp; 

**Test 2** 

