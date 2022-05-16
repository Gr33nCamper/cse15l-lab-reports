# Lab Report 3: More Remote Access (and Github)

Implemented Group Choice Options (1-3) from Lab 5 are below. 

&nbsp; 

*1. Streamlining ssh Configuration*

<a href="https://ibb.co/SVVksbn"><img src="https://i.ibb.co/1RRCv1q/Screen-Shot-2022-05-15-at-5-52-04-PM.png" alt="Screen-Shot-2022-05-15-at-5-52-04-PM" border="0"></a>

After changing directory to ~/.ssh on local computer, typed in `open config` Edited file with TextEdit (file was initially blank).

&nbsp; 

<a href="https://ibb.co/r7Fjhc5"><img src="https://i.ibb.co/M2ZvHGP/ssh-ieng6-command.png" alt="ssh-ieng6-command" border="0"></a> 

The ssh command used to log in with alias. Alias used: ieng6. 

As you can see, much simpler than typing out `ssh cs15lsp2zadi@ieng6.ucsd.edu`.

&nbsp; 

<a href="https://ibb.co/PgzmLX2"><img src="https://i.ibb.co/5LxM0pQ/Screen-Shot-2022-05-15-at-10-48-03-PM.png" alt="Screen-Shot-2022-05-15-at-10-48-03-PM" border="0"></a> 

An scp command copying staff.txt from local computer to remote account with only alias.

&nbsp;

&nbsp; 


**2. Setup Github Access from ieng6**

<a href="https://ibb.co/MNx9jHx"><img src="https://i.ibb.co/dKw73vw/public-key-on-github.png" alt="public-key-on-github" border="0"></a>

Public key on Github.

&nbsp; 


<a href="https://ibb.co/h2f6sY1"><img src="https://i.ibb.co/6DBMYXJ/Screen-Shot-2022-05-16-at-12-01-57-AM.png" alt="Screen-Shot-2022-05-16-at-12-01-57-AM" border="0"></a>

Public key and private key location on user account is in .ssh directory.

&nbsp;


<a href="https://ibb.co/hRHKLN5"><img src="https://i.ibb.co/4ZMjKLy/Screen-Shot-2022-05-16-at-12-02-21-AM.png" alt="Screen-Shot-2022-05-16-at-12-02-21-AM" border="0"></a>

Value of public key.

&nbsp; 


Show where the private key you made is stored on your user account (but not its contents) as a screenshot.


Show running git commands to commit and push a change to Github while logged into your ieng6 account.

<a href="https://ibb.co/GM930GJ"><img src="https://i.ibb.co/ykpBXKR/Screen-Shot-2022-05-16-at-2-07-51-AM.png" alt="Screen-Shot-2022-05-16-at-2-07-51-AM" border="0"></a>

Adding edited MarkdownParse.java file to staging area. 

&nbsp; 

<a href="https://ibb.co/H7c9L2n"><img src="https://i.ibb.co/Y25V4Wp/Screen-Shot-2022-05-16-at-2-08-16-AM.png" alt="Screen-Shot-2022-05-16-at-2-08-16-AM" border="0"></a>

Committing changes to repository. 

[Link to resulting commit](https://github.com/R3dbAbyVamp/markdown-parser/commit/35a8c7f0f4769b69f8e0db806f0aeb304430cab0) 

&nbsp; 

<a href="https://ibb.co/PN4RRtN"><img src="https://i.ibb.co/TkRZZrk/Screen-Shot-2022-05-16-at-2-12-40-AM.png" alt="Screen-Shot-2022-05-16-at-2-12-40-AM" border="0"></a>

Pushing changes to main branch. 


&nbsp; 

**3. Copy whole directories with scp -r**
Show copying your whole markdown-parse directory to your ieng6 account.
Show logging into your ieng6 account after doing this and compiling and running the tests for your repository.
Show (like in the last step of the first lab) combining scp, ;, and ssh to copy the whole directory and run the tests in one line.
