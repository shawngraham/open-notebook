title: Open Notebooks
link: http://electricarchaeology.ca/2014/09/16/open-notebooks/
author: fhg1711
description: 
post_id: 2200
created: 2014/09/16 10:26:25
created_gmt: 2014/09/16 15:26:25
comment_status: open
post_name: open-notebooks
status: publish
post_type: post

# Open Notebooks

[caption id="" align="aligncenter" width="429"]![](http://www.horsenation.com/wp-content/uploads/2014/01/packrat3.jpg) A packrat. Tack by Jennifer Buxton http://braymere.blogspot.ca/ More tiny saddles on tiny animals at http://www.horsenation.com/2014/01/28/we-dont-have-tack-for-that-presented-by-thinline-18/[/caption] This post is more a reminder to me that anything you'd like to read, but anyway- I want to make my research more open, more reproducible, and more accessible. I work from several locations, so I want to have all my stuff easily to hand. I work on a Mac (sometimes) a PC (sometimes) and on Linux (rarely, but it happens; with new [goodies from Bill Turkel et al](http://williamjturkel.net/2014/09/09/creating-the-historycrawler-virtual-machine/) I might work more there!). I build models in Netlogo. I do text analysis in R. I visualize and analyze with things like Voyant and Overview. I scrape websites. I use Excel quite a lot. I'm starting to write in markdown more often. I want to teach students (my students typically have fairly low levels of digital literacy) how to do all this too. What I don't do is much web development type stuff, which means that I'm still struggling with concepts and workflow around things like version control. And indeed, getting access to a server where I can just screw around to try things out is difficult (for a variety of reasons). So my server-side skills are weak. What I think I need, is an open notebook. Caleb McDaniel [has an excellent post](http://wcm1.web.rice.edu/open-notebook-history.html) on what this could look like. He uses [Gitit](http://gitit.net/). I looked at the documentation, and was defeated out of the gate. [Carl Boettiger](http://www.carlboettiger.info/lab-notebook.html) uses a combination of github and jekyll and who knows what else. What I really like is [Mark Madsen's example](http://notebook.madsenlab.org/labnotebook.html) but I'm not aufait enough yet with all the bits and pieces (damn you version control, commits, make, rake, et cetera et cetera!) I've got [ipython](http://ipython.org/) notebooks working on my PC, which are quite cool (I installed the [Anaconda](http://continuum.io/downloads.html) version). I don't know much python though, so yeah. Stefan Sinclair is working on 'voyant notebooks' which uses the same general idea to wrap analysis around Voyant, so I'm looking forward to that. Ipython can be used [to call R](http://nbviewer.ipython.org/github/ipython/ipython/blob/3607712653c66d63e0d7f13f073bde8c0f209ba8/docs/examples/notebooks/rmagic_extension.ipynb), which is cool, but it's still early days for me (here's a [neat example passing data to R's ggplot](http://nbviewer.ipython.org/gist/yoavram/5280132)2). So maybe that's just the wrong tool.  Much of what I want to do, at least as far as R is concerned is covered in this post by Robert Flight on '[creating an analysis as a package and vignette](http://rmflight.github.io/posts/2014/07/vignetteAnalysis.html)' in R studio. And there's also this, for making sure things are reproducible - '[packrat](http://rstudio.github.io/packrat/)' Some combination of all of this I expect will be the solution that'll work for me. Soon I want to start doing some more agent based modeling & simulation work, and it's mission critical that I sort out my data management, notebooks, versioning etc first _this time_. God, you should see the mess around here from the last time!

## Comments

**[Caleb McDaniel (@wcaleb)](#31319 "2014-09-20 21:55:32"):** Thanks for the link! Glad that you're interested in this, too! Gitit is, I agree, not the most user-friendly system out of the gate. Don't know it you saw it, but I subsequently wrote up a post about [the technical aspects of my system](http://wcm1.web.rice.edu/plain-text-citations.html).

**[Shawn](#31320 "2014-09-22 21:32:37"):** Thanks Caleb! I would've like to try Gitit, but was utterly stumped right at the word go. But I have gotten to this... http://shawngraham.github.io/open-notebook/ll_CC/#!index.md

**[Caleb McDaniel (@wcaleb)](#31321 "2014-09-23 09:55:01"):** Nice!

