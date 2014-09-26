title: GIS & ABM in Netlogo
link: http://electricarchaeology.ca/2008/06/02/gis-abm-in-netlogo/
author: fhg1711
description: 
post_id: 284
created: 2008/06/02 11:08:20
created_gmt: 2008/06/02 16:08:20
comment_status: open
post_name: gis-abm-in-netlogo
status: publish
post_type: post

# GIS & ABM in Netlogo

Came across a [post ](http://gisagents.blogspot.com/2008/04/gis-extension-for-netlogo.html)today on the '[GIS and Agent-Based Modelling](http://gisagents.blogspot.com/)' blog (from the good people at CASA at UCL in the UK) that should encourage more archaeologists to get into agent modelling. Archaeologists are very familiar with GIS, and to a much lesser degree, agent based modelling.  Getting the two to work together - importing GIS data into an agent-modelling environment - has usually been difficult. Apparently, there is now a plugin for Netlogo to import esri shapefiles into the [Netlogo ](http://ccl.northwestern.edu/netlogo/)environment: 

> "Whilst browsing the [OpenABM website](http://www.openabm.org/site/) I came across a [post by Eric Russell](http://www.openabm.org/site/node/45) about a beta version GIS Extension for NetLogo and could not resist trying it out. The extension provides primitives for importing vector GIS data (in the form of ESRI shapefiles) and raster GIS data (in the form of ESRI ascii grid files) into NetLogo. 
> 
> The extension and instillation instructions can be downloaded from: <http://ccl.northwestern.edu/netlogo/4.0/extensions/gis/>
> 
> There are two example models, one which loads a raster file of surface elevation for a small area near Cincinnati, Ohio (above). To quote from the documentation “It uses a combination of the gis:convolve primitive and simple NetLogo code to compute the slope (vertical angle) and aspect (horizontal angle) of the earth surface using the surface elevation data. Then it simulates raindrops flowing downhill over that surface by having turtles constantly reorient themselves in the direction of the aspect while moving forward at a constant rate”.

This should make it easier for archaeologists with an interest in how humans interact with the landscape to get their GIS (for managing landscape data) & ABM's (for modelling how we think humans work) to work together! I'm going to, when I have a moment, install this plugin and see what it can do.