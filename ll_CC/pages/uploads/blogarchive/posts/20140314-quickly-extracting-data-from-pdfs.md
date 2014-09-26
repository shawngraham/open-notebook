title: Quickly Extracting Data from PDFs
link: http://electricarchaeology.ca/2014/03/14/quickly-extracting-data-from-pdfs/
author: fhg1711
description: 
post_id: 1981
created: 2014/03/14 09:19:34
created_gmt: 2014/03/14 14:19:34
comment_status: open
post_name: quickly-extracting-data-from-pdfs
status: publish
post_type: post

# Quickly Extracting Data from PDFs

By 'data', I mean the tables. There are lots of archaeological articles out there that you'd love to compile together to do some sort of meta-study. Or perhaps you've gotten your hands on pdfs with tables and tables of census data. Wouldn't it be great if you could just grab that data cleanly? [Jonathan Stray](https://source.opennews.org/en-US/learning/you-got-documents-now-what/) has written a great synopsis of the various things you might try and has sketched out a workflow you might use. Having read that, I wanted to try '[Tabula](http://tabula.nerdpower.org/)', one of the options that he mentioned. Tabula is open source and runs on all the major platforms. You simply download it an double-click on the icon; it runs within your browser. You load your pdf into it, and then draw bounding boxes around the tables that you want to grab. Tabula will then extract that table cleanly, allowing you to download it as a csv or tab separated file, or paste it directly into something else. For instance, say you're interested in the data that Gill and Chippindale compiled on Cycladic Figures. You can grab the pdf from JSTOR: 

> Material and Intellectual Consequences of Esteem for Cycladic Figures
> 
> David W. J. Gill and Christopher Chippindale
> 
> American Journal of Archaeology , Vol. 97, No. 4 (Oct., 1993) , pp. 601-659
> 
> Published by: [Archaeological Institute of America](http://www.jstor.org/action/showPublisher?publisherCode=aia)
> 
> Article DOI: 10.2307/506716
> 
> Article Stable URL: <http://www.jstor.org/stable/506716>

Download it, and then feed it into Tabula. Let's look at table 2. 

![gillchippendaletable2](http://electricarchaeologist.files.wordpress.com/2014/03/gillchippendaletable2.png?w=300)

You could just highlight this table in your pdf reader and hit ctrl+c to copy it; when you paste that into your browser, you'd get:

![gillchippendaletable2cutnpaste](http://electricarchaeologist.files.wordpress.com/2014/03/gillchippendaletable2cutnpaste.png?w=300)

Everything in a single column. For a small table, maybe that's not such a big deal. But let's look at what you get with Tabula. You drag the square over that same table; when you release the mouse button you get:

![tabula1](http://electricarchaeologist.files.wordpress.com/2014/03/tabula1.png?w=300)

_Much, much cleaner & faster!_ I say 'faster', because you can quickly drag the selection box around every table and hit download just the one time. Open the resulting csv file, and you have all of your tables in a useful format:

![tabula2](http://electricarchaeologist.files.wordpress.com/2014/03/tabula2.png?w=300)

But wait, there's more! Since you can copy directly to the clipboard, you can paste directly into a google drive spreadsheet (thus taking advantage of all the visualization options that Google offers) or into something like [Raw from Density Design](http://app.raw.densitydesign.org).

Tabula is a nifty little tool that you'll probably want to keep handy.

## Comments

**[Mx Macaronic](#23132 "2014-03-15 17:09:05"):** Oooh, very nice! I could've used this when I was working on my dissertation. Definitely gonna keep it in mind for the future.

