title: Mining a Day of Archaeology
link: http://electricarchaeology.ca/2012/07/09/mining-a-day-of-archaeology/
author: fhg1711
description: 
post_id: 1520
created: 2012/07/09 12:36:32
created_gmt: 2012/07/09 17:36:32
comment_status: open
post_name: mining-a-day-of-archaeology
status: publish
post_type: post

# Mining a Day of Archaeology

![](http://graeworks.net/topic-model/doa2012/doa-topics.png)The [Day of Archaeology](http://dayofarchaeology.com) is modeled after the [Day of Digital Humanities](http://dayofdh2012.artsrn.ualberta.ca/). Archaeologists from around the world take a few moments to blog about what they're doing, _right now_. This year, it was on June 29th. It's a fascinating window into a fascinating profession. As an archaeologist-cum-digital-humanities person, the obvious thing to do with all of this info (over 700 individual archaeologists; over 300 individual posts of some 250-500 words each, at least) is to mine it, to analyze it, to topic model it. What are the discourses of practicing archaeologists? 

  1. The first thing is to collect all of the information. I'm using OutWit Hub to scrape every post. Now scraping can be morally dubious, but happily the organizers of DoA and all of its contributors agree to a creative commons attribution. Designing a scraper involves looking at the source code for the page, figuring out the page structure, and identifying the tags that enclose the information that one wants to collect. Then, OutWit can be sent forth to work through each page in succession. The resulting information can then be exported into Excel; I send it over as a csv file so that I can then do further work with it. ([The CSV file may be downloaded here](http://graeworks.net/topic-model/doa2012/all posts doa 2012.csv))
  2. I then use a macro in Excel to save each individual row as an individual text files, into a separate folder. This folder can be zipped and uploaded into Voyant Tools.
  3. Finally, I can point the[ Mallet Java GUI](http://electricarchaeology.ca/2011/11/11/topic-modeling-with-the-java-gui-gephi/) at the original csv file and [topic model all of the posts](http://graeworks.net/topic-model/doa2012/all_topics.html) (400 iterations, with 40 topic words and topic proportion threshold 0.05, for 20 topics);  I then visualize the interrelationships of the topics using Gephi.
In this post, I'm going to provide you with links to the data in various tools, and give a first pass over the data. Then, why not play with this info for yourself, and see what you find? Perhaps we can all crowdsource an article out of this; comments and findings in the comments please! **Let's begin, shall we?** This is what I find. First, the topics ([related files here](http://graeworks.net/topic-model/doa2012/)): 

#### List of Topics

1.
[archaeological information artifacts museum years university research cultural collection important collections sites including county center materials management include projects includes resource curator work archaeologists focus identify individual ago assistant provide recovered thousands analysis history artifact southern tasks cooper idaho patterns](http://graeworks.net/topic-model/doa2012/Topics/Topic1.html)

2.
[war shropshire number uk british castle whilst military county royalist local london young market royal active base money significant nice july command clear australia rescue country hard shrewsbury memorial army news march garrison britain considered bristol charles highly leaving support](http://graeworks.net/topic-model/doa2012/Topics/Topic2.html)

3.
[de la en el los una por del es las para se lo con arqueolog madrid al amtta hist como ya os museo english patrimonio civil arqueol historia spanish su crisis campus cruz dayofarch ser pero part ver punto law](http://graeworks.net/topic-model/doa2012/Topics/Topic3.html)

4.
[find http www conservation blog shelf images months object follow number post image create org photos completely leather task finish major preserved produced department stop add conditions content set watch possibly laarc helping arts tiny pictures rob detail excitement examining](http://graeworks.net/topic-model/doa2012/Topics/Topic4.html)

5.
[finds roman interesting iron medieval glass building post excavated age pottery found large years london final today bones bone metal discovered part working date houses archive fragments pieces based period animal vessel assemblage scheme specialist general evidence parts range amazing](http://graeworks.net/topic-model/doa2012/Topics/Topic5.html)

6.
[working long stone field part half survey results end high understand equipment tools weather water notes modern walk located techniques hand sherds system structures hours reports valley lost process variety prehistoric complete tool personal level looked shell bag takes findings](http://graeworks.net/topic-model/doa2012/Topics/Topic6.html)

7.
[small city early site record century ve recording big soil present analysis recorded common excavated back inside middle stage study context picture wood piece beer colleague deposits simple written suggest special air map shoe put ll size upper wild generally](http://graeworks.net/topic-model/doa2012/Topics/Topic7.html)

8.
[site found excavation today june pm twitter test excavations areas maps vitaemilia trench worked dayofarch pit digging tea section surface find samples construction block hard clay emily natural place wright wall dug pits fill left storage paperwork excavating feature opened](http://graeworks.net/topic-model/doa2012/Topics/Topic8.html)

9.
[archaeological excavation archaeologists community local past house team excavations professional town members human groups volunteers main information late ireland interest early st children northern medieval involved programme friends role association similar enjoy revealed result scientific gardens city give structure irish](http://graeworks.net/topic-model/doa2012/Topics/Topic9.html)

10.
[field day students year summer school reading week continue lab university learn photo program dig questions process called student season graduate page river campus digging unit crew experience class undergraduate veterans features larger dirt director learning sense order indiana artifacts](http://graeworks.net/topic-model/doa2012/Topics/Topic10.html)

11.
[archaeology public historic historical archaeological national state park project day house today cemetery society archaeologist american history philadelphia pennsylvania june media meeting photographs york university spent states usa work resources teaching anthropology arkansas native ideas united preservation document college region](http://graeworks.net/topic-model/doa2012/Topics/Topic11.html)

12.
[world ancient art material open write people recently make website plan starting institute centre studies related idea web street current yesterday july monday series lovely issues individuals exciting article received wrote giving italy topic term lives church earlier week left](http://graeworks.net/topic-model/doa2012/Topics/Topic12.html)

13.
[archaeology project day heritage work report team week activities staff month busy time working emails blog wessex today planning archaeological friday check due fieldwork visit company environment officer previous design exciting office manager event based current reports development side table](http://graeworks.net/topic-model/doa2012/Topics/Topic13.html)

14.

## Comments

**[Nicolas Laracuente](#7077 "2012-07-09 12:57:50"):** I was wondering if there was a way to scrape the images associated with the articles as well. Atlas.ti has functionality for coding images and video in discourse analysis... I'm not familiar with the programs your using here though.

**[Shawn](#7078 "2012-07-09 13:01:07"):** Hi Nicolas, Outwit can grab images or other files (as could something like downthemall, firefox plugin), but for subsequent analysis, I wouldn't know where to begin. I haven't played with Atlas.ti.

**[Nicolas Laracuente](#7079 "2012-07-09 13:46:17"):** I am playing with Atlas.ti as a way to analyzing discourse in historic documents associated with the distilling industry. I'm not an expert in it (just tinkering at the moment) but I think that photos can be tagged (the same way you tag people on Facebook) with codes you have assigned for the analysis. Tags like "paperwork, artifact, archives, computer, office" might be a place to start. Then ATLAS.ti can take those tags correlate them with codes you've assigned to text and make a network map with nodes (similar in appearance to what you posted above from Voyant) although what you can do with that info is probably different. I've got a big project I'm trying to finish in the next week or so, but after that I might try to integrate the data into ATLAS if the baby lets me (we are getting teeth right now so my spare time is non-existent)

**[abercrombie pas cher](#11265 "2013-11-27 23:53:47"):** En fait, Rama Yade n'est pas ¨¤ jour. Car sa pr¨¦vision de croissance pour la France l'an prochain de 0,8% ¨¤ 1% ; soit de juste en-dessous ¨¤ juste au-dessus du chiffrage de Bercy... En revanche, elle a quelques mois de retard pour la Commission europ¨¦enne. D¨¨s mai, la croissance fran?aise pour 2014. abercrombie pas cher http://www.agenceneptune.com/FR/Abercrombie/

