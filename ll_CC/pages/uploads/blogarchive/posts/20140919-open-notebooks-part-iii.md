title: Open notebooks part III
link: http://electricarchaeology.ca/2014/09/19/open-notebooks-part-iii/
author: fhg1711
description: 
post_id: 2217
created: 2014/09/19 18:06:18
created_gmt: 2014/09/19 23:06:18
comment_status: open
post_name: open-notebooks-part-iii
status: publish
post_type: post

# Open notebooks part III

[caption id="attachment_2224" align="alignleft" width="68"]![Do my bidding my robots!](http://electricarchaeologist.files.wordpress.com/2014/09/screen-shot-2014-09-19-at-7-06-30-pm.png?w=68) Do my bidding my robots![/caption]I've sussed the Scrivener syncing issue by moving the process of converting out of the syncing folder (remember, not the actual project folder, but the 'sync to external folder'). I then have created four automator applications to push my stuff to github in lovely markdown. Another thing I've learned today: when writing in Scrivener, just keep your formatting simple. Don't use markdown syntax _within Scrivener_ or your stuff on github will end up looking like this \\##second-heading. I mean, it's still legible, but not as legible as we'd like. So - I have four robots. I write in Scrivener, keep my notes, close the session, whereupon it syncs rtf to the 'external folder' (in this case, my dropbox folder for this purpose; again, not the actual scrivener project folder). 

  1. I hit robot 1 on my desktop. Right now, this is called 'abm-project-move-to-conversion-folder'. When I have a new project, I just open this application in Automator, and change the source directory to that project's Scrivener external syncing folder. It grabs everything out of that folder, and copies it into a 'conversion-folder' that lives on my machine.
  2. I hit robot 2, 'convert-rtf-to-md', which opens 'conversion-folder' and turns everything it finds into markdown. The conversion scripts live in the 'conversion-folder'; the things to be converted live in a subfolder, conversion-folder/draft 
  3. I hit robot 3, 'push-converted-files-to-github-repo'. This grabs just the markdown files, and copies them into my local github repository for the project. When I have a new project, I'd have to change this application to point to the new folder. This also overwrites anything with the same file name.
  4. I hit robot 4, 'clean-conversion-folder' which moves everything (rtfs, mds,) to the trash. This is necessary because if not, then I can end up with duplicates of files I haven't actually modified getting through my pipeline onto my github page. (If you look at some of my experiments on github, you'll see the same card a number of times with 1...2...3...4 versions).
Maybe it's possible to create a meta-automator that strings those four robots into 1. I'll try that someday. [pause] Ok, so of course, I tried stringing them just now. And it didn't work. So I put that automator into the trash - [pause] and now my original four robots give me errors, 'the application .... can't be opened. -1712'. I found t[he solution here](http://www.likelyanswers.com/29305201/-1712-Error-While-Opening-Automator-Apps) (basically, go to spotlight, type in activity, then locate the application on the list and quit it). Here are my automators: [caption id="attachment_2218" align="aligncenter" width="300"]![Robot 1](http://electricarchaeologist.files.wordpress.com/2014/09/screen-shot-2014-09-19-at-6-57-17-pm.png?w=300) Robot 1[/caption] [caption id="attachment_2219" align="aligncenter" width="300"]![Robot 2](http://electricarchaeologist.files.wordpress.com/2014/09/screen-shot-2014-09-19-at-6-58-18-pm.png?w=300) Robot 2[/caption] [caption id="attachment_2220" align="aligncenter" width="300" class=" "]![Robot 3](http://electricarchaeologist.files.wordpress.com/2014/09/screen-shot-2014-09-19-at-6-58-42-pm.png?w=300) Robot 3[/caption] [caption id="attachment_2221" align="aligncenter" width="300" class=" "]![Robot 4](http://electricarchaeologist.files.wordpress.com/2014/09/screen-shot-2014-09-19-at-6-59-06-pm.png?w=300) Robot 4[/caption] Automator.... I think I love you.

## Comments

**[Nowhere Man](#31318 "2014-09-20 18:34:27"):** Yes, this is a great way to get it working. I just used MD format for Android but when my docs were converted back into Scrivener they were without any MD tags. Seemed more intuitive to me. Also, if you don't like the formatting when the MDs are converted back to RTF you can actually go into the shell files and mess with how it's presented. This line in md2rtf is how this is set up: echo "p { text-indent: 0em; margin-bottom: 0.5em; }" > $TEMPNAME It's basically a CSS command to not indent paragraphs and to space out each para. Neat, huh?

