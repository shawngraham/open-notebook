title: Networked Corpus Index
link: http://electricarchaeology.ca/2014/01/08/networked-corpus-index/
author: fhg1711
description: 
post_id: 1935
created: 2014/01/08 13:53:21
created_gmt: 2014/01/08 18:53:21
comment_status: open
post_name: networked-corpus-index
status: publish
post_type: post

# Networked Corpus Index

I found this today: [http://www.networkedcorpus.com  ](http://www.networkedcorpus.com)for visualizing the results of MALLET topic models, by reference to exemplary passages. Its creators explicitly contrast this with index building by hand... more about all that later; here's how to get it working for you. See the documentation at <https://github.com/jeffbinder/networkedcorpus> Install python 2.7, numpy, and scipy. Download the installers, and follow the instructions. Then download the networked corpus zip file, and unzip it somewhere on your machine. In the networked-corpus folder, there is a subfolder called 'res' and a script called gen-networked-corpus.py. Move these two items to your Mallet folder. Generate a topic model as you would normally do, from the command line. Then, type at the command prompt: `gen-networked-corpus.py --input-dir <the folder with your original texts in it> \--output-dir <the name of a folder you'd like all the output to be in>` Navigate to that folder in your browser, open the index.html and voila.