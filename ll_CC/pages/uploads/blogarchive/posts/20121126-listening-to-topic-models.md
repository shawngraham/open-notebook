title: Listening to Topic Models
link: http://electricarchaeology.ca/2012/11/26/listening-to-topic-models/
author: fhg1711
description: 
post_id: 1623
created: 2012/11/26 11:43:51
created_gmt: 2012/11/26 16:43:51
comment_status: open
post_name: listening-to-topic-models
status: publish
post_type: post

# Listening to Topic Models

![](http://electricarchaeologist.files.wordpress.com/2012/11/playing-topic-models.png?w=150)I want to explore alternate ways of 'visualizing' patterns in data, beyond the visual. To that end, I've taken the major topics & their proportions from a topic model generated with MALLET and run them through the [Musical Algortihms ](http://musicalgorithms.ewu.edu/)site at EWU. 1\. I obtained data from the [Portable Antiquities Scheme](http://finds.org.uk/) related to ceramic building materials recovered by the scheme (why this and not something else? I'm thinking about brick these days. No other reason). 2\. I created a[ topic model](http://programminghistorian.org/lessons/topic-modeling-and-mallet) of the descriptor text. 3\. I take the composition file that is outputed (the one that can be read as 'in document 2 the major topic is 4 at 25%, then topic 6 at 12%...' etc), and grab the topics and the amount by which they compose the document- so the first two columns. I turn the decimals into whole numbers by multiplying by 100. 4\. I put these two columns into Musical Algorithmns. I perform the modulo scaling, then I invert the numbers. I used a 1 for the duration of the note. You can listen to the [output here](http://graeworks.net/topic-model/output.mid) So what does it sound like? Well, I haven't got there yet. But... if you do the whole process again, this time with topic models derived from [writing qua writing](http://graeworks.net/topic-model/play-the-past/output_csv/) (rather than database entries; the link takes you to topic models I did from posts on [Play the Past](http://playthepast.org)), you [get this](http://graeworks.net/topic-model/play-the-past/output-play-the-past.mid).  Which sounds markedly different. More structure. Less repetition. Anyway, this is obviously something that'll require some more playing around (ha - see what I did there?)

## Comments

**[kristina1990](#8732 "2012-12-14 00:31:36"):** This is such a cool idea :D Have you concluded that Ceramic databases are not very good composers? :P

**[Shawn](#8751 "2012-12-14 10:34:20"):** Well, it's interesting. You'd expect a database to be very structured, and for that structure to be reflected in repeating rythmns etc. There is a bit of a drone to it though...

**[kristina1990](#8838 "2012-12-17 11:59:27"):** Well, datasets often have outliers and these outliers were actually noticeable in the music as well. I though that was pretty interesting.

