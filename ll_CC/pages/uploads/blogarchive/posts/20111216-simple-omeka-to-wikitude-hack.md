title: Simple Omeka to Wikitude Hack
link: http://electricarchaeology.ca/2011/12/16/simple-omeka-to-wikitude-hack/
author: fhg1711
description: 
post_id: 1320
created: 2011/12/16 21:04:09
created_gmt: 2011/12/17 02:04:09
comment_status: open
post_name: simple-omeka-to-wikitude-hack
status: publish
post_type: post

# Simple Omeka to Wikitude Hack

I'm working on some projects at the moment, aiming to make augmented reality and cultural heritage discovery easier and gentler for the small scale historical society, student groups, etc: folks with a basic level of web literacy, but no real great level of programming skills. To that end, here's something one can do with [Omeka](http://omeka.org), to push items from its database into the [Wikitude ](http://wikitude.me)augmented reality platform. 

  1. In Omeka, have the [Geolocation ](http://omeka.org/codex/Plugins/Geolocation)plugin installed and working.
  2. Navigate to `[http://[your omeka site.com]/geolocation/map.kml](http://example.com/geolocation/map/browse)`
  3. You should see the xml structure of your geolocated items.
  4. In a new tab, go to [wikitude.me](http://wikitude.me), and sign up for a developer account (it's free).
  5. Click 'add new world'.
  6. Click 'upload KML file'.
  7. Fill in all required fields (you'll have to create a 32 by 32 pixel icon to serve as a dot-on-the-map, and upload that too).
  8. Under 'KML/KMZ' file, click on 'Enter KML URL'. This will give you a box into which you may paste the URL from #2.
  9. Hit save.
If you're successful, the next screen will tell you how many points have been uploaded. If, at some later point you've added many more items to Omeka, you'll have to go back to your World in Wikitude and hit save again, to upload the most recent stuff. Now, with Wikitude on your phone, you might not be able to find your world right away. There's a solution. If you log back into the Wikitude developer zone, and click on the world you just created, you'll find a string of letters under 'developer key'. On your Iphone, go to 'settings' , select 'Wikitude'. Under 'Developer Settings', there's a box for the developer key. Enter that developer key there. Start Wikitude up, refresh the display, and your items from Omeka will be under 'Around Me'. ...And there you have it. Right now, this just does the basic text descriptions, and the location. By fiddling with the Geolocation plugin code, one might be able to add the other information that Wikitude can display, like images, video, audio, etc. For a similar approach, but directly from Google Maps, see this video by [drmonkeyjcg](http://www.youtube.com/user/drmonkeyjcg): http://www.youtube.com/watch?v=Ot5HKJvIST4