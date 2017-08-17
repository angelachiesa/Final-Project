# Final Project Fail Log
August 16th

---
# First Step - Downloading the Data
###### DhBox 
First step is to download this data. My DH box account has expired, so I just made a new account with my father’s email address. Now that I’m logged in, I’m going to create a directory for my project and download the files. 
How did I do this?
1.	I typed in **mkdir** followed by “shawville”. Mkdir is how you make a new directory which is pretty much your file, and Shawville is what I named it, which is after the newspaper.
2.	Next, I typed **ls** to make sure the file was created and it is still present.
3.	I typed **cd Shawville** which pretty much lets you enter/click on the folder. So, cd is stating you want to click on a folder, and you follow up by typing the name of which folder you want.
4.	Now to download only specifically the 2010s I would need to go **wget http://collections.banq.qc.ca:8008/jrn03/equity/src/ -A "*2010*".txt -nc -r --no-parent -nd –w 2 --limit-rate=20k** (You use “wget” to tell the program to install it into dhbox.)
-	Where the brackets say 2010, I can either put 201 which means it will download the decade. Prior to this I had planned to only doing 2010, but I feel like there may not be as much information. I just choose 2010 because it was the most recent year out of the scanned documents, but I think it’ll be more interesting to do my project on what topics were most common in the 21st century rather than just to 2010.
5.	New command is now wget http://collections.banq.qc.ca:8008/jrn03/equity/src/ -A "*201*".txt -nc -r --no-parent -nd –w 2 --limit-rate=20k **
6.	To save the work, I typed out **history** and **history > dhbox-work-today.md** which created a new file to show my saved work. All from exercise 2 in Week 1. 

**Note**
I noticed when I went into nano that I couldn't find the actually text? Not sure what I did wrong but when I went into the file manger, all the files were there. So that's reassuring but I’m wondering if this will cause problems in terms of fixing the text down the line. Instead of using Notepad++, and going through all the time, I’m going to go through Open File to clean this up a bit. 

##### Mistakes
First mistake, after trying to open the files in nano, I realized that I typed out what 2010s and beyond, not 2000-2010. No problem, the most important thing is that I realized quickly why. The new command is 
wget http://collections.banq.qc.ca:8008/jrn03/equity/src/ -A "*200*".txt -nc -r --no-parent -nd –w 2 --limit-rate=20k **


>References
To do this part of the project, I used exercise __2:wget__ to refresh my memory on how to do this.
https://via.hypothes.is/http://workbook.craftingdigitalhistory.ca/module-2/Exercises/#exercise-2-wget

>Reflection
Doing it a second time was a lot easier, obliviously from experience and now knowing what you need to do. I defiantly don’t feel overwhelmed by doing this project anymore and I really think this was an effective way of teaching someone coding. The way I learnt a lot of my computer software’s was by being given projects and just doing them, and spending a lot of time on YouTube even as simple as “where is this button”. 


# Second Step - Cleaning up the Data
In this step, we are going to clean up the data by using Regex. Were going to use this to search and replace patterns in text. We are using **Exercise 2** in Module 3 as reference for this part of the project.
How did I do this?
1. used the command **curl** which is like wget. In this exercise, it asks us to use curl. After reading more about it, it seems to be used as an API that can be used by everyone? Not sure if my file from wget was fine but I figured I would stick with the tutorial to avoid any problems since they are two different commands. 
2. So after **curl** I copied and pasted the web URL for the Shawville files which is http://collections.banq.qc.ca:8008/jrn03/equity/src/ and I used **> texas.txt**
- By using the **>** this creates a file, not a folder, once again, not entirely sure if I could have just used my folder? but I know how these software’s/programs work and one slight change sometimes just ends up not working. So hopefully I didn't just add in the information twice.
3. Okay so when I tried copying and pasting the information from the texas.txt file, I only got the dates of the newspaper which makes a lot of sense because the tutorial was geared around categorizing them. I went into my Shawville file and pulled out a file from 2000. This is making me reconsider using a decade of information rather than a year because these files are extremely dense, however instead of changing my project, I’m just going to use this file to clean up and search and play around for a little bit. Worse case scenario, I just use only one year of data!
4. Something that I thought was interesting in RegEx was that in the examples you can use to search is *24 or 32 big colors*. I wonder if you can use this to search for headlines in newspapers? 
5. I noticed that there was a lot � symbols and I wanted to get rid of them so I used the command from the tutorial using to get rid of something else, and changed up the command to this \r\n[^�].+. This is supposed to search for that symbol and replace it with nothing.

