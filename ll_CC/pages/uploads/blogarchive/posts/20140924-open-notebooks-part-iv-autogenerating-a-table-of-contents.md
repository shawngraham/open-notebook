title: Open Notebooks Part IV - autogenerating a table of contents
link: http://electricarchaeology.ca/2014/09/24/open-notebooks-part-iv-autogenerating-a-table-of-contents/
author: fhg1711
description: 
post_id: 2226
created: 2014/09/24 20:56:47
created_gmt: 2014/09/25 01:56:47
comment_status: open
post_name: open-notebooks-part-iv-autogenerating-a-table-of-contents
status: publish
post_type: post

# Open Notebooks Part IV - autogenerating a table of contents

I've got [MDWiki](http://dynalon.github.io/mdwiki/#!quickstart.md) installed as the [public face of my open notebook](http://shawngraham.github.io/open-notebook/ll_CC/#!index.md). Getting it installed was easy, but I made it hard, and so I'll have to collect my thoughts and remember exactly what I did... but, as I recall, it was this bit I found in the documentation that got me going: **First off, create a new (empty) repository on GitHub, then;**
    
    
    git clone https://github.com/exalted/mdwiki-seed.git
    cd mdwiki-seed
    git remote add foobar <HTTPS/SSH Clone URL of the New Repository>
    git push foobar gh-pages
    

## 

  Then, I just had to remember to edit the 'gh-pages' branch. Also, on github, if you click on 'settings', it'll give you the .io version of your page, which is the pretty bit. So, I updated robot 3 to push to the 'uploads/documents' folder. Hooray! But what I needed was a self-updating 'table of contents'. Here's how I did that. In the .[md file that describes a particular project](https://raw.githubusercontent.com/shawngraham/open-notebook/gh-pages/ll_CC/pages/aural.md) (which goes in the 'pages' folder) I have a heading 'Current Notes' and a link to a file, content.md, like so: ## [Current Notes](uploads/documents/contents.md) Now I just train a robot to always make an updated contents.md file that gets pushed by robot 3. I initially tried building this into robot 2 ('convert-rtf-to-md'), but I outfoxed myself too many times. So I inserted a new robot into my flow between 2 & 3\. Call it 2.5, 'Create-toc': ![Screen Shot 2014-09-24 at 9.40.16 PM](http://electricarchaeologist.files.wordpress.com/2014/09/screen-shot-2014-09-24-at-9-40-16-pm.png?w=300) It's just a shell script: [code language="bash"] cd ~/Documents/conversion-folder/Draft ls *.md &gt; nolinkcontents.md sed -E -n 's/(^.*[0-9].*$)/ \\* [\1](\1)/gpw contents.md' nolinkcontents.md rm nolinkcontents.md [/code] Or, in human: go to the conversion folder. List out all the newly-created md files and write that to a file called 'nolinkcontents.md'. Then, wrap markdown links around each line, and use each line as the text of the link, and call that 'contents.md'. Then remove the first file. Ladies and gentlemen, this has taken me the better part of four hours. Anyway, this 'contents.md' file gets pushed to github, and since my project description page always links to it, we're golden. Of course, I realize now that I'll have to modify things slightly, structurally and in my nomenclature, once I start pushing more than one project's notes to the notebook. But that's a task for another night. Now to lesson plan for tomorrow. (update: when I first posted this, I kept saying robot 4. Robot 4 is my take-out-the-trash robot, which cleans out the conversion folder, in readiness for the next time. I actually meant Robot 3. See [Part III](http://electricarchaeology.ca/2014/09/19/open-notebooks-part-iii/))