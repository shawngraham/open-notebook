title: Coins from Sirmium in the PAS database
link: http://electricarchaeology.ca/2012/10/02/coins-from-sirmium-in-the-pas-database/
author: fhg1711
description: 
post_id: 1582
created: 2012/10/02 12:15:24
created_gmt: 2012/10/02 17:15:24
comment_status: open
post_name: coins-from-sirmium-in-the-pas-database
status: publish
post_type: post

# Coins from Sirmium in the PAS database

![](http://electricarchaeologist.files.wordpress.com/2012/10/coins-from-sirmium-in-the-uk-pas.png?w=300)Interested in networks, and looking for an exemplar that I could do in my class, I turned to the Portable Antiquities Scheme database, and extracted coins known to have originated from the mint at Sirmium (modern Sremska Mitrovica, Serbia). [You can find the list here](http://finds.org.uk/database/search/results/mint/196). I downloaded the data as a CSV. Looking at it, it seemed to me that a multimodal graph of coin to findspot, to material, to date, and to ruling house might be useful (and of course could be transformed into single mode graphs as necessary).  So I made a list, where the 21 coins were marked 'source' and the other data were marked 'target' (which means that I repeated the coins four times in my list). Here is the resulting network in a zoomable pdf: [coins from Sirmium in the UK - PAS](http://electricarchaeologist.files.wordpress.com/2012/10/coins-from-sirmium-in-the-uk-pas.pdf). I ran modularity and betweeness centrality. Most central nodes were 'copper' as a material, Constantine I and II, and then coins [283287 ](http://finds.org.uk/database/artefacts/record/id/283287)and [433211 ](http://finds.org.uk/database/artefacts/record/id/433211)and the date, AD324.![](http://electricarchaeologist.files.wordpress.com/2012/10/modularity.png?w=300) If you revisualize the graph so that the communities are grouped into single nodes, the most 'between' of these communities is group 3, which has the following data: coins [410195](http://finds.org.uk/database/artefacts/record/id/410195), [272397](http://finds.org.uk/database/artefacts/record/id/272397), [451670](http://finds.org.uk/database/artefacts/record/id/451670), [474164](http://finds.org.uk/database/artefacts/record/id/474164), [283287](http://finds.org.uk/database/artefacts/record/id/283287), silver as a material, Constantius II and Valentinian I, and Bedford, Isle of Wight, North Kesteven, and the Vale of White Horse. I'm no numismatist, but perhaps the coin folks out there can take a look at this small experiment, and tell me if these patterns are meaningful to them... my csv files & gephi files are here: Coins from Sirmium, a networking experiment. Shawn Graham. [fig**share**](http://figshare.com). Retrieved 17:15, Oct 02, 2012 (GMT) <http://dx.doi.org/10.6084/m9.figshare.96219>