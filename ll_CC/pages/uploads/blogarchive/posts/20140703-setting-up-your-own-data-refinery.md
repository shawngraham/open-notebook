title: Setting up your own Data Refinery
link: http://electricarchaeology.ca/2014/07/03/setting-up-your-own-data-refinery/
author: fhg1711
description: 
post_id: 2087
created: 2014/07/03 13:12:27
created_gmt: 2014/07/03 18:12:27
comment_status: open
post_name: setting-up-your-own-data-refinery
status: publish
post_type: post

# Setting up your own Data Refinery

[caption id="attachment_2089" align="alignleft" width="240"]![Refinery at Oxymoron, by Wyatt Wellman, cc by-sa 2.0. Flickr.](http://electricarchaeologist.files.wordpress.com/2014/07/3828101802_08e0b6428b_m.jpg) Refinery at Oxymoron, by Wyatt Wellman, cc by-sa 2.0. Flickr.[/caption] _I've been playing with a Mac. I've been a windows person for a long time, so bear with me. _ I'm setting up a number of platforms locally for data mining. But since what I'm *really* doing is smelting the ore of data scraped using things like Outwit Hub or [Import.io ](https://import.io/)(the 'mining operation', in this tortured analogy), what I'm setting up is a data refinery. Web based services are awesome, but if you're dealing with sensitive data (like oral history interviews, for example) you need something local - this will also help with your ethics board review too.  Onwards! 

## Voyant-Tools

You can now set Voyant-Tools up locally, keeping your data safe and sound. [The documentation and downloads are all on this page](http://docs.voyant-tools.org/resources/run-your-own/voyant-server/). This was an incredibly easy setup on Mac. Unzip, double-click voyant-tools.jar, and boom you've got Voyant-Tools puttering away in your browser. It'll be at  [http://127.0.0.1:8888](http://127.0.0.1:8888/). You can also hit the cogwheel icon in the top right to run your corpus through all sorts of other tools that come with Voyant but aren't there on the main layout. You'll want 'export corpus with other tool'. You'll end up with a url something like http://127.0.0.1:8888/tool/RezoViz/?corpus=1404405786475.8384 . You can then swap the name of any other tool in that URL (to save time). RezoViz by the way uses named entity extraction to construct a network of entities mentioned in the same documents. So if you upload your corpus in small-ish chunks (paragraphs; pages; every 1000 words, whatever) you can see how it all ties together this way. From the cogwheel icon on the RezoViz layout, you can get .net which you can then import into Gephi. How frickin' cool is that? 

## Overview Project

[vimeo 71483614 w=500 h=281] Topic modeling is all the rage, and yes, you should have MALLET or the Stanford TMT or R on your machine. But sometimes, it's nice to just see something rather like a dendrogram of folders with progressively finer levels of self-similarity. Overview does [term-frequency inverse document frequency ](http://en.wikipedia.org/wiki/Tf%E2%80%93idf)weightings to figure out similarity of documents. The instructions (for all platforms) [are here](https://github.com/overview/overview-server/wiki/Installing-and-Running-Overview). It's not quite as painless as Voyant, but it's pretty darn close. You'll need to have [Postgres](http://postgresapp.com/) - download, install, run it once, then download Overview. You need to have Java 7. (At some point, you'll probably need to look into r[unning multiple versions of Java](https://www.google.ca/search?q=running+multiple+versions+of+java&oq=running+multiple+versions+of+java&aqs=chrome..69i57j69i60l3j69i59l2.3464j0j4&sourceid=chrome&es_sm=91&ie=UTF-8#q=running+multiple+versions+of+java), if you continue to add elements to your refinery). Then: 

  1. Ctrl-Click or Right-click on `Overview for Mac OS X.command` and select `Open`. When the dialog box asks if you are sure you want to open the application, click on the `Open` button. From then on, you can start Overview by double-clicking on `Overview for Mac OS X.command`.
  2. Browse to [http://localhost:9000](http://localhost:9000/) and log in as `admin@overviewproject.org` with password`admin@overviewproject.org`.
And you now have Overview running. You can do many many things with Overview - it'll read pdfs, for instance, which you can then export within a csv file. You can tag folders and export those tags, to do some fun visualizations with the next part of your refinery, RAW. [caption id="" align="aligncenter" width="363"]![](http://overview.ap.org/wp-content/uploads/2014/06/Exported-tags.png) Tags exported from Overview[/caption] [caption id="" align="aligncenter" width="471"]![](http://overview.ap.org/wp-content/uploads/2013/04/Screen-Shot-2013-12-03-at-7.33.58-AM-1024x750.png) Tags visualized. This wasn't done with Raw (but rather, a commercial piece of software), but you get the idea.[/caption] 

## RAW

[caption id="attachment_2088" align="alignleft" width="300"]![Flow diagram in Raw, using sample movie data](http://electricarchaeologist.files.wordpress.com/2014/07/screen-shot-2014-07-03-at-1-55-47-pm.png?w=300) Flow diagram in Raw, using sample movie data[/caption] [Raw](http://app.raw.densitydesign.org/) does wonderful things with CSV formatted data, all in your browser. You can use the webapp version; nothing gets communicated to the server. But, still, it's nice to keep it close to home. So, [you can get Raw source code here.](https://github.com/densitydesign/raw) It's a little trickier to install than the others. First thing: you'll need [Bower](http://bower.io/#installing-bower). But you can't install Bower without [Node.js and npm](http://nodejs.org/). So, go to Node.js and hit install. Then, download Raw. Unzip Raw and go to that folder. To install Bower, type 

$ sudo npm install -g bower

Once the dust settles, there's a bunch of dependencies to install. Remember, you're in the Raw folder. Type:
    
    
    $ bower install

When the dust clears again, and assuming you have [Python](https://www.python.org/) installed on your machine, fire Raw up in a server: 
    
    
    $ python -m SimpleHTTPServer 4000

(If you don't have python, well, go get python. I'll wait). Then in your browser go to 
    
    
    localhost:4000

And you can now do some funky visualizations of your data. There are a number of chart types packaged with Raw, but you can also develop your own - [here's the documentation](https://github.com/densitydesign/raw/wiki/Adding-New-Charts). [Michelle Moravec](https://twitter.com/ProfessMoravec) has been doing some lovely work visualizing her historical research using Raw. [You should check it out](http://historyinthecity.blogspot.ca/2013/12/visualizing-gender-in-history-of-woman.html).  

## Your Open Source Data Refinery

With these three pieces of data refinery infrastructure installed on your machine, or in your local digital history computer lab, you'll have no excuse not to start adding some distant reading perspective to your method. Go. Do it now.

## Comments

**[krunce](#31286 "2014-07-07 02:36:19"):** This post is perfect: thank you for it! After our convo, I've cooked up this strange dream of playing around with data mining and topic modelling with online commentary on sites I feel connected to, like Globe & Mail or the tragically sophisticated forum discussions around Megatokyo. Probably won't get to it this summer, but I'll definitely come back to this post when I get closer!

