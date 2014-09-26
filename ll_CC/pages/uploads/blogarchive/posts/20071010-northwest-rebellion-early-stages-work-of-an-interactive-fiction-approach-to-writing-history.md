title: Northwest Rebellion - early stages work of an Interactive Fiction approach to writing history
link: http://electricarchaeology.ca/2007/10/10/northwest-rebellion-early-stages-work-of-an-interactive-fiction-approach-to-writing-history/
author: fhg1711
description: 
post_id: 77
created: 2007/10/10 10:14:44
created_gmt: 2007/10/10 15:14:44
comment_status: open
post_name: northwest-rebellion-early-stages-work-of-an-interactive-fiction-approach-to-writing-history
status: publish
post_type: post

# Northwest Rebellion - early stages work of an Interactive Fiction approach to writing history

![Charles Boulton](http://upload.wikimedia.org/wikipedia/en/6/63/CharlesBoulton.jpg)One of the neat things about the [Great Canadian Mysteries](http://www.canadianmysteries.ca/indexen.html) series is how 'doing history' is constructed as 'solving' a mystery, by examining the primary historical documents. In the [interactive fiction](http://en.wikipedia.org/wiki/Interactive_fiction) (IF) below - which is only an early *early* draft - I am trying to accomplish the same thing. Here, the 'game' will be to explore and construct and interpretation of the Northwest Rebellion, by interacting with the historical characters who were there... and who speak to you in their own words. Just about anything [Major Charles Boulton](http://en.wikipedia.org/wiki/Charles_Arkoll_Boulton) says come from [his own published historical reminisces](http://wsb.datapro.net/rebellions/chap1.html). Now, an interactive fiction requires plot, pacing, a story arc, etc... or can it simply be as simple as 'talking' with a simulated person...? Right now, this IF just shows how such a writing of history could be accomplished. I need to program the non-player character of Major Boulton with a bit of artificial intelligence so that he can respond to a wide variety of interactions with the player. My model is [Emily Short's _Galatea_](http://emshort.wordpress.com/my-work/), which won the 2006 IF prize. I don't want this work to be a simple kind of [chatterbot.](http://en.wikipedia.org/wiki/Chatterbot) So, here's an early version of the [Major Charles Boulton and the Northwest Rebellion Interactive Historical Fiction](http://www.simulatinghistory.com/IF-archive/northwest.html), by Shawn Graham.

## Comments

**[Jason Dyer](#97 "2007-10-11 17:11:10"):** I realize this is an early early build, but judging from the reponse to "ask charles about bayonette" you might want to break things up a little -- that's a lot of text for a single question. I could imagine enjoying a conversation where I have to explore different topics a bit before he says anything about Upper Canada College. The sense of discovery in conversation (in this sort of game) needs to be the same as the sense of discovery in exploring an environment.

**[Shawn](#99 "2007-10-12 09:01:58"):** You're quite right - it is an awful lot of text. I'm still getting to grips with Inform for writing this kind of work. I've been following/adapting the code examples that come with Inform, and so just cut'n'pasted in some of Major Boulton's writings. I take your point on the sense of discovery - that's exactly what I need to be building into this. Ideally, I would love for the conversation to flow much more naturally. I wonder if it is possible to remove the actor that the player 'tells' to do things: instead of the player typing, 'Ask charles about the bayonette', they might directly address Charles: 'So charles, that's a real bayonette?'. Maybe that's possible, maybe not.

**[Jason Dyer](#100 "2007-10-12 18:46:03"):** Well, you might try the TOPICS system used in Emily Short's _[City of Secrets_](http://www.wurb.com/if/game/2106). It's a hybrid of topic choosing and a menu -- so you might start by typing BAYONETTE and then get a list of questions that you might ask about the bayonette. This can also account the type who already knows it's a real bayonette and is more curious about the manufacturer.

**[Shawn](#103 "2007-10-16 09:34:51"):** I'll try that. I had been trying the 'Conversation Rules' by Eric Eve, but I was having difficulty getting the sample, 'The Tribune's Report', but I kept getting the error, "Problem. The table Table Types was said to be a continuation, but it contains columns not found in the original". And of course, as far as I can see, the 'original' table is no-where to be found (perhaps it is in the extension itself). Anyway, thanks for the suggestion. Hopefully I'll have a better version up and running later this week.

**[Jason Dyer](#188 "2007-11-16 08:37:50"):** How is this (and the other project) going? (Using the 'pestering fosters productivity' philosophy.)

**[Shawn](#189 "2007-11-16 11:54:54"):** Well, life intervenes... I'm still working on it, albeit very slowly. I really got excited the other day though when I read the piece in Wired on the escape from the Tower of London game... one thing that occurred to me was, 'you could use this system to play a text adventure game - in real space!' which is not all that profound as that is in truth what the Tower game is. So, rushing off madly in all directions, I'm trying to see if I can get my hands on the right kind of hand-held computer... What I really need is a block of time, and the funds, to pursue all this properly... ;)

