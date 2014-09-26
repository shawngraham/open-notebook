title: MAGIS: Mediterranean Archaeology GIS
link: http://electricarchaeology.ca/2007/09/18/magis-mediterranean-archaeology-gis/
author: fhg1711
description: 
post_id: 65
created: 2007/09/18 11:47:49
created_gmt: 2007/09/18 16:47:49
comment_status: open
post_name: magis-mediterranean-archaeology-gis
status: publish
post_type: post

# MAGIS: Mediterranean Archaeology GIS

It turns out that what I thought was so clever yesterday, was done some time ago by folks at DePauw: 

> [MAGIS](http://cgma.depauw.edu/MAGIS/), an inventory of regional survey projects in the greater Mediterranean region.![](http://cgma.depauw.edu/MAGIS/Images/cgmatitletile.gif)

As of today, they have 288 survey projects in their spatially-searchable database. The interface is a bit clunky though, and relies on popups, which my browser consistently shuts down, despite me telling it not too. Platial and my BiblioCartography also have the advantage of allowing others to embed the maps in their own applications. If I get around to it, I might incorporate the MAGIS inventory.

## Comments

**[Gabriel](#71 "2007-09-20 12:23:08"):** The interesting lesson that I would like to see learned from the experiences of your Platial implementation, MAGis, and the [Pleiades team](http://pleiades.stoa.org/), among others, is how low the first hurdle to participation can be brought. An archaeologist working outside of the classical academy who discovers a Roman site in the desert of Libya, for example, who will perhaps publish her work in an obscure, non-English language journal that never makes its way into the right library catalogues or onto the web, and wants to submit her site to your database. How does she go about it? What technical training is needed? What software is needed? What credentials need to be supplied before she has permission to access the tool? Of course, what is really useful is not so much a *single* repository of all this data (we're not empire-builders any more), but a protocol whereby data living in any of a thousand conforming repositories or individual websites can be aggregated via some mechanism like Atom or GeoRSS for whatever search it is you are interested in. Oder?

**[Shawn](#72 "2007-09-20 12:40:48"):** A very good point. Platial is still in beta-testing, and so it still has a few bugs to work out. That being said, once those are taken care of, it should be a simple matter of point-and-clicking on the right part of the map, and typing in the information. I don't think it could get any simpler than that. Right now, no credentials are necessary to use the tool, although I have ultimate 'approve' / 'disallow' privileges for anything that gets submitted. It seems too that other users can make changes to information put up, which suggests that the usual wiki - ecology will emerge over time. I've been using the Platial bulk-upload system too to import information from MAGIS. The bulk-upload is less complicated than your typical Arcview GIS set-up. There's one or two hiccups, which again are probably due to this being a beta-version - it takes a few tries for the software to recognise the information - but eventually it works. I expect that this process will get easier as well. You also mention Atom or GeoRSS - these too can be used to update the site. So, between the three kinds of data-aggregation (user point-and-click, bulk-upload from databases, and rss-feeds), it should be possible to put together quite a repository. Platial uses the Google Maps/Google Earth api, so perhaps what we're seeing is Google's protocols becoming the defacto means of representing spatially-annotated data. Whether ultimately that's a good thing or a bad thing I don't know.... but it's certainly far easier now to get good quality spatially-referenced data than when I first set foot in the field!

