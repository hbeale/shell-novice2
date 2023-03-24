---
layout: page
title: Setup
root: .
---

## Connect to the server
If you need help with this step, please see the section of the TUBI handbook called "Connecting to the TUBI server." 

## Download files
Use the following commands to download some files that are used in this tutorial. These commands won't necessarily make sense right now, but the rest of the tutorial will help you understand how to interpret them.

On the server, run the command `wget https://UCSC-Treehouse.github.io/shell-novice2/data/data-shell.zip` to download the file. It's easiest to copy the command to the server. Press enter once you've pasted it. If you're using Windows and PuTTY, check the handbook for instructions on pasting.
   
After you run the command, you should see something like the following
~~~   
-bash-4.2$ wget https://UCSC-Treehouse.github.io/shell-novice2/data/data-shell.zip
--2021-04-29 12:53:18--  https://ucsc-treehouse.github.io/shell-novice2/data/data-shell.zip
Resolving ucsc-treehouse.github.io (ucsc-treehouse.github.io)... 185.199.108.153, 185.199.110.153, 185.199.109.153, ...
Connecting to ucsc-treehouse.github.io (ucsc-treehouse.github.io)|185.199.108.153|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 580102 (567K) [application/zip]
Saving to: ‘data-shell.zip’

100%[===================================================================================================>] 580,102     --.-K/s   in 0.04s   

2021-04-29 12:53:19 (14.0 MB/s) - ‘data-shell.zip’ saved [580102/580102]

~~~
{: .output}

Run the command `unzip -o data-shell.zip` to unzip/extract the file. **If you need help with this step, please reach out on Slack**

After you run the unzip command, you'll see many files scroll by, and the end will look something like this
~~~   
 extracting: data-shell/writing/thesis/empty-draft.md  
  inflating: data-shell/solar.pdf    
   creating: data-shell/creatures/
  inflating: data-shell/creatures/unicorn.dat  
  inflating: data-shell/creatures/basilisk.dat  
  inflating: data-shell/creatures/minotaur.dat  
-bash-4.2$ 
~~~
{: .output}

In the lesson, you will find out how to access the downloaded data files.

