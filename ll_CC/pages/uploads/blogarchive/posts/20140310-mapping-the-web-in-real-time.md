title: Mapping the Web in Real Time
link: http://electricarchaeology.ca/2014/03/10/mapping-the-web-in-real-time/
author: fhg1711
description: 
post_id: 1959
created: 2014/03/10 10:20:49
created_gmt: 2014/03/10 15:20:49
comment_status: open
post_name: mapping-the-web-in-real-time
status: publish
post_type: post

# Mapping the Web in Real Time

I don't think I've shared my workflow before for mapping the structure of a webcrawl. After listening to Sebastian Heath speak at [#dapw](https://twitter.com/search?q=%23dapw&src=hash) it occurred to me that it might be useful for, interalia linked open data type resources. So, here's what you do (and my example draw's from this year's SAA 2014 blogging archaeology session blog-o-sphere): 1\. install the [http graph generator from the gephi plugin marketplace.](https://gephi.org/2011/the-http-graph-plugin/) 2\. download the [navicrawler + firefox portable zip fil](http://webatlas.fr/wp/navicrawler/)e at the top of this page. 3\. make sure no other instance of firefox is open. Open firefox portable. DO NOT click the 'update firefox' button, as this will make navicrawler unusable. 4\. Navicrawler can be used to download or scrape the web. In the navicrawler window, click on the (+) to select the 'crawl' pane. This will let you set how deep and how far to crawl. Under the 'file' tab, you can save all of what you crawl in various file formats. With the httpgraph plugin for Gephi however, we will simply 'listen' to the browser and render the graph in real time. 5\. The first time you run firefox portable, you will need to configure a manual proxy. Do this by going to tools >> options >> network >> settings. Set the manual proxy configuration for http to 127.0.0.1 and the port to 8088. Click 'ok'. If you tried loading a webpage at this point, you'd get an error. To resolve this, you need to tell Gephi to connect to that port as well, and then web traffic will be routed correctly. 6\. Open Gephi. Select new project. Under 'generate', select 'http graph'. This will open a dialogue box asking for the port number. Enter 8088. 7\. Over in Firefox portable, you can now start a websearch or go to the page from which you wish to crawl. For instance, you could put in the address bar, <http://dougsarchaeology.wordpress.com/2013/11/05/blogging-archaeology/>. Over in gephi, you will start to see a number of nodes and edges appearing. In the 'crawl' window in Navicrawler, set 'max depth' to 1, 'crawl distance' to 2' and 'tabs count' to 25. Then hit the 'start' button. Your Gephi window will now begin to fill with the structure of the internet. There are 4 types of nodes: client, uri, host, and domain. For our purposes here, we will want to filter the resulting graph to hide most of the architecture of the web and just show the URIs. (This by the way could be very useful for visualizing archaeological resources organized via Linked Open Data principles). Your crawl can run for quite some time.  I was running the crawl describe above for around 10 minutes when it crashed on me. The resulting gephi file (which has 5374 nodes and 14993 edges) can be d[ownloaded from my space on figshare](http://figshare.com/articles/Blogging_Archaeology_Web_of_Links/956273). For the illustration below, I filtered the 'content-type' for 'text/html', to present the structure of the human readable archaeo-blog-o-sphere as represented by Doug's Blogging Archaeology Carnival. 

![The view from Doug's place](http://electricarchaeologist.files.wordpress.com/2014/03/dougs-archaeology.png?w=300)

    The view from Doug's place