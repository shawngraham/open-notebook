title: Looted Heritage: Infotrapping the Illicit Antiquities Trade
link: http://electricarchaeology.ca/2012/02/23/looted-heritage-infotrapping-the-illicit-antiquities-trade/
author: fhg1711
description: 
post_id: 1382
created: 2012/02/23 12:56:45
created_gmt: 2012/02/23 17:56:45
comment_status: open
post_name: looted-heritage-infotrapping-the-illicit-antiquities-trade
status: publish
post_type: post

# Looted Heritage: Infotrapping the Illicit Antiquities Trade

To crowdsource something - whether it is a problem of code, or the need to transcribe historical documents - is generally about fracturing a problem into its component pieces, and allowing an interested public to solve the tiny pieces. In 2011 I and my students embarked on a project to crowdsource sense of place, using [Ushahidi ](http://ushahidi.com)to solicit and collect community memories about cultural heritage resources in Pontiac and Renfrew counties in Eastern Canada ([The HeritageCrowd Project](http://heritagecrowd.org)). As part of that project, I had initially set up a deployment of Ushahidi using their hosted service, called 'C[rowdmap](https://crowdmap.com/mhi)'. It contains all of the functionality of the vanilla Ushahidi, but since they are doing the hosting, it cannot be customized to any great deal. I mothballed that initial deployment, and installed my own on my own server so I could customize. The entire experience was recounted in a contribution to the forthcoming born-digital volume, '[Writing History in the Digital Age](http://writinghistory.trincoll.edu/crowdsourcing/heritagecrowd-project-graham-massie-feuerherm/)', edited by Jack Dougherty and Kristen Nawrotzki. One of the findings of that small experiment was about the order of operations in a crowdsourced project: 

> ...in one sense our project’s focus was misplaced. Crowdsourcing should not be a first step. The resources are already out there; why not trawl, crawl, spider, and collect what has already been uploaded to the internet? Once the knowledge is collected, then one could call on the crowd to fill in the gaps. This would perhaps be a better use of time, money, and resources.

This January, I started the second term of my year long first year seminar in digital antiquity, and I decided to re-start my mothballed Crowdmap as part of a module on crowdsourcing. But as I prepared, that one paragraph above kept haunting me. Perhaps what was needed was not so much a module on crowdsourcing, but rather, one on information trapping. I realized that Ushahidi and Crowdmap are better thought of as info-traps. Thus, '[Looted Heritage: Monitoring the Illicit Antiquities Trade](http://heritage.crowdmap.com)' was born. The site monitors various social media and regular media feeds for stories and reports about the trade in antiquities, which can then be mapped, giving a visual depiction of the impact of the trade. I intend to use Zotero public library feeds as well, to enable the mapping of academic bibliography on the trade. Why illicit antiquities? The [Illicit Antiquities Research Centre at Cambridge University](http://www.mcdonald.cam.ac.uk/projects/iarc/home.htm) (which is, sadly, closed) provides some statistics on the nature and scale of the illicit antiquities trade; these statistics date to 1999; the problem has only grown with the wars and disruptions of the past decade: 

  * _Italy: _120,000 antiquities seized by police in five years;
  * _Italy: _100,000+ Apulian tombs devastated;
  * _Niger: _in southwest Niger between 50 and 90 per cent of sites have been destroyed by looters;
  * _Turkey:_ more than 560 looters arrested in one year with 10,000 objects in their possession;
  * _Cyprus: _60,000 objects looted since 1974;
  * _China: _catalogues of Sotheby’s sales found in the poor countryside: at least 15,000 sites vandalized, 110,000 illicit cultural objects intercepted in four years;
  * _Cambodia: _300 armed bandits surround Angkor Conservation compound, using hand grenades to blow apart the monuments; 93 Buddha heads intercepted in June this year, 342 other objects a month later;
  * _Syria:_ the situation is now so bad a new law has been passed which sends looters to jail for 15 years;
  * _Belize: _73 per cent of major sites looted;
  * _Guatemala: _thieves now so aggressive they even looted from the laboratory at Tikal;
  * _Peru: _100,000 tombs looted, half the known sites.
-Brodie and Watson, <http://www.mcdonald.cam.ac.uk/projects/iarc/culturewithoutcontext/issue5/brodie-watson.htm> The idea then is to provide my students with hands-on experience using Crowdmap as a tool, and to foster engagement with the real-world consequences of pot-hunting and tomb-robbing. Crowdmap also allows users to download all of the reports that get created. One may download all reports on Looted Heritage in CSV format at the [download page](https://heritage.crowdmap.com/reports_download). I will be using this data as part of my teaching about data mining and text analysis, getting the students to run this data through tools like [Voyant](http://voyant-tools.org/) to spot patterns in the way that the antiquities trade is portrayed in the media. At one point, I also had feeds from eBay for various kinds of artefacts, Greco-Roman, Egyptian, pre-Columbian, etc, but there is so much volume going through eBay that it completely overwhelmed the other signals. I think dealing with eBay and exploring the scope of the trade there will require different scrapers and quantitative tools, so I'm leaving that problem aside for the time being. I'm also waiting anxiously for [trap.it](http://trap.it/), which was described earlier this week in [Profhacker](http://chronicle.com/blogs/profhacker/set-traps-for-online-information-with-trapit/38649), to allow exports of the information it finds. Right now, you can only consume what it finds within its ecosystem (or through kludgy workarounds). Ideally, I would be able to grab a feed from Trap.it for one of its traps and bring that directly into Looted Heritage. Trap.it is more of an active agent than the passive sieve approach that Crowdmap takes, so combining the two ought to be a powerful approach. From Profhacker: 

> [Trap.it is] a web service that combines machine learning algorithms with user-selected topics and filters. (The algorithms used in this project stem from the same research that led to Apple’s Siri.) After creating an account, you create a “trap” by entering in a keyword or short phrase into the Discovery box. Once you save your trap, you personalize it by clicking thumbs up or thumbs down on a number of articles in your trap. The more articles you rate, the closer attuned the trap becomes to the kinds of material you want to read.

Finally, one of the other aspects we learned in the HeritageCrowd project was the importance of outreach. For Looted Heritage, I am using a combination of [If This Then That](http://ifttt.com/) to monitor Looted Heritage's feed, sending new reports to[ Buffer App](http://bufferapp.com/dashboard), which then sends to Twitter, @[looted_heritage](https://twitter.com/#!/looted_heritage). Aside from some problems with duplicated tweets, I've been quite happy with this setup (and thanks to [Terry Brock](https://twitter.com/#!/@brockter) for suggesting this). There's an interesting possibility of circularity there, with Crowdmap picking up @looted_heritage in its traps, and then sending them out again... but my students should spot that if it occurs. [Ushahidi also provides an IOS app](http://blog.ushahidi.com/index.php/2011/07/09/ushahidi-ios-white-label/) that can be deployed in the field, so that an archaeologist who discovers the work of tombaroli could take geo-tagged photographs and submit them with a click to the Looted Heritage installation, drawing police attention.

## Comments

**[Donna](#5979 "2012-02-24 22:59:09"):** This is amazingly cool! I'm going to follow this closely for sure!

**[Terry Brock](#6007 "2012-02-27 10:18:57"):** Considering the recent barrage of tv shows that celebrate looting (spike tv and National Geographic Channel being our latest), this project couldn't come at a better time.

**[Shawn](#6008 "2012-02-27 10:57:48"):** It would seem astonishing that something like National Geographic would air a show like that - but, actually, when you consider some of the things they've aired (see this blog for reviews of 'Expedition Week' programmes), it sadly isn't.

