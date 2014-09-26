title: Gaze & Eonydis for Archaeological Data
link: http://electricarchaeology.ca/2014/01/15/gaze-eonydis-for-archaeological-data/
author: fhg1711
description: 
post_id: 1939
created: 2014/01/15 11:55:57
created_gmt: 2014/01/15 16:55:57
comment_status: open
post_name: gaze-eonydis-for-archaeological-data
status: publish
post_type: post

# Gaze & Eonydis for Archaeological Data

I'm experimenting with [Clement Levallois](http://www.clementlevallois.net)' data mining tools '[Gaze](https://github.com/seinecle/Gaze/wiki/Gaze:-find-structure-in-your-networks)' and '[Eonydis](https://github.com/seinecle/Eonydis/wiki/wiki)'. I created a table with some mock archaeological data in it: artefact, findspot, and date range for the artefact. More on dates in a moment. Here's [the fake dataset](https://www.dropbox.com/s/nnbqwgj57fvbvel/archaeo-test.csv). Firstly, Gaze will take a list of nodes (source, target), and create a network where the source nodes are connected to each other by virtue of sharing a common target. Clement explains: 

> Paul,dog Paul, hamster Paul,cat Gerald,cat Gerald,dog Marie,horse Donald,squirrel Donald,cat ... In this case, it is interesting to get a network made of Paul, Gerald, Marie and Donald (sources nodes), showing how similar they are in terms of pets they own. Make sure you do this by choosing "directed networks" in the parameters of Gaze. A related option for directed networks: you can choose a minimum number of times Paul should appear as a source to be included in the computations (useful to filter out unfrequent, irrelevant nodes: because you want only owners with many pets to appear for instance).

The output is in a [nodes](https://www.dropbox.com/s/ed1oopxzt03j5xz/archaeo-test_nodes_list.dl).dl file and an [edges](https://www.dropbox.com/s/xlwtn0kj9p82s1u/archaeo-test_edges_list.dl).dl file. In Gephi, go to the import spreadsheet button on the data table, import the nodes file first, then the edges file. Here's the [graph file](https://www.dropbox.com/s/gwdf74fnftwgwug/archaeo-test.gexf). [caption id="attachment_1940" align="alignleft" width="300"]![Screenshot, Gaze output into Gephi, from mock archaeo-data](http://electricarchaeologist.files.wordpress.com/2014/01/screenshot-gaze-archaeotest.png?w=300) Screenshot, Gaze output into Gephi, from mock archaeo-data[/caption] Eonydis on the other hand takes that same list and if it has time-stamps within it (a column with dates), will create a dynamic network over time. My mock dataset above seems to cause Eonydis to crash - is it my negative numbers? How do you encode dates from the Bronze Age in the day/month/year system? Checking the documentation, I see that I didn't have proper field labels, so I needed to fix that. Trying again, it still crashed. I fiddled with the dates to remove the range (leaving a column to imply 'earliest known date for this sort of thing'), which gave me [this file](https://www.dropbox.com/s/1vq4vr5cjldj1sx/archaeo-test3.csv). Which still crashed. Now I have to go do some other stuff, so I'll leave this here and perhaps one of you can pick up where I've left off. The example file that comes with Eonydis works fine, so I guess when I return to this I'll carefully compare the two. Then the task will be to work out how to visualize dynamic networks in Gephi. [Clement has a very good tutorial on this](http://www.clementlevallois.net/gephi/tuto/gephi_tutorial_dynamics.pdf). Postscript: Ok, so I kept plugging away at it. I found if I put the dates yyyy-mm-dd, as in 1066-01-23 then Eonydis worked a treat. Here's the [mock data](https://www.dropbox.com/s/jrl0tftp75ppkye/archaeo-test4.csv) and here's the [gexf](https://www.dropbox.com/s/z437ggbdvnoz0uk/archaeo-test4_eonydis.gexf). And here's the dynamic animation! <http://screencast.com/t/Nlf06OSEkuA> Post post script: I took the mock data (archaeo-test4.csv) and concatenated a - in front of the dates, thus -1023-01-01 to represent dates BC. In Eonydis, where it asks for the date format, I tried this: #yyyy#mm#dd  which accepted the dates, but dropped the negative; -yyyy#mm#dd, which accepted the dates and also dropped the negative. Thus, it seems to me that I can still use Eonydis for archaeological data, but I should frame my date column in relative terms rather than absolute, as absolute isn't really necessary for the network analysis/visualization anyway.

## Comments

**[beetles for sale insects](#18680 "2014-02-27 22:26:22"):** I know this website presents quality dependent posts and additional stuff, is there any other web site which offers such information in quality?

