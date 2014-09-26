title: The Tiber Valley Brick Industry as Two Mode Network
link: http://electricarchaeology.ca/2012/06/25/the-tiber-valley-brick-industry-as-two-mode-network/
author: fhg1711
description: 
post_id: 1500
created: 2012/06/25 13:40:14
created_gmt: 2012/06/25 18:40:14
comment_status: open
post_name: the-tiber-valley-brick-industry-as-two-mode-network
status: publish
post_type: post

# The Tiber Valley Brick Industry as Two Mode Network

![](http://electricarchaeologist.files.wordpress.com/2012/06/signa_to_fig_pr.png?w=300)From the first to third centuries AD, the brick manufactories in the Tiber Valley around Rome made millions of bricks. A proportion of these carry makers' marks, with many different dimensions of information - the brick maker; the estate; the landowner; the year; and various decorative features which may or may not be signficant. I worked on this material for my PhD thesis (which these days makes me cringe when I look at it). I've been reconsidering that work lately, especially in light of recent work by Malkin, Knappet, Brughmans, and of course the interest in digital humanities in networks more generally. I discovered on an old and nearly defunct laptop a file I'd created as part of my PhD work, which listed the text of every stamp in the CIL XV.1, and gave the original neo-latin description of the figurative device on these stamps. (CIL is written in 19th century academic Latin). So, I decided to see what I could find if I translated this into a Gephi two-mode network, and ran some descriptive statistics on it - how I wish I'd had these tools a decade ago! As I wrote in 2002 there are 46 different types of signa, across 428 types of stamp, totalling about 3000 examples listed in CIL. The file I'm working here is a bit more messy, with many variants of the typical motifs. So, what do we have? It's a two mode network, which can be filtered into a single giant component of 570 nodes and 608 edges connecting it. For the brick afficonados amongst you, you can pick out the big name figlinae like Terentianae or Domitianae, and see how they interconnect based on shared useage of signa. If you calculate modularity on this network, you get 18 very strong sub-communities. That jives very nicely with the archaeometry I did on the brick, finding about 12 groups in a cluster analysis using Ward's Method on the XRD results from the South Etruria Survey collection of bricks. Next thing: split this graph up by time, space, clay sources, and usage patterns at sites. Here's the [pdf version with labels](http://electricarchaeologist.files.wordpress.com/2012/06/signa_to_fig_and_pr_w_labels.pdf). Keep in mind, this is rather rough.![](http://electricarchaeologist.files.wordpress.com/2012/06/cilxv-1_189.jpg)