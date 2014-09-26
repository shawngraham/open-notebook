title: Patterns in Roman Inscriptions
link: http://electricarchaeology.ca/2013/08/21/patterns-in-roman-inscriptions/
author: fhg1711
description: 
post_id: 1877
created: 2013/08/21 12:11:39
created_gmt: 2013/08/21 17:11:39
comment_status: open
post_name: patterns-in-roman-inscriptions
status: publish
post_type: post

# Patterns in Roman Inscriptions

_Update August 22_ I've now analyzed all 1385 inscriptions. I've put an interactive browser of the visualized topic model at <http://graeworks.net/roman-occupations/>. [caption id="attachment_1878" align="alignleft" width="440"]![See how nicely the Latin clusters?](http://electricarchaeologist.files.wordpress.com/2013/08/roman-occ-cluster.png) See how nicely the Latin clusters?[/caption] I've played with topic modeling inscriptions before. I've now got a very effective script in R that runs the topic model and produces various kinds of output (I'll be sharing the script once the relevant bit from our [book projec](http://www.themacroscope.org/)t goes live). For instance, I've grabbed 220 inscriptions from [Miko Flohr's database](http://www.mikoflohr.nl/databases/occupational_inscriptions/) of inscriptions regarding various occupations in the Roman world(there are many more; like everything else I do, this is a work in progress). Above is the dendrogram of the resulting topics. Remember, those aren't phrases, and I've made no accounting for case endings. (Now, it's worth pointing out that I didn't include any of the meta data for these inscriptions; just the text of the inscription itself, with the diacritical marks removed.) Nevertheless, you get a sense of both the structure and content of the inscriptions, reading from left to right, top to bottom. We can also look at which inscriptions group together based on the similarity matrix of their topics, and graph the result. [caption id="attachment_1879" align="alignleft" width="440"]![roman-occ-graph](http://electricarchaeologist.files.wordpress.com/2013/08/roman-occ-graph.png) Inscriptions, linked based on similarity of the language of the inscription, via topics. If the image appears wonky, just click through.[/caption] So let's look at these groups in a bit more depth. I can take the graph exported by R and import it into Gephi (or another package) to do some exploratory statistical analysis. I've often put a lot of stock in 'betweeness centrality', reckoning that if a document is highly between in a network representation of the patterns of similarity of topics, then that document is representative of the kinds of discourses that run through it. What do we get, then? We get this ([here's the page in the database](http://www.mikoflohr.nl/databases/occupational_inscriptions/200to220/)): 

aurifices
Roma
CIL 6, 9207
Inscription
Occupation

M(arcus) Caedicius Iucundus / aurifex de / sacra via vix(it) a(nnos) XXX // Clodia ...

But there are a lot of subgroupings in this graph. Something like 'closeness' might indicate more locally important inscriptions. In this case, the two with the highest 'closeness' measures are 

aurifices
Roma
CIL 6, 9203
Inscription
Occupation

Protogeni / aurfici / vix(it) an(nos) LXXX / et Claudiae / Pyrallidi con(iugi) ...

and 

aurifices
Roma
CIL 6, 3950
Inscription
Occupation

Lucifer v(ixit) a(nnum) I et d(ies) XLV / Hesper v(ixit) a(nnos) II / Callistus ...

If we look for subgroupings based on the patterning of connections, the biggest subgroup has 22 inscriptions: Dis Manibus Felix publicus Brundisinorum servus aquarius vixit... Dis Manibus Laetus publicus populi Romani 3 aquarius aquae An{n}ionis... Dis Manibus sacrum Euporo servo vilico Caesaris aquario fecit Vestoria Olympias... Nymphis Sanctis sacrum Epictetus aquarius Augusti nostri Dis Manibus Agathemero Augusti liberto fecerunt Asia coniugi suo bene... Agatho Aquarius Caesaris sibi et Anniae Myrine et suis ex parte parietis mediani... Dis Manibus Sacrum Doiae Palladi coniugi dignissimae Caius Octavius... Dis Manibus Tito Aelio Martiali architecto equitum singularium ... Dis Manibus Aureliae Fortunatae feminae incomparabili et de se bene merenti.. Dis Manibus Auliae Laodices filiae dulcissimae Rusticus Augusti libertus... Dis Manibus Tychico Imperatoris Domitiani servo architecto Crispinilliano. Dis Manibus Caio Iulio 3 architecto equitum singularium... Dis Manibus Marco Claudio Tryphoni Augustali dupliciario negotiatori... Dis Manibus Bromius argentarius Faustus 3ae argentari Dis Manibus sacrum Tiberius Claudius Hymeneus aurarius argentarius... Dis Manibus Silio Victori filio et Naebiae Amoebae coniugi et Siliae... Dis Manibus 3C3 argentari Allia coniugi? bene merenti fecit... Dis Manibus Marco Ulpio Augusti liberto Martiali coactori argentario... Suavis 3 aurarius Dis Manibus sacrum Tiberius Claudius Hymeneus aurarius argentarius... Dis Manibus Tito Aurelio Aniceto Augusti liberto aurifici Aurelia... What ties these together? Well, 'dis manibus' is good, but it's pretty common. The occupations in this group are all argentarii, architectii, or aquarii. So that's a bit tighter. Many of these folks are mentioned in conjunction with their spouses. In the next largest group, we get what must be a family (or familia, extended slave family) grouping: Caius Flaminius Cai libertus Atticus argentarius Reatinus Caius Octavius Parthenio Cai Octavi Chresti libertus argentarius Musaeus argentarius Caius Caicius Cai libertus Heracla argentarius de foro Esquilino sibi... Caius Iunius Cai libertus Salvius Caius Iunius Cai libertus Aprodisi... Caius Vedennius Cai filius Quirina Moderatus Antio militavit in legione... Aurifex brattarius Caius Acilius Luci filius Trebonia natus architectus Caius Postumius Pollio architectus Caius Camonius Cai libertus Gratus faber anularius Caius Antistius Isochrysus architectus Elegans architectus Caius Cuppienus Cai filius Pollia Terminalis praefectus cohortis... Cresces architectus Cresces architectus Caius Vedennius Cai filius Quirina Moderatus Antio militavit in legione... Pompeia Memphis fecit sibi et Cnaeo Pompeio Iucundo coniugi suo aurifici... Caius Papius Cai libertus Salvius Caius Papius Cai libertus Apelles... Caius Flaminius Cai libertus Atticus argentarius Reatinus The outliers here are graffitos or must be being picked up by the algorithmn due to the formation of the words; the inclusion of Pompeia in here is interesting, which must be to the overall structure of that inscription. Perhaps a stretch too far to wonder why these would be similar...? This small experiment demonstrates I think the potential of topic modeling for digging out patterns in archaeological/epigraphic materials. In due time I will do Flohr's entire database. [Here are my files to play with yourself](http://figshare.com/articles/Patterns_in_Roman_Inscriptions/777835). [caption id="attachment_1880" align="alignleft" width="440"