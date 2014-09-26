title: Converting 2 mode networks with Multimodal plugin for Gephi
link: http://electricarchaeology.ca/2012/04/04/converting-2-mode-with-multimodal-plugin-for-gephi/
author: fhg1711
description: 
post_id: 1426
created: 2012/04/04 13:21:20
created_gmt: 2012/04/04 18:21:20
comment_status: open
post_name: converting-2-mode-with-multimodal-plugin-for-gephi
status: publish
post_type: post

# Converting 2 mode networks with Multimodal plugin for Gephi

[Scott Weingart](https://twitter.com/#!/scott_bot) drew my attention this morning to a [new plugin for Gephi by Jaroslav Kuchar](https://gephi.org/plugins/multimode-networks-transformations/) that converts multimodal networks to one mode networks. 

> This plugin allows multimode networks projection. For example: you can project your bipartite (2-mode) graph to monopartite (one-mode) graph. The projection/transformation is based on the matrix multiplication approach and allows different types of transformations. Not only bipartite graphs. The limitation is matrix multiplication - large matrix multiplication takes time and memory.

After some playing around, and some emails & tweets with Scott, we determined that it does not seem to work at the moment for directed graphs. But if you've got a bimodal **undirected** graph, it works very well indeed! It does require some massaging though. I assume you can already download and install the plugin. 1\. Make sure your initial csv file with your data has a column called 'type'. Fill that column with 'undirected'. The plugin doesn't work correctly with directed graphs. 2\. Then, once your csv file is imported, create a new column on the nodes table, call it 'node-type' - here you specify what the thing is. Fill it up accordingly. (cheese, crackers, for instance). 3\. I thank Scott for talking me through this step. First, save your network; this next step will irrevocably change your data. Click 'load attributes'. Under attribute type, select your column you created for step 2. Then, for left matrix, select select Cheese - Crackers; for right matrix, select Crackers - Cheese. Hit 'run'. This gets you a new Cheese-Cheese network (select the inverse to get a crackers - crackers network).  You can then remove any isolates or dangly bits by ticking 'remove edges' or 'remove nodes' as appropriate. 4\. Save your new 1 mode network. Go back to the beginning to create the other 1 mode network.