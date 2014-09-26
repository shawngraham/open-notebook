title: Artefact Networks Analysis - Thinking Out Loud
link: http://electricarchaeology.ca/2012/06/27/artefact-networks-analysis-thinking-out-loud/
author: fhg1711
description: 
post_id: 1508
created: 2012/06/27 11:19:54
created_gmt: 2012/06/27 16:19:54
comment_status: open
post_name: artefact-networks-analysis-thinking-out-loud
status: publish
post_type: post

# Artefact Networks Analysis - Thinking Out Loud

What follows is a process of me thinking out loud whilst working with data related to the Tiber Valley Brick Industry. If we look at the distribution of stamped bricks across the Tiber Valley (as collected by the BSR), we can work out some of the implications for production and consumption by considering the way location, stamp type, and fabric of the brick intersect. I looked at every combination for every site in the South Etruria Survey, having done archaeometric analysis on the same collection to the point where I could say that 'these two bricks share the same fabric'. Here is the table (where 1 implies same, 0 implies different): 

Combination
Findspot
Stamp
Fabric

A
1
1
1

B
1
1
0

C
1
0
0

D
1
0
1

E
0
0
0

F
0
0
1

G
0
1
1

H
0
1
0
Which we may collapse, as some of these become functionally the same. 1\. A&G: imply a common origin and distribution 2\. B&H: imply a geographically dispersed production 3\. D&F: imply a single clay source exploited by different _figlinae_. Finally, there is situation 'C', which suggests that builders at a site had access to a variety of sources. Since we can closely date many of the bricks, we can look at how these modes play out over time (remembering that this is a tally of _relationships_): 

Julio-Claudian
Flavian
Nerva-Hadrian
Antoninus Pius-Commodus
Severan
Late
Total

Mode 1 (A/G)
10
2
2
6
2
22

Mode 2 (B/H)
54
14
4
4
6
82

Mode 3 (D/F)
13
13
7
7
2
42

Combination C ("Consumer Choice")
17
7
6
2
1
2
35

Total
94
36
19
19
11
2
181
We can graph that: [caption id="attachment_1509" align="aligncenter" width="300"]![](http://electricarchaeologist.files.wordpress.com/2012/06/brick-modes.png?w=300) After Fig. 4.2, Graham 2006 Ex Figlinis[/caption] Thus, by simply categorizing the relationships and graphing their evolution over time, we develop a complex view of the changing dynamics of production and consumption in the Tiber Valley. However, we can also represent these relationships as a multi-modal network graph. The nodes in this graph are bricks and locations. Some of those locations, like the findspots, are known in space. Other locations, like the precise x,y, of the clay bodies is unknown or can be suggested to be roughly in a particular area. I create a directed graph where clay sources are 'source' and bricks are 'target', and where bricks are 'source' to findspots. I also categorize the linkages according to the relationships determined above. The result is below (Fig 1), where colours = communities and size = betweeness: [caption id="attachment_1511" align="aligncenter" width="181"]![](http://electricarchaeologist.files.wordpress.com/2012/06/all-combos.png?w=297) Fig 1. All relationships in evidence in Tiber Valley Roman Bricks[/caption] [all relationships in tv-bricks ](http://electricarchaeologist.files.wordpress.com/2012/06/all-combos-table-4-3.pdf) (zoomable pdf of the png image) One can then filter this graph, looking for instance for relationships of type B (Fig 2). What I would really like is to be able to lay these graphs out so that my findspots and claysources can be pinned to geographic space, while allowing the bricks themselves and their relationships to float freely. This would require a layout plugin that understood how to apply a different layout algorithm to nodes with null latitude/longitude values. That at the moment is rather beyond me. [caption id="attachment_1512" align="aligncenter" width="134"]![](http://electricarchaeologist.files.wordpress.com/2012/06/filtered-for-b.png?w=300) Fig 2. Type B relationships[/caption] Finally, one can collapse this graph into its component communities, and look at those relationships.[ In this PDF](http://electricarchaeologist.files.wordpress.com/2012/06/a-single-community.pdf) you can zoom in and see not just the bricks, but also the kinds of relationships, and the clay body that seems to go with this group (B6, somewhere in the neiborhood of Fiano Romano-ish). [caption id="attachment_1513" align="aligncenter" width="159"]![](http://electricarchaeologist.files.wordpress.com/2012/06/brick-modularity.png?w=300) Fig 3. Community 1[/caption] Here we collapse the communities into single nodes, and run betweeness on this graph (fig 4). We end up with community 6 being 'most between'; this community seems to source its clay from somewhere in the upper Sabina in the Forum Novum area (see chapter 3 of Ex Figlinis). Next most between is community 1, which sources in South Etruria in the Fiano Romano area and in the lower Sabina. Then we have community 8, which is pulling from either side of the Tiber in the lower reaches of South Etruria and the Sabina. Community 6 has within it two sites and six bricks -TVP3592 and TVP2304; bricks se18, se13, se116, se104, se156, and se152. These bricks are first century bricks from the Tonneiana/Viccianae, PL (which might mean 'Portus Licini'), someone named CASPR and a Q. Sulpicius Sabinus. What does 'betweeness' mean in this context here? Obviously, a question with a lot riding on it, but off the top of my head, if the association of PL with Portus Licini, which was a known brick warehouse is suggestive. Community 1 is a much more complicated group with six sites and 15 brickstamps. Figlinae mentioned are Tonneina/Viccianae again, some Domitianae Veteres, an explicit Portus Licini stamp, a few tied to the Domitiana family, some late 'officinae' stamps (including 'Boconiana', which implicitly suggests the town of Bocignano).