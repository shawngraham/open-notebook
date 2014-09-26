title: Yahoo Pipes and the Pleiades Project
link: http://electricarchaeology.ca/2007/09/27/yahoo-pipes-and-the-pleiades-project/
author: fhg1711
description: 
post_id: 71
created: 2007/09/27 10:13:03
created_gmt: 2007/09/27 15:13:03
comment_status: open
post_name: yahoo-pipes-and-the-pleiades-project
status: publish
post_type: post

# Yahoo Pipes and the Pleiades Project

I recently wrote about trying to get [Platial](http://platial.com) to map various kinds of data. Today I tried [Yahoo Pipes](http://pipes.yahoo.com/pipes/). Again, the task was relatively straightforward: can I get an RSS feed of archaeological data - such as ancient places in the (non-mapped) [Pleaides website](http://pleiades.stoa.org/) database - onto a map without having to point-and-click each individual place? First of all, I searched the various existing pipes that others have created. A pipe, by the way, is a collection of different modules 'piped' together to mash together different kinds of, and sources of, data. The pipe updates itself when the in-coming data changes. I found the [geo-annotated Reuters news pipe, by el80n](http://pipes.yahoo.com/pipes/pipe.info?_id=gGThvN_62xG2JH50ZoQMOQ). This pipe collects information from the Reuters news-feed, extracts the locational information from it, finds out the actual coordinates for that location, and then displays [the result](http://pipes.yahoo.com/pipes/pipe.info?_id=ZBsn7kj52xGrEUMRo_NLYQ) on a yahoo map. ![pipe1.JPG](http://electricarchaeologist.files.wordpress.com/2007/09/pipe1.JPG)I swapped the feed from Reuters to Pleiades' [Archaic places](http://pleiades.stoa.org/places/archaic), and la voila. A number of the sites from that list turned up on the map. Now, there're a few bugs in it. The place-extractor looks at the feed, and grabs the first 'obvious' place name. In Reuters, that's the modern name. In Pleaides, that's the ancient name. The database that contains the geocoding only has modern names, so things get a little odd. For instance, [Artamis (modern Messa),](http://pleiades.stoa.org/places/373737/) gets mapped to an island in the South China Sea. There's a query builder in the pipe, so I need to figure out how to get it to grab the modern name, while labeling the map with the ancient name. All of this took about an hour. I had never used pipes before, and all I really did was swap feeds. Imagine what somebody who knew what they were doing could accomplish! You may view the live result [here](http://pipes.yahoo.com/pipes/pipe.info?_id=Eli7GQdt3BGigpuzODY80A). ![pipe2.JPG](http://electricarchaeologist.files.wordpress.com/2007/09/pipe2.JPG)

## Comments

**[Shawn](#1803 "2009-01-23 11:16:42"):** When you open up Pipes, there are a number of building blocks along the side that you can drag-and-drop into the building area. You then can adjust each one's parameters, and then you drag from the output thingy (a small bubble at the bottom of the block) to the input of the next block (the bubble at the side). You have to watch to make sure each output is a compatible input. You can also drag-and-drop complete other 'pipes'. What I did was more or less save a copy of the geoannotated reuters news and swap the feed from Reuters to the feed from Pleiades. In truth, I haven't played with pipes for some time, so when I visited mine, I found it wasn't working any more.

**[Mina](#1791 "2009-01-15 02:28:50"):** Hi. I have a question about your work related to Yahoo Pipe. can I ask some question ?

**[Shawn](#1792 "2009-01-15 09:53:44"):** Sure - what would you like to know?

**[Mina](#1793 "2009-01-15 11:50:52"):** I think You used google map feed .and then mixed up them.how? can you explain more ? Thanks.

