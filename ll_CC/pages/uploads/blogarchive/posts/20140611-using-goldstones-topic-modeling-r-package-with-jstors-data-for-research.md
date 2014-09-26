title: Using Goldstone's Topic Modeling R package with JSTOR's Data for Research
link: http://electricarchaeology.ca/2014/06/11/using-goldstones-topic-modeling-r-package-with-jstors-data-for-research/
author: fhg1711
description: 
post_id: 2051
created: 2014/06/11 10:52:58
created_gmt: 2014/06/11 15:52:58
comment_status: open
post_name: using-goldstones-topic-modeling-r-package-with-jstors-data-for-research
status: publish
post_type: post

# Using Goldstone's Topic Modeling R package with JSTOR's Data for Research

[Andrew Goldstone](http://andrewgoldstone.com) and [Ted Underwood](http://tedunderwood.com/) have an article on 'the quiet transformation of literary studies' ([preprint](http://www.rci.rutgers.edu/~ag978/quiet/preprint.pdf)), where they topic model a literary history journal and discuss the implications of that model for their discipline. [Andrew has a blog post discussing their process ](http://andrewgoldstone.com/blog/2014/05/29/quiet/)and the coding that went into that process. I'm currently playing with their code, and thought I'd share some of the things you'll need to know if you want to try it out for yourself - [get it on github](https://github.com/agoldst/dfrtopics). I'm assuming you're using a Windows machine. 1\. Get the right version of R. [You need 3.0.3 for this](http://cran.r-project.org/bin/windows/base/old/3.0.3/). Use either the 32 bit or 64 bit version of R ( both download in a single installer; when you install it, you can choose the 32 bit or the 64 bit version, depending on your machine. Choose wisely). 2\. Make sure you're using the right version of Java. If you are on a 64 bit machine, have 64 bit java; 32 bit: 32 bit java. 3\. Dependencies. You need to have the rJava package, and the Mallet wrapper, installed in R. You'll also need 'devtools'. In the basic R gui, you can do this by clicking on packages >> install packages. Select rJava. Do the same again for Mallet. Do the same again for 'devtools'. Now you can install Goldstone's dfrtopics by typing, at the R command prompt `library(devtools) install_github("dfrtopics","agoldst")` Now. Assuming that you've downloaded and unzipped a dataset from JSTOR (go to [dfr.jstor.org](dfr.jstor.org) to get one), here's what you're going to need to do. You'll need to increase the available memory in Java for rJava to play with. You do this before you tell R to use the rJava library. I find it best to just close R, then reload it. Then, type the following, one at a time: ` options(java.parameters="-Xmx2048m") library(rJava) library(mallet) library(dfrtopics) ` The first item in that list increases the memory heap size. If all goes well, there'll be a little message telling you that your heap size is 2048 mb and you should really increase it to 2gb. As these are the same thing, then no worries. Now to topic model your stuff! `m <\- model_documents(citations_files="[path to your]\\\citations.CSV", dirs="[path to your]\\\wordcounts\\\", stoplist_file="[path to your]\\\stoplist.txt", n_topics=60) ` Change n_topics to whatever you want. In the path to your files, remember to use double \\\\. Now to export your materials. `output_model(m, "data") ` This will create a 'data' folder with all of your outputs. But where? In your working directory! If you don't know where this is, wait until the smoke clears (the prompt returns) and type `` `getwd() ` You can use setwd() to set that to whatever you want: ` setwd("c:\\\path-to-your-preferred-work-directory") ` You can also export all of this to work with Goldstone's topic model browser, but that'll be a post for another day. Open up your data folder and explore your results.

## Comments

**[Andrew Goldstone](#31282 "2014-06-11 12:56:38"):** Thanks for trying this out, Shawn! Amazed dfrtopics even works on Windows. Looks like the code example that says how to run model_documents is missing a line. You can specify file paths in R, even on Windows, with forward slashes, so that might save typing all those double backslashes. You exposed my laziness on the java heap size check, which assumes "XXXm" is always less than 2GB. Numbers!

**[Shawn](#31283 "2014-06-11 13:39:49"):** Cheers Andrew! I fixed the error in model_documents. Reader - go see Andrew's github page!

