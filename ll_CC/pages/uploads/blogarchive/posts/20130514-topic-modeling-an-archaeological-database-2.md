title: Topic Modeling an Archaeological Database 2
link: http://electricarchaeology.ca/2013/05/14/topic-modeling-an-archaeological-database-2/
author: fhg1711
description: 
post_id: 1765
created: 2013/05/14 13:27:37
created_gmt: 2013/05/14 18:27:37
comment_status: open
post_name: topic-modeling-an-archaeological-database-2
status: publish
post_type: post

# Topic Modeling an Archaeological Database 2

Some things I have learned in recent days: 

  * data must be cleaned. Really. It's probably still too noisy, even when you think it isn't. Eliminate frequently occuring meta-notes (as it were). All citations to Guest & Wells on Coins in the UK, for instance, really muck things up.
  * you can enter a single csv file as an input for MALLET. I knew this; but I had forgotten it, faced with a few hundred thousand rows of material (as I type this, the thought also occurs that I could run MALLET on the entire single file download I got from PAS, all ~500 000 rows. Presumably, locations and periods would sort themselves out into different topics?)
  * MALLET considers letter characters to make up words. If you've got other stuff in there - numerals, for instance - that are significant, you'll need to become familiar with - -token regex , which you'd use during that initial file-import. It was suggested to me to try these

> \-- token-regex \s\d+\s \--token-regex '[\p{L}\p{M}\p{N}]+'

What else? Oh, that's about all, for now. Oh, wait: custom stopwords. Instead of --remove-stopwords, you'll want --extra-stopwords yourlist.txt . And your list has to be formatted so that there is whitespace between the words. I'm not sure if that means 'white space' like how you and I would figure it, or if that means 'white space' in some kind of crazy hidden code kind of way (like this in regex: \s [(see this)](http://www.regular-expressions.info/charclass.html)). If you open one of the default stopword lists, there doesn't look like there's any hit-the-space-bar-kind-of white space that I'd normally assume. Onwards!