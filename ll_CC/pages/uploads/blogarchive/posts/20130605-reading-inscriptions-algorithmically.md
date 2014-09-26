title: Reading Inscriptions Algorithmically
link: http://electricarchaeology.ca/2013/06/05/reading-inscriptions-algorithmically/
author: fhg1711
description: 
post_id: 1793
created: 2013/06/05 12:31:14
created_gmt: 2013/06/05 17:31:14
comment_status: open
post_name: reading-inscriptions-algorithmically
status: publish
post_type: post

# Reading Inscriptions Algorithmically

Inscriptions are complicated beasts. Frequently quite small and incomplete, epigraphers are able to extract an enormous amount of information from inscriptions - especially when they have other inscriptions with which to contrast and compare. Let us look at the [inscriptions from Aphrodisias](http://insaph.kcl.ac.uk/index.html), which are published online following [Epidoc](http://insaph.kcl.ac.uk/iaph2007/xml/tei-epidoc.dtd) conventions. Because of this, we are able to do some data-mining on them with a minimum of pre-processing. (**Joyce Reynolds**, **Charlotte Roueché**, **Gabriel Bodard**, _Inscriptions of Aphrodisias_ (2007), available <<http://insaph.kcl.ac.uk/iaph2007>>, ISBN 978-1-897747-19-3.) The first one looks like this, when the xml tags are stripped away: 

> Reynolds1982 Creative Commons licence Attribution 2.5 (http://creativecommons.org/licenses/by/2.5/) All reuse or distribution of this work must contain somewhere a link back to the URL http://insaph.kcl.ac.uk/ Originally published in Reynolds (1982). English French German Ancient Greek Transliterated Greek Modern Greek Italian Latin Spanish Turkish 2007-07-04cmrDONE2007-04-02Charlotte Tupmanhand tidiedGBhand tidied 2007-03-15Elliott HallBatch converted Word2XML 
> 
> Description of MonumentUpper right corner of a white marble block (0.36 x 0.24 x 0.34).
> 
> Description of TextInscribed on one face.
> 
> LettersLate Republican or Augustan; ave 0.02. rho in ll. 1, 3, 6 has a very small stroke slanting rightwards from the junction of the bowl with the vertical.
> 
> Date Late Republican or Augustan (lettering, content)
> 
> Edition οὗτος ὁ τόπος ἱερὸς ἄσυλος ὡς ἔκριναν ὁ μέγας Καῖσαρ ὁ δικτάτωρ καὶ ὁ υἱὸς αὐτοῦ αὐτοκράτωρ Καῖσαρ καὶ ἡ σύνκλητος καὶ ὁ δῆμος ὁ Ῥωμαίων καθὼς καὶ τὰ φιλάνθρωπα καὶ δελτογραφήματα καὶ ἐπικρίματα περιέχει ἀνέστησεν δὲ τοὺς ὅρους Γάϊος Ἰούλιος Ζωΐλος ὁ ἱερεὺς τῆς Ἀφροδείτης
> 
> Apparatus For the supplements, compare the partner inscription 1.38.
> 
> Translation [?This area is] the sacred asylum [?as defined by] the great [?Caesar, the] Dictator, and [?his son] Imperator [Caesar and the ] Senate [and People] of Rome, [as is also contained in the] grants of privilege, the public documents [and decrees. C. Iulius Zoilos priest of Aphrodite set up the boundary stones.]
> 
> Commentary See , 159-160.
> 
> Locations Stray find. Temple/Church temenos. Museum (1977)
> 
> Text Constituted From Transcription (Reynolds)
> 
> History of Recording Recorded by the NYU expedition in 1963 (63.596)
> 
> Bibliography Published by Reynolds, , doc. 35, whence SEG 1982.1097, BE 1983.388, 1984.878, McCabe 379, R. R. R. Smith, (Mainz, 1993) T5.
> 
> Photographs Face (1977)

There's a lot of meta information that goes along with a single inscription above and beyond its transcription and translation, all of it which is necessary to understand the possible significance. I don't think there's a better illustration of what 'close reading' might mean in archaeology, than the epigrapher's art. What might we spot if we look at a corpus of inscriptions from a macro level? What patterns might exist? Is there something going on related to geography? Researcher? language of the inscription? Publication history? Dating? This is where the algorithmns of topic modeling might be useful. My go-to tool for this is [MALLET](http://mallet.cs.umass.edu/index.php). Mallet allows one to strip out all of the xml tags (see MALLET's help file from the command line for -import-dir), so I can download the xml files as zip from the Inscriptions of Aphrodisias site, and begin exploring for patterns. I optimize the interval too when I train the topic model, to shake out the utility of the resulting 'topics'. I began by modeling 50 topics. [You can download the MALLET file and results here, to play with and explore for yourself](http://figshare.com/articles/Exploring_the_Inscriptions_of_Aphrodisias_2_via_topic_modeling/710648). When I look at the results (inscriptionkeys.txt), the 'strongest' topics all relate to metadata regarding their online publication (the top 3). The next few clearly relate to the researchers who are behind the inscriptions of Aphrodisias website, so not overly useful for me here. The next couple seem to be a mixture of findspot information and publishing history: 

> topic6 0.34603 unpublished fragment reynolds face museum version lettering inscription born digital joyce unknown marble expedition white centuries nyu inscribed stray 32 0.23776 face upper moulding left side lettering part lower expedition museum white marble nyu broken aphrodisias asia corner inscribed front topic39 0.15711 south walls east face west block part wall gate expedition findspot city stretch tupman mama lettering depth measurable marble topic7 0.14493 mama gaudin published reinach mccabe cormack kubitschek squeeze notebook phi expedition records originally aphrodisias reichel publications recorded charlotte representations topic43 0.13213 mccabe published originally bodard gabriel rouech aphrodisias phi description findspot reported subsequently charlotte unknown preliminary inscription tidied publication funerary

The remaining topics all deal explicitly with the inscriptions themselves, their texts and their findspots (it seems). 

> topic47 0.06106 son honoured honours people council claudius priest diogenes family tiberius man high cl public gerousia lived virtue life zenon topic8 0.05807 roman family wife names father aphrodisian case daughter suggests citizenship early century reference possibly menodotos clear named civic late topic38 0.05137 son zenon adrastos attalos dionysios athenagoras artemidoros apollonios hypsikles aphrodite diogenes daughter early tupman menestheus cf goddess grandson sons

[caption id="attachment_1794" align="alignleft" width="150"]![Groupings in Inscriptions of Aphrodisias](http://electricarchaeologist.files.wordpress.com/2013/06/inscriptions1.png?w=150) Groupings in Inscriptions of Aphrodisias[/caption] Every file is composed of all these different topics, to differing degrees. I would like to visualize the paths of these discourses through the corpus, so I translate the inscriptioncomp.txt file so that I end up with at at least 9/10s of each document's composition (in practice, this means cutting and pasting the inscriptioncomp.txt file so that I end up with a single list with source-document, target-topic, and weight). I also filtered out those strongest topics described above (5,6,7,9,16,17,29,39,43). I imported this list into Gephi, and set about trying to find groupings of topics and inscriptions, based on the shared patterns (and the weighting) of relationships. I coloured it by group (modularity) and resized nodes based on 'betweeness'. What does betweeness mean here? I think it means the principle ideas (the discourse) that ties this entire collection together. In this case, topic 0: 

> statue base honours shaft ll moulding set city sbi council feature honoured capital aurelius prosopography top moulded ligatures antonius

followed closely by 1 and 37: 

> topic1 sarcophagus funerary inscription front lid standard necropolis aurelius forms buried tomb east formula elements aur rim burial end line

## Comments

**[swimming pool used auto parts fort worth texas](#12443 "2014-01-26 05:57:30"):** Great blog here! Also your site loads up fast! What host are you using? Can I gett your affiliate link to your host? I wish my sit loaded up as fast as yours lol

**[home improvement ideas](#13823 "2014-02-06 21:36:16"):** Better insulation, for example, both saves you money and keeps you warm. In most cases, people in military services and veterans can benefit from extra privileges that allow them to receive a grant without having to pay it back. A handyman might not have the skill to do home improvements.

