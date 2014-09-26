title: Getting started with some open source alternatives to 123D Catch
link: http://electricarchaeology.ca/2014/01/28/getting-started-with-some-open-source-alternatives-to-123d-catch/
author: fhg1711
description: 
post_id: 1947
created: 2014/01/28 12:31:08
created_gmt: 2014/01/28 17:31:08
comment_status: open
post_name: getting-started-with-some-open-source-alternatives-to-123d-catch
status: publish
post_type: post

# Getting started with some open source alternatives to 123D Catch

I like 123D Catch, but there is the whiff of 'black-box' about it all. Sometimes, you'd just like to know what's going on. There may also be times when, for various reasons, uploading data to a cloud service hosted in another country is just not the right solution for you. There are many open source products though; right now I'm playing with [VisualSFM](http://ccwu.me/vsfm/). Download and install it; then [download CMVS](http://francemapping.free.fr/Portfolio/Prog3D/CMVS.html). Extract the zip. Within it you will find folders for various operating systems. Find yours, and copy the files within, to the VisualSFM folder. Now you're ready to go, as per the image below. Here's[ a longer tutorial too](http://www.iafsm.org/resources/Opensourcetoolspart3.pdf). ![](http://ccwu.me/vsfm/toolbar_new.jpg) You might however find it easier to use this[ bundle of all the bits and pieces ](http://opensourcephotogrammetry.blogspot.ca/2010/12/new-package-available-for-windows.html)you need, if you are familiar with python. Extract the zip, grab the folder that corresponds to your operating system, and move it to C:\ . Install [python ](http://python.org/)(I'm using Python 2.7). Then, open the command prompt (type 'cmd' in the 'run' box, Windows), navigate to the folder (On my machine, it's now in c:\bundler, so I had to type: C:\users\Shawn Graham> cd .. C:\users> cd .. C:\> cd bundler C:\Bundler>RunBundler.py --photos=C:\MyPhotoFolder\ ...and the magic begins to happen. I got an error at first: 'blah blah blah PIL missing blah blah'. PIL stands for Python Image LIbrary. Go [here, grab the correct version, ](http://www.pythonware.com/products/pil/)download it, and double-click to install. Then try again with the RunBundler.py command above. So that's running now on my machine; I'll update here if it all goes wrong - or if indeed it all goes right!