# Remote Access Tutorial 

Hey how's it going? If you have taken, or are currently taking, CSE 15L, this tutorial may be helpful for you
in understanding some things about running commands on remote computers.     
Ok, here we go.      

*Step 1: Installing VScode*
  
&nbsp;
<a href="https://ibb.co/s29RMhM"><img src="https://i.ibb.co/c1h37P7/unnamed.png" alt="unnamed" border="0"></a>
  
Pretty simple. Just go to the VScode website and download [here](https://code.visualstudio.com) for your operating system. Upon opening the application, you should see something that looks like the above (this is from a Mac, may be different for Windows). 
 
&nbsp; 
  
  
*Step 2: Remotely Connecting* 
  
&nbsp;
<a href="https://ibb.co/xXgccfy"><img src="https://i.ibb.co/9c4ffVJ/unnamed-3.png" alt="unnamed-3" border="0"></a> 

Once you have VScode installed, you can use the `ssh` command in terminal to connect to the server. When I entered the command, it prompted me for my password, and let me in after I copy and pasted it in (you'll see something like this also). This can get inconvenient if you have to do it repeatedly, however, so stay tuned for the easier method in Step 5.   
   
&nbsp; 


*Step 3: Trying Some Commands*
  
&nbsp;
<a href="https://imgbb.com/"><img src="https://i.ibb.co/4MKWH4h/unnamed-2.png" alt="unnamed-2" border="0"></a>
  
Great! Now that you're in, you can test out some commands on the server (I used `ls`, `whoami`, and `pwd`, but you can run any other commands you would like).  
&nbsp;
  
  
*Step 4: Moving Files with scp*
&nbsp;

Here's another useful command: scp.    
Using scp, we can securely copy files like WhereAmI.java from our local computer to the server, and run them from there. 

<a href="https://ibb.co/ZKKrtLW"><img src="https://i.ibb.co/d66v1WG/unnamed-4.png" alt="unnamed-4" border="0"></a> 
  
<a href="https://ibb.co/W6vKzk3"><img src="https://i.ibb.co/rm2ypxt/unnamed-5.png" alt="unnamed-5" border="0"></a> 
  
  
To check if this file is actually there, we can connect to the server from the client, then list out the files (and sure enough, it is!)

&nbsp;
  
  
*Step 5: Setting an SSH Key* 
    
<a href="https://ibb.co/DVvLzLV"><img src="https://i.ibb.co/qycx7xy/Screen-Shot-2022-04-17-at-11-27-18-PM.png" alt="Screen-Shot-2022-04-17-at-11-27-18-PM" border="0"></a>
    
Now, for the easier method I mentioned earlier. What we're going to do is use the ssh -keygen program to generate public and private ssh keys, then save the key to a file called .ssh/id_rsa (We leave the “enter passphrase” prompt blank since we do not want a passphrase).    

  
<a href="https://ibb.co/QHvtpgy"><img src="https://i.ibb.co/X5xMjQc/Screen-Shot-2022-04-17-at-11-43-18-PM.png" alt="Screen-Shot-2022-04-17-at-11-43-18-PM" border="0"></a>.

Once we have copied the public key from the client to the server, it is now possible to log in to the server *WITHOUT our password*.    
Pretty neat, right?  
&nbsp; 
  
&nbsp; 


*Step 6: Optimizing Remote Running* 

&nbsp;
<a href="https://ibb.co/SXFH88h"><img src="https://i.ibb.co/xSxw00p/Screen-Shot-2022-04-18-at-3-26-41-PM.png" alt="Screen-Shot-2022-04-18-at-3-26-41-PM" border="0"></a> 
  
One way to optimize the process is to simply use previously entered commands. In this example, I used 4 keystrokes. Up key to get `scp WhereAmI.java cs15lsp22adi@ieng6.ucsd.edu:~/`, then enter to run, followed by up key to get `ssh cs15lsp22adi@ieng6.ucsd.edu “javac WhereAmI.java; java WhereAmI"` and enter to run.  
Essentially, this just copies over the edited file from the client, and simultaneously compiles and runs the file on the server.
  
&nbsp;

Well, that is all for now. Thank you for reading through this tutorial and until next time, take care.

