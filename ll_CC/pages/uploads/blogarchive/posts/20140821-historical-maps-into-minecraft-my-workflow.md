title: Historical Maps into Minecraft: My Workflow
link: http://electricarchaeology.ca/2014/08/21/historical-maps-into-minecraft-my-workflow/
author: fhg1711
description: 
post_id: 2150
created: 2014/08/21 10:38:07
created_gmt: 2014/08/21 15:38:07
comment_status: open
post_name: historical-maps-into-minecraft-my-workflow
status: publish
post_type: post

# Historical Maps into Minecraft: My Workflow

The folks at the New York Public Library [have a workflow and python script for translating historical maps into Minecraft](https://github.com/NYPL/historical-minecraft). It's a three-step (quite big steps) process. First, they generate a DEM (digital elevation model) from the historical map, using [QGIS](http://www.qgis.org/en/site/). This is saved as 'elevation.tiff'. Then, using [Inkscape](http://www.inkscape.org/en/), they trace over the features from the historical map that they want to translate into Minecraft. Different colours equal different kinds of blocks. This is saved as 'features.tiff'. Then, using a [custom python script](https://github.com/NYPL/historical-minecraft/tree/master/fort-washington), the two layers are combined to create a minecraft map, which can either be in 'creative' mode or 'survival' mode. There are a number of unspoken steps in that workflow, including a number of dependencies for the python script that have to be installed first. Similarly, QGIS and its plugins also have a steep (sometimes hidden) learning curve. As does Inkscape. And Imagemagick. This isn't a criticism; it's just the way this kind of thing works. The problem, from my perspective, is that if I want to use this in the classroom, I have to guide 40 students with widely varying degrees of digital fluency.* I've found in the past that many of my students "didn't study history to have to work with computers" and that the payoff sometimes (to them) doesn't seem to have (immediate) value. The pros and cons of that kind of work shall be the post for another day. Right now, my immediate problem is, how can I smooth the gradient of the learning curve? I will do this by providing 3 separate paths for creating the digital elevation model. 

### Path 1, for when _real world_ geography is not the most important aspect.

It may be that the shape of the world described by the historical map is what is of interest, rather than the current topography of the world. For example, I could imagine a student wanting to explore the historical geography of the Chats Falls before they were flooded by the building of a hydro dam. Current topographic maps and DEMs are not useful. For this path, the student will need to use the process described by the NYPL folks: 

> ### Requirements
> 
> QGIS 2.2.0 ( [http://qgis.org](http://qgis.org/) ) 
> 
>   * Activate Contour plugin
>   * Activate GRASS plugin if not already activated
> A map image to work from 
>   * We used a geo-rectified TIFF exported from [this map](http://maps.nypl.org/warper/maps/16089#Rectify_tab) but any high rez scan of a map with elevation data and features will suffice.
> 
> ### Process:
> 
> Layer > Add Raster Layer > [select rectified tiff] 
> 
>   * Repeat for each tiff to be analyzed
> Layer > New > New Shapefile Layer 
>   * Type: Point
>   * New Attribute: add 'elevation' type whole number
>   * remove id
> Contour (plugin) 
>   * Vector Layer: choose points layer just created
>   * Data field: elevation
>   * Number: at least 20 (maybe.. number of distinct elevations + 2)
>   * Layer name: default is fine
> Export and import contours as vector layer: 
>   * right click save (e.g. port-washington-contours.shp)
>   * May report error like "Only 19 of 20 features written." Doesn't seem to matter much
> Layer > Add Vector Layer > [add .shp layer just exported] Edit Current Grass Region (to reduce rendering time) 
>   * clip to minimal lat longs
> Open Grass Tools 
>   * Modules List: Select "v.in.ogr.qgis"
>   * Select recently added contours layer
>   * Run, View output, and close
> Open Grass Tools 
>   * Modules List: Select "v.to.rast.attr"
>   * Name of input vector map: (layer just generated)
>   * Attribute field: elevation
>   * Run, View output, and close
> Open Grass Tools 
>   * Modules List: Select "r.surf.contour"
>   * Name of existing raster map containing colors: (layer just generated)
>   * Run (will take a while), View output, and close
> Hide points and contours (and anything else above bw elevation image) Project > Save as Image You may want to create a cropped version of the result to remove un-analyzed/messy edges

The hidden, tacit bits here involve installing the Countour plugin, and working with GRASS tools (especially the bit about 'editing the current grass region', which always is fiddly, I find). Students pursuing this path will need a lot of one-on-one. 

### Path 2, for when you already have a shapefile from a GIS:

This was cooked up for me by Joel Rivard, one of our GIS & Map specialists in the Library. He writes, 

> 1) In the menu, go to Layer > Add Vector Layer. Find the point shapefile that has the elevation information.
> 
> Ensure that you select point in the file type.
> 
> 2) In the menu, go to Raster > Interpolation. Select "Field 3" (this corresponds to the z or elevation field) for Interpolation attribute and click on "Add".
> 
> Feel free to keep the rest as default and save the output file as an Image (.asc, bmp, jpg or any other raster - probably best to use .asc since that's what MicroDEM likes.

We'll talk about MicroDEM in a moment. I haven't tested this path yet, myself. But it should work.

### Path 3 For when modern topography is fine for your purposes

In this situation, modern topography is just what you need. 1\. [Grab Shuttle Radar Topography Mission ](http://dwtkns.com/srtm/)data for the area you are interested in (it downloads as a tiff.) 2\. Install MicroDEM and all of its bits and pieces (the installer wants a whole bunch of other supporting bits; just say yes. MicroDEM is PC software, but I've run it on a Mac within [WineBottler](http://winebottler.kronenberg.org/)). 3\. This video tutorial covers working with MicroDEM and Worldpainter: <https://www.youtube.com/watch?v=Wha2m4_CPoo> But here's some screenshots - basically, you open up your .tiff or your .asc image file within MicroDEM, crop to the area you are interested in, and then convert the image to grayscale: [caption id="attachment_2151" align="alignleft" width="246"]![MicroDEM: open image, crop image.](http://electricarchaeologist.files.wordpress.com/2014/08/microdem.png?w=246) MicroDEM: open image, crop image.[/caption] [caption id="attachment_2152" align="alignleft" width="300"]![Convert to grayscale](http://electricarchaeologist.files.wordpress.com/2014/08/microdem2.png?w=300) Convert to grayscale[/caption] [caption id="attachment_2153" align="alignleft" width="300"]![Remove legends, marginalia](http://electricarchaeologist.files.wordpress.com/2014/08/microdem3.png?w=300) Remove legends, marginalia[/caption] Save your grayscaled image as a .tiff. Regardless of the path you took (and think about the historical implications of those paths) you now have a gray scale DEM image that you can use to generate your mindcraft world. 

### Converting your grayscale DEM to a Minecraft World

## Comments

**[CGSaw](#31305 "2014-08-22 07:58:15"):** Reblogged this on [Christopher P. Sawula](http://sawula.wordpress.com/2014/08/22/historical-maps-into-minecraft-my-workflow/) and commented: I've been following Shawn's work on this for the last couple of weeks on Twitter so I'm very excited he's posted his workflow. Will have to try it out down the line.