**Further Context on where and why I'm using this command**
 If I was using a text editor on my computer, the search string is (\n[^~].+)
\n or \r\n means to search for a new line
[] within those, and the ^ this means to search
the .+ means to search for all the rest of the characters in the line as well
To look at it go, grep '~' texas.txt > index.txt
what this does is, it looks for the '~' lines and puts it into a new file called index.txt which you can access with nano.

6. I realized by using that command, it didn't pick up anything and I realized it was because it was looking for a new line so I decided to try **[^�]**. This picked up everything but the symbols. Exactly not what I was going for. Actually I think it does highlight all these things but I can't seem to delete them.
>Reflection
Well I tried to delete them and not to sure where I went wrong, but i'm going to continue with the project regardless. Even though I won't have perfect or most organized data, I'm going to go ahead and continue with searching through. 

# Third Step - Finding the Data & Analyzing and Searching
Were going to go ahead and use some tutorials in Module 4. After doing some reading, the Topic Modeling Tool allows you to browse results. This can help me find my information.
How did I do this?
1. First I had to zip the files so I used the command **zip -r shawville.zip shawville**. Than I went into the filemanger and downloaded the zip file. I'm assuming you had to do this to get all the files to download onto your computer. Makes a lot of sense since when I tried to do this earlier in Open Refine and Regex, I only did only file. Glad I now know how to do this step and I can continue with my data. 
2. Now that I have Topic Modeling downloaded, I use the default settings and plugged in my information into the input folder and created a file for the output folder and ran the settings. It worked and made a spreadsheet of the words said most in each year, with the ten most talked about subjects. I will be using these data to plug into some visualizations. 

# Fourth Step – Visualization
I saw that exercise 7 in module 4 looked like a clever idea to use to create my charts. I had difficult with the data I had. It wasn’t organised as well as I thought. I begin to consider it more and realized that I would have had better search results if I excluded number and dates. Rather than restart, I decided to add it because it still something that’s talked about. For example, a specific date could involve a topic or something that had happen. April 1st was mentioned a lot, which we all know as April fools. 
I liked RAW graphs a lot and it’s something I will defiantly use in the future. It just made this a whole lot easier to show and display. 
How did I do this?
1. Go to http://app.rawgraphs.io/
2. Copy and paste your excel Information
3. Choose which kind of graph you want to use
4. Drag the column to the appropiate settings
5. Save as a png 

**Other Programs I tried**

# Paradata Essay

>The readings really did make me think more of the time these people go through to understand and study. Something that also really made me think was that there isn't just google out there. I found it so interesting that there all these other search engines and I’m happy I was able to finally do this at a larger scale rather than minor exercises.


> During the entire process, I did not feel frustrated at all because I understood that this course was more about the process and how you get there, and not what you achieve. I wanted to be able to look for head tiles and I genially did try with Regex but it's not an easy program to use. Even all the commands change based on what computer you use so google wasn't to much help.



> Self Reflection
I feel like I pushed myself a lot throughout this summer course. I almost completed every exercise in every week. I even now tried more than two exercises than in Module 4 than recommended and in Module 5. I learnt a lot, especially patience and I also learnt to appreciate what some of these people do. I find a lot of the time you just look at the final product and not many people look at the work that goes into these things. This isn't just with this summer course, but in general. Everything takes time, and has a process. Nothing is better than enjoying the process of something, and the feeling of the end results at the product. For example, I remember being in high school and everyone complained "when am I ever going to use advanced functions", and I understood that no, were probably never going to use it, but the point of doing this, is to teach us that there is a process and how to solve problems. I feel like in a way, that's basically University too. It's all about framing someone's mind and making them think and not just do. Overall, I'm glad that this course was formatted more with how you achieve or get to something and not the total result. It really made me think why. I was even telling someone the other day, that this course wasn't easy for me, and they asked me why. The response was super easy, I said "well, if you want to download something, you press a button that says download, you got to memorize, and type out commands that have nothing to relate to the subject, for example, curl or wget". Right after said that, it just made me appreciate the time historians spend doing this kind of stuff.


