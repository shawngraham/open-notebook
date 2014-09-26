title: Reading 'Writing History in the Digital Age' at a Distance
link: http://electricarchaeology.ca/2011/11/01/reading-writing-history-in-the-digital-age-at-a-distance/
author: fhg1711
description: 
post_id: 1292
created: 2011/11/01 11:21:30
created_gmt: 2011/11/01 16:21:30
comment_status: open
post_name: reading-writing-history-in-the-digital-age-at-a-distance
status: publish
post_type: post

# Reading 'Writing History in the Digital Age' at a Distance

[caption id="attachment_1293" align="alignright" width="300" caption="Topics by authors in Writing History in the Digital Age"]![](http://electricarchaeologist.files.wordpress.com/2011/11/writing-digital-history-topic-model.png?w=300)[/caption] I and my students have made some contributions to '[Writing History in the Digital Age](http://writinghistory.trincoll.edu/)', the born-digital volume edited by  [Jack Dougherty](http://bit.ly/jackdougherty) and [Kristen Nawrotzki](https://www.h-net.org/people/person_view.php?id=124081). Rather than reflect on the writing process, I thought I'd topic model the volume to see what patterns emerged in the contributions. I use [Mallet ](http://mallet.cs.umass.edu/)to do this. I've posted earlier about [how to get Mallet running](http://electricarchaeologist.wordpress.com/2011/08/30/getting-started-with-mallet-and-topic-modeling/). I used [Outwit Hub](http://www.outwit.com/products/hub/) to scrape each individual paragraph from each paper (> 700 paragraphs) into a CSV file (I did not scrape block quotes, so my paragraph numbers are slightly out of sync with those used on the Writing History website). I used the Textme excel macro (google it; it lives in multiple versions and requires a bit of modification to work exactly the way you want it to) to save each paragraph into its own unique text file, which I then load into Mallet. Phew. Now, the tricky part with Mallet is deciding how many topics you want it to look for. Finding the *right* number of topics requires a bit of iteration - start with say 10. Look at the resulting composition of files to topics. If an inordinate number of files all fall into one topic, you don't have enough granularity yet. As an initial read, I went with [15 topics](http://electricarchaeologist.files.wordpress.com/2011/11/whkeys.docx). One topic - which I'll label 'working with data' - had quite a large number of files [(composition document)](http://electricarchaeologist.files.wordpress.com/2011/11/wh-composition-labelled1.xlsx) (remember, the individual paragraphs from the papers). Ideally, I would re-run the analysis with a greater number of topics, so that the 'working with data' topic would get broken up. I also [graphed the results](http://electricarchaeologist.files.wordpress.com/2011/11/writing-history-in-the-digital-age-topics-by-authors.pdf), so that each author is linked to the topics which compose his or her paper; the thickness of the line indicates multiple paragraphs with that topic. I have also graphed topics by individual paragraphs, but the granularity isn't ideal making the resulting visual not all that useful. The colours correspond with the 'modularity' of the graph, that is, communities of similar patterns of connections. The size of the node represents 'betweeness' on all paths between every pair of nodes. So what does it all mean? At the level of paragraph-by-topic, if we had the correct level of granularity, one might be able to read the entire volume by treating the graph as a guide to hyperlinking from paragraph to paragraph, perhaps - a machine generated map/index of the internal structure of ideas. At the level of individual authors, it perhaps suggests papers to read together and the organizing themes of the volume. This is of course a quick and dirty visualization and analysis, and my initial impressions. More time and consideration, greater granularity, is to be desired. 

Topic, Authors
Community

Crowdsourcing
0

Students' Learning
0

graham
0

grahammassiefeuerherm
0

sikarskie
0

Working with Data
1

Video
1

faltesek
1

Games
1

noonan
1

poe
1

zucconietal
1

castaneda
2

Activism, Protests
2

African Americans and the South
2

Primary Resources, Teaching, and Libraries
2

haber
2

judkins
2

madsen-brooks
2

sklardubin
2

tomasek
2

wolff
2

Blogging and Peer Interactions
3

Monitoring Wikipedia
3

introduction
3

jarret
3

lawrence
3

saxtonetal
3

seligman
3

bauer
4

Keywords and Search
4

cummings
4

Japan and History
4

Writing Process
4

dorn
4

## Comments

**[amirazara](#5084 "2011-11-11 12:34:25"):** It's nice to see that someone is interested in the same topics regarding archaeology as I am. Nice post! www.amirazara.wordpress.com

