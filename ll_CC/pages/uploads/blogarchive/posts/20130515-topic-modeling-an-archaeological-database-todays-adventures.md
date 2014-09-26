title: Topic Modeling an archaeological database: today's adventures
link: http://electricarchaeology.ca/2013/05/15/topic-modeling-an-archaeological-database-todays-adventures/
author: fhg1711
description: 
post_id: 1768
created: 2013/05/15 12:17:18
created_gmt: 2013/05/15 17:17:18
comment_status: open
post_name: topic-modeling-an-archaeological-database-todays-adventures
status: publish
post_type: post

# Topic Modeling an archaeological database: today's adventures

_If you follow me on twitter, and saw a number of bizarre/cryptic tweets today, I was live tweeting my work stream. This is what I did today - think of this as stream of consciousness over the last five hours._

  * imported portable antiquities scheme database into access so I could work with it.
  * queried it, selecting just those columns I was interested in
  * exported back to csv
  * cleaned up the data by removing '=' signs (circular reference error in excel), names of liason officers, meta notes from PAS on the quality of the record, and indications that the record was sourced from the work of Guest and Wells (nb, not any citations to them). also celtic coins index note.
  * run a simple defaults topic model to get a sense of what words I need to add to a custom stopwords list.
  * 552438 rows (id numbers run to 548561, so I must have lost some).
it occurs to me that I should have left the names of the liason officers in, in case they get associated with a particular topic. d'oh. bin\mallet import-file --input pasnebraska/everything.csv --output paseverything.mallet --keep-sequence --token-regex '[\p{L}\p{M}\p{N}]+' --remove-stopwords bin\mallet train-topics --input paseverything.mallet --num-topics 50 --optimize-interval 20 --output-state topic-state.gz --output-topic-keys everything_keys.txt --output-doc-topics everything_composition.txt 
  * then run this? http://article.gmane.org/gmane.comp.ai.mallet.devel/1483/  yes, as per options suggested by @mwidner on twitter on may 14.
  * I think these results will be more useful than the previous ones. Although I believe I forgot to optimize-interval. Yes, I did.
so, running this: bin\mallet run cc.mallet.topics.tui.TopicTrainer --input paseverything.mallet --num-topics 50 --optimize-interval 20 --diagnostics-file everythingdiagnostics.xml --output-topic-keys everythingdiag_keys.txt --output-doc-topics everythingdiag_topics.txt --xml-topic-pharse-report everythingdiag_phrase.txt --xml-topic-report everythingdiag_topicreport.xml --topic-word-weights-file everythingdiag_word_weights.txt --word-topic-counts-file everythingdiag_word_counts.txt --output-state output-state.gz looking at the results, it looks like the first two columns, first three? were taken to be labels. shite. 
  * reformat csv so that I have an id, and a text, per row.
  * found formula to combine all columns into a single column. but blank rows are buggering things up:
=stoneage!B1&" "&stoneage!C1&stoneage!D1&" "&stoneage!E1&" "&stoneage!F1&" "&stoneage!G1&stoneage!H1&" "&stoneage!I1&" "&stoneage!J1&" "&stoneage!K1&stoneage!L1&" "&stoneage!M1&" "&stoneage!N1&" "&stoneage!O1&stoneage!P1&" "&stoneage!Q1&" "&stoneage!R1&" "&stoneage!S1&stoneage!T1&" "&stoneage!U1&" "&stoneage!V1&" "&stoneage!W1&stoneage!X1&" "&stoneage!Y1&" "&stoneage!Z1&" "&stoneage!AA1&stoneage!AB1&" "&stoneage!AC1 
  * returned to access database. gone with the april pas database (csv, download). importing selected columns, ignoring column shift. filtering out blank rows (and/or rows where everything's colunm shifted all over the place)
  * exporting by period. leaving liason officers in. too bloody awkward to deal with the entire database at once.
  * put all the columns into a single column, so now I have just two: an id number, and a 'text'.
  * imported, with regex, and diagnostics topic model,
wierd errors when running the model. 
  * reimporting without regex.
  * rerunning with diagnostics. looks much better.
topic composition file is crazy talk. 
  * ok, screw diagnostics. run normal. optimization 20, topics 50, for stoneage (9680 records).
ok, still the same problem with the composition file. What the hang? 
  * re-running without optimization.
nope, still getting this kind of thing: 

> #doc name topic proportion ... "0 51" "FLAKE 10 0.480592529670674 44 0.3208674000538096 32 0.10756601869328378 "15 422" BLADE NEOLITHIC -4000 -2200 "Black/grey 22 0.8415325393137797 30 0.12728676320083662

So, that says to me that something weird happened in the initial import. Yet topic keys seem to make sense. Sigh... Wait, over on Mallet page it says, 

> ... the first token of each line (whitespace delimited, with optional comma) becomes the instance name, the second token becomes the label, and all additional text on the line is interpreted as a sequence of word tokens.

Simple as that? So I just need a bloody extra column in there. For the love of god... 

  * add column. filled it with document id (again).
  * reimporting. no regex.
  * running the topic model with diagnostics. 50 topics, optimized interval of 20.
By god, that was it. Almost. Something still weird with the document names. Ah, found it. A blank in the first few rows. 
  * reimporting. no regex.
  * running the topic model with diagnostics. 50 topics, optimized interval of 20.

# _SUCCESS!_

Now to repeat with other periods (I elided palaeo, meso, and neolithic into a separate csv file). Then to interpret what all this means. And I think I really need to reformulate my idea of 'document' to not be the individual rows, but rather the districts. I could pull all that out by hand, but I really want to figure out how to make the computer do that. Anyway, some of the 'topics' from today's adventures (what are 'topics' anyway? what might it mean, archaeologically, to think of these as 'discourses'?, are some questions I need to ask): 

> implement lithic mesolithic neolithic flint flake bc blade dating date waste possibly period atherton rachel worked core flakes circa grey flint colour brown dark neolithic light flake mottled cortex mid white cream flakes patina pale coloured knapped translucent neolithic age bronze early flint date late scraper bc flake probable tool dating complete retouched knife made part tertiary scraper end neolithic tool flint retouch semi edge circular thumb distal dorsal face abrupt side cortex nail thumbnail plan core platform flint mesolithic single flakes removed cortex worked scars platforms tl pebble neolithic striking multi removals small blades flake flint cortex rface dorsal grey retouch neolithic edge small damage face remaining scars edges brown secondary made white bulb flake percussion platform striking end ventral rface flint proximal dorsal face neolithic scars small grey mid distal patina side plan end profile margin left distal retouched dorsal proximal shaped flake flint convex scraper ventral snapped edge plano mm mea length res width weighs flake flint neolithic ring wide long weighing adams kurt thick thickness west blade section implement plan neolithic lithic triangular shaped date cross shape object oval rectangular rface sides roughly worked edge knapped hill graham south flake west cornwall paul penwith flint sw margin cream end grey brown distal fig dorsal translucent arrowhead neolithic leaf shaped flint tanged worked tip barbed point triangular broken early faces transverse missing oblique invasive tang blade end distal mesolithic proximal snapped broken retouch flint ends parallel dorsal edges break incomplete missing sides damage long