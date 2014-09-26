title: Visualizing THATCamp
link: http://electricarchaeology.ca/2012/09/11/visualizing-thatcamp/
author: fhg1711
description: 
post_id: 1564
created: 2012/09/11 12:59:06
created_gmt: 2012/09/11 17:59:06
comment_status: open
post_name: visualizing-thatcamp
status: publish
post_type: post

# Visualizing THATCamp

![](http://electricarchaeologist.files.wordpress.com/2012/09/thatcamp2012.png?w=300)[THATCamps](http://thatcamp.org) are quite popular. [I'm throwing one myself](http://accessibility2012.thatcamp.org/). But who are the people talking about them on Twitter? What does the THATCamp look like on the Twitterverse? I used [NodeXL ](http://nodexl.codeplex.com/)to retrieve the data - a search for tweets, people, and the links between them. I then visualized the data in [Gephi](http://gephi.org), where colour = community (per Gephi's modularity routine) and sized the nodes (individual Twitterers) using Pagerank, on the premise that this was a directed graph and one should follow the links (although there was little difference with Betweeness Centrality. Major players are still major, either way). I found 233 individuals, linked together by 4435 edges. Some general stats on this directed network: 

Top 10 Vertices, Ranked by Betweenness Centrality
Betweenness Centrality

thatcamp
10493.93299

marindacos
3381.65598

amandafrench
2530.589717

openeditionsays
2491.27153

inactinique
2183.450362

briancroxall
2093.876857

piotrr70
2014.064889

brettbobley
1798.013658

miriamkp
1693.203103

melissaterras
1596.42585
 

Top Replied-To in Entire Graph
Entire Graph Count

colleengreene
4

thatcamp
3

rosemarysewart
2

normasalim
2

janaremy
2

spagnoloacht
1

chuckrybak
1

lawnsports
1

ncecire
1

academicdave
1

Top Mentioned in Entire Graph
Entire Graph Count

thatcamp
25

piotrr70
25

briancroxall
17

ncecire
16

spouyllau
14

thtcmpfeminisms
10

marindacos
8

dhlib2012
8

thatcamprtp
7

goldstoneandrew
6

Top URLs in Tweet in Entire Graph
Entire Graph Count

<http://leo.hypotheses.org/9506>
26

<http://bit.ly/RyrPvA>
19

<http://tcp.hypotheses.org/609>
19

<http://tcp.hypotheses.org/programme>
15

<http://rtp2012.thatcamp.org/apply/>
12

<http://bit.ly/w1IFmR>
11

<http://dhlib2012.thatcamp.org/register/>
10

<http://goo.gl/qJ185>
10

<http://dhlib2012.thatcamp.org/>
8

<http://bit.ly/RNHLKO>
8

Top Hashtags in Tweet in Entire Graph
Entire Graph Count

thatcamp
137

mla13
27

dh
22

tcp2012
17

thatcampsocal
12

dhlib2012
9

unconferences
7

thatcamptheory
6

digitalhumanities
6

tcny2012
6
And now the visualization. You can [download the zoomable pdf here. ](http://electricarchaeologist.files.wordpress.com/2012/09/thatcamp-sept11-20122.pdf) As I look at the modularity in this graph, at first blush, you can see quite a North America / European divide, with various satellite outposts. This could be of course because there's a THATCamp Paris coming down the pipe (lots of French in the tweets).

## Comments

**[Shawn](#8086 "2012-10-19 12:56:29"):** Hi Rena, I'm glad your project is progressing, and that this visualization is helpful. Please do sign up for THATCamp. It costs nothing and might make a nice break from writing the application :)

**[renabivens](#8085 "2012-10-19 12:52:35"):** This is great and has sparked an idea for me while I'm still in the process of putting together this new research proposal I came to talk to you about. I'm thinking I can search for hashtags popular in the gender-based violence movement (#VAW instantly comes to mind as an example) and then get a quick visualization of some of the major players in the movement. Thanks Shawn! My project has developed enormously since I spoke with you last. I'm hoping to come to THATCamp although it is the weekend before this application is due so I haven't signed up yet just in case I am still just as crazy busy as I am now. Hope all is well!

