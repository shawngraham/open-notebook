title: An Open Research Notebook Workflow with Scrivener and Github Part 2: Now With Dillinger.io!
link: http://electricarchaeology.ca/2014/09/19/an-open-research-notebook-workflow-with-scrivener-and-github-part-2-now-with-dillinger-io/
author: fhg1711
description: 
post_id: 2211
created: 2014/09/19 13:38:07
created_gmt: 2014/09/19 18:38:07
comment_status: open
post_name: an-open-research-notebook-workflow-with-scrivener-and-github-part-2-now-with-dillinger-io
status: publish
post_type: post

# An Open Research Notebook Workflow with Scrivener and Github Part 2: Now With Dillinger.io!

A couple of updates: 

### First item

The four scripts that [sparkygetsthegirl](http://sparkygetsthegirl.com/blog/2014/08/28/scrivener-dropbox-android-writing-app/) crafted allow him to 1\. write in Scrivener, 2\. sync to a Dropbox folder, 3\. Convert to md, 4\. then open those md files on an android table to write/edit/add 5\. and then reconvert to rtf for syncing back into Scrivener. ![Screen Shot 2014-09-19 at 2.24.27 PM](http://electricarchaeologist.files.wordpress.com/2014/09/screen-shot-2014-09-19-at-2-24-27-pm.png?w=300)I wondered to myself, what about some of the online markdown editors? Dillinger.io can scan Dropbox for md files. So, I went to [Dillinger.io](http://dillinger.io), linked it to my dropbox, scanned for md files, and lo! I found my project notes. So if the syncing folder is shared with other users, they can edit the notecards via Dillinger. Cool, eh? Not everyone has a native app for editing, so they can just point their browser's device to the website. I'm sure there are more options out there. 

### Second Item

I was getting syncing errors because I wasn't flipping the md back to rtf. But, one caveat: when I went to run the md to rtf script, to get my changes back into Scrivener (and then sync), things seemed to go very wonky indeed. One card was now blank, the others were all Scrivener's markup but Scrivener wasn't recognizing it. So I _think_ the problem is me doing things out of order. I continue to play. 

### Third Item

I automated running of the conversion scripts. You can see my automator set up in the screenshot below. Again, I saved it as an application on my desktop. First step is to grab the right folder. Second, to open the terminal, input the commands, then close the terminal. ![Screen Shot 2014-09-19 at 2.36.03 PM](http://electricarchaeologist.files.wordpress.com/2014/09/screen-shot-2014-09-19-at-2-36-03-pm.png?w=300) Postscript I was asked why on earth would I want to share my research notes? Many many reasons - see [Caleb McDaniel's post](http://wcm1.web.rice.edu/open-notebook-history.html), for instance - but one other feature is that, because I'm doing this on Github, a person could fork (copy) my entire research archive. They could then use it to build upon. Github keeps track of who forks what, so forking becomes a kind of mass citation and breadcrumb trail showing who had an idea first. Moreover, [github code (or in this case, my research archive) can be archived](http://mozillascience.github.io/code-research-object/) on [figshare](http://figshare.com) too, thus giving it a unique DOI *and* proper digital archiving in multiple locations. Kinda neat, eh?