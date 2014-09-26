title: Getting Started with MALLET and Topic Modeling
link: http://electricarchaeology.ca/2011/08/30/getting-started-with-mallet-and-topic-modeling/
author: fhg1711
description: 
post_id: 1253
created: 2011/08/30 19:44:36
created_gmt: 2011/08/31 00:44:36
comment_status: open
post_name: getting-started-with-mallet-and-topic-modeling
status: publish
post_type: post

# Getting Started with MALLET and Topic Modeling

**UPDATE! September 19th 2012: ** [Scott Weingart](http://www.scottbot.net/HIAL/), [Ian Milligan](http://ianmilligan.ca/), and I have written an expanded '[how to get started with Topic Modeling and MALLET' for the Programming Historian 2](http://programminghistorian.org/lessons/topic-modeling-and-mallet). Please do consult that piece for detailed step-by-step instructions for getting the software installed, getting your data into it, and thinking through what the results might mean. Original Post that Inspired It All: I'm very interested in topic modeling at the moment. It has not been easy however to get started - I owe a debt of thanks to Rob Nelson for helping me to get going. In the interests of giving other folks a boost, of paying it forward, I'll share my recipe. I'm also doing this for the benefit of some of my students. Let's get cracking! First, some background reading: 

  1. Clay Templeton, “Topic Modeling in the Humanities: An Overview | Maryland Institute for Technology in the Humanities”, n.d., <http://mith.umd.edu/topic-modeling-in-the-humanities-an-overview/>.
  2. Rob Nelson, _Mining the Dispatch_ <http://dsl.richmond.edu/dispatch/>
  3. Cameron Blevins, “Topic Modeling Martha Ballard’s Diary” _Historying_, April 1, 2010, <http://historying.org/2010/04/01/topic-modeling-martha-ballards-diary>/
  4. David J Newman and Sharon Block, “Probabilistic topic decomposition of an eighteenth‐century American newspaper,” _Journal of the American Society for Information Science and Technology_ 57, no. 6 (April 1, 2006): 753-767.
  5. David Blei, Andrew Ng, and Michael Jordan, “Latent dirichlet allocation,” _The Journal of Machine Learning Research_ 3 (2003), <http://dl.acm.org/citation.cfm?id=944937>.
Now you'll need the software. Go to the [MALLET ](http://mallet.cs.umass.edu/)project page, and [download Mallet](http://mallet.cs.umass.edu/download.php). (Mallet was developed by Andrew McCallum at U Massachusetts, Amherst). Then, you'll need the [Java developer's kit](http://www.oracle.com/technetwork/java/javase/downloads/index.html) \- nb, not the regular Java that's on every computer, but the one that lets you program things. Install this. Unzip Mallet into your C:/ directory . **This is important; it can't be anywhere else**. You'll then have a folder called C:/mallet-2.0.6 or similar. Next, you'll need to create an environment variable called MALLET_HOME. You do this by clicking on control panel >> system >> advanced system settings (in Windows 7; for XP, see [this article](http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/environment_variables.mspx?mfr=true)), 'environment variables'. In the pop-up, click 'new' and type MALLET_HOME in the variable name box; type c:/mallet-2.0.6 (ie, the exact location where you unzipped Mallet) in variable value. To run mallet, click on your start menu >> all programs >> accessories >> command prompt. You'll get the command prompt window, which will have a cursor at c:\user\user> (or similar). type cd .. (two periods; that ain't a typo) to go up a level; keep doing this until you're at the C:\ .  Then type cd:\mallet-2.0.6 and you're in the Mallet directory. You can now type Mallet commands directly. If you type bin\mallet at this point, you should be presented with a list of Mallet commands - congratulations! At this point, you'll want some data. Using the regular windows explorer, I create a folder within mallet where I put all of the data I want to study (let's call it 'data'). If I were to study someone's diary, I'd create a unique text file for each entry, naming the text file with the entry's date. Then, following the [topic modeling](http://mallet.cs.umass.edu/topics.php) instructions on the mallet page, I'd import that folder, and see what happens next. I've got some work flow for scraping data from websites and other repositories, but I'll leave that for another day (or skip ahead to [The Programming Historian](http://niche-canada.org/programming-historian) for one way of going about it.) Once you've imported your documents, Mallet creates a single 'mallet' file that you then manipulate to determine topics. 
    
    
    bin\mallet import-dir --input \data\johndoediary --output
    johndoediary.mallet \ --keep-sequence --remove-stopwords

(modified from the Mallet topic modeling page) This sequence of commands tells mallet to import a directory located in the subfolder 'data' called 'johndoediary' (which contains a sequence of txt files). It then outputs that data into a file we're calling 'johndoediary.mallet. Removing stopwords strips out 'and' 'of' 'the' etc. Then we're ready to find some topics: 
    
    
    bin\mallet train-topics --input johndoediary.mallet \
      --num-topics 100 --output-state topic-state.gz --output-topic-keys
      johndoediary_keys.txt --output-doc-topics johndoediary_composition.txt

(modified from the Mallet topic modeling page) Now, there are more complicated things you can do with this - take a look at the documentation on the Mallet page. Is there a 'natural' number of topics? I do not know. What I have found is that I have to run the train-topics with varying numbers of topics to see how the composition file breaks down. If I end up with the majority of my original texts all in a very limited number of topics, then I need to increase the number of topics; my settings were too coarse. More on interpreting the output of Mallet to follow. Again, I owe an enormous debt of gratitude to Rob Nelson for talking me through the intricacies of getting Mallet to work, and for the record, I think the work he is doing is tremendously important and fascinating!

## Comments

**[Shawn](#6491 "2012-04-09 14:57:21"):** Hi Abbey, You can find my email here: http://www2.carleton.ca/history/people/1631-2 and send a screenshot.

**[Ellen L Freeman](#6707 "2012-04-27 13:54:45"):** Shawn--I am having the same problem that Colin was having ---any resolution?

**[Shawn](#6708 "2012-04-27 14:15:32"):** Can you send me a screenshot of what's happening? I have trouble visualizing text sometimes :)

**[Shawn](#6916 "2012-05-17 13:18:22"):** Hi Vita - yes, it turns your texts into a single file that it then does its magic on (it does leave your original files where you left 'em though).

**[Ian Milligan](#7133 "2012-07-27 13:15:43"):** This is a fantastic guide. I can just imagine how long I'd have been bashing my head against this thing without the help (esp. the critically important things like needing the Java SDK). Just so I don't forget, a few details for OS X. It all mostly works the same, except you have to make sure to tell the shell that you want to run the mallet script from the directory you're working on rather than your path - in essence, this means appending ./ to the commands: i.e. ./bin/mallet . Conveniently you don't have to worry about putting it in your root directory or anything, you can just put it wherever you want and navigate to it using the terminal. Another key thing that's improved my ability to work with large corpuses is increasing the memory available to your Java virtual machine. Otherwise, you'll crash as you run out of heap space. Using a text editor, if you edit the 'mallet' file that you're running (in the /bin directory), you can change the memory variable. By default it's at 1g, I now have mine up to 8g (but I have a lot of RAM). For example, I'm currently running a topic model that's eating up 7 gigs of memory and crashes if you don't give it any more.

**[John Muccigrosso (@JD_PhD)](#4852 "2011-08-31 08:31:34"):** What is this C: drive you speak of?

**[Shawn](#5080 "2011-11-11 10:34:09"):** Hi Ben - thank you for the links! I've been playing with the Java GUI you found. Important note regarding the input file or directory - if you use a .mallet file you've already created, your output will be filled with gibberish. You need to input the original txt files or directory holding them all. This is quite exciting. I have some students interested in doing this kind of analysis, and having the GUI will make that much easier for them. ![Topic Modeling 'Writing History in the Digital Age' with Java GUI: html output](http://electricarchaeologist.files.wordpress.com/2011/11/topic-modeling-w-java-gui.png)

**[Ben](#5062 "2011-11-07 04:31:13"):** Thanks for the quick and detailed reply, that's very helpful. Have you tried any of the R packages for topic modelling? They're not very well documented at the moment, but I've got results from topicmodels, though Mallet is substantially faster. The other package, lda, is proving a bit more of a challenge though. I've been using python for other text mining tasks but have yet to try any of its topic modelling packages. Regarding the problem of how many topics are enough, there seems to be a method to address that here: Griffiths, T. L., & Steyvers, M. (2004). Finding scientific topics. Proceedings of the National Academy of Science, 101, 5228-5235, but the implementation is not obvious (to me anyway!). Hierarchical Dirichlet Processes are supposed to be an approach to automatic selection of the best number of topics, but the results I get from hlda in MALLET are not very satisfying...

**[Shawn](#5070 "2011-11-08 09:36:49"):** Hi Ben, Thank you for the link - I'll chase that up. Regarding the right number of topics, I'm not sure what the best approach is... running the analysis, examining the composition file, tuning the parameters, and running again seems clumsy but it does have the virtue of getting me to look closely at what's happening at every step. I haven't tried R, though it's been sitting on my desktop - accusingly - waiting for me to start working through the various tutorials... Enrico Crema, http://evolvingspaces.blogspot.com/ , uses R for agent modeling and other wizardry. While I don't think he's tried topic modeling, he does seem to be quite adept at R and might find it interesting to try.

**[Ben](#5077 "2011-11-10 17:13:39"):** Just an update on evaluating the best number of topics, here's what I've learned recently... two papers discuss the problem in detail, one by Mimno et al 9http://aclweb.org/anthology/D/D11/D11-1024.pdf) and one by AlSumait et al. (http://www.cs.gmu.edu/~carlotta/publications/ECML09_AlSumaitetal.pdf). And there are some instructions on how to get a diagnostics file on topics from MALLET (http://article.gmane.org/gmane.comp.ai.mallet.devel/1483/) that correspond to some of measures of topic usefulness in the two papers mentioned. By the way, I also recently came across this Java GUI for MALLET which outputs CSV files directly: http://code.google.com/p/topic-modeling-tool/

**[abbey](#6440 "2012-04-05 09:54:33"):** Have follow your instruction as stated above but i got the following- Error: Could not find or load main class cc.mallet.classify.tui.Text2Vectors from command prompt I could sent you the screenshoot through yr email if i have it. Pls help.

**[Shawn](#5056 "2011-11-05 20:32:48"):** I've been following the lead of Elijah Meeks, who has been using Gephi (http://gephi.org) to visualize these things. (Gephi's not the best program for network analysis, but it certainly is one of the most aesthetically pleasing in terms of its visualization capabilities). Elijah's workflow is here: https://dhs.stanford.edu/comprehending-the-digital-humanities/ I take the resultant composition file from Mallet, identify what the various topics might mean by sorting the input files (paragraphs, diary entries, blog posts, what have you) by their highest percentage composition (eg, text-file1.txt is composed of topic 4 95% topic 3 3 % topic 8 2 %. I then read text-file1.txt and compare it with the key words for topic 4; this gives me an idea of what topic 4 actually is about. Then, having done that for every topic, I create a csv file with two columns. In the first column (labelled 'source') are the names of every input text file (eg, july8.txt, july9.txt...) In the second column (labelled 'target') is the topic name for the topic that dominates that file's composition. I could create a third column, call it weight, that records that percentage, too. I then use http://gephi.org to visualize the input files to topics. Gephi is a bit temperamental, but its csv import routine usually works well. (More on that in a later post). This creates a directed graph, by the way, which is important if one wanted to do any sort of network metrics.

**[Ben](#5554 "2012-01-09 01:35:31"):** Hi Shaun, I recently completed my first start-to-finish foray into topic modelling. I used R all the way, mostly because I found it easiest to code to automate the discovery of the optimum number of topics for the corpus (following Griffiths & Steyvers 2004). The R code is here https://github.com/benmarwick/AAA2011-Tweets and contains a few other snippets useful for manipulating topic modelling output from R, basic text mining of tweets and visualizing the results with ggplot2. I just wanted to thank you for your earlier correspondence, it was very helpful as I was getting started (even though I didn't use MALLET in this instance)

**[Shawn](#4853 "2011-08-31 09:20:36"):** It's your main hard drive.

**[collinjennings](#5874 "2012-02-16 15:49:16"):** Hi Shawn, Thanks so much for this! I've been struggling to get mallet installed. Following your directions, when I try to get into the mallet directory (I unzipped mallet onto the c drive, and am on the c directory, and I type cd:\mallet-2.0.7, it says "The filename, directory name, or volume label syntax is incorrect." I set the environment variable (although I don't know if it's supposed to be under system variables or user variables). Do you have any ideas as to what's going wrong? Thanks again!

**[Chris Leeder](#6744 "2012-04-30 15:46:10"):** Thanks so much for this, Shawn. The original programmers instrcutions leave a lot to be desired.

**[Shawn](#6739 "2012-04-30 10:25:32"):** Hi Collin - Sorry it's taken me so long to get thinking on this- Ellen sent me a screenshot of what she's seeing. Try putting a space after 'cd', like so: c:\cd mallet-2.0.7 And that should do it. My apologies for the delay.

**[Shawn](#6740 "2012-04-30 10:25:53"):** c:\cd mallet-2.0.7

**[Shawn](#5886 "2012-02-17 11:37:51"):** Hi Collin - maybe you could send me some screenshots of what you're seeing, and I can try to diagnose what the issue is.

**[Ben](#5049 "2011-11-04 22:30:25"):** Nice overview of getting started with MALLET, thanks. Matthew Jockers has done a similar topic modelling study here http://www.stanford.edu/~mjockers/cgi-bin/drupal/node/39 How did you do the visualization?

**[Vita](#6844 "2012-05-10 09:28:18"):** Shawn, I import files from some directories , just want to make sure , after I imported that files documents, does Mallet create a SINGLE ‘mallet’ file, really, really a single file ?

**[Shawn](#24586 "2014-03-21 14:21:30"):** Hi - if you check our longer, more complete tutorial at http://programminghistorian.org/lessons/topic-modeling-and-mallet, you'll find what you need. Also, the journal of digital humanities (http://journalofdigitalhumanities.org) has an entire issue devoted to these kinds of questions. Good luck!

