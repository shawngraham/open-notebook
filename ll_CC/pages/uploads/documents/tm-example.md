---
author: Shawn Graham
date: Sept 29 2014
title: An Example Topic Model Script
...

This is for an example of using Mimno's wrapper for Mallet. We're using
the sample data that comes bundeled when you download MALLET from
<http://mallet.cs.umass.edu/download.php>. We've assumed that, on Mac,
you've put MALLET that you unzipped from Umass into a folder under
[user], ie "shawngraham/mallet-2.0.7" (on windows, use the full path
"C:\>\\mallet-2.0.7\\" ). Insert the path to your documents between the
quotation marks and windows users be sure to use double back slashes
instead of a single backslash.

We're assuming that you've already installed the mallet wrapper for R;
if not, uncomment and run this line: install.packages('mallet')

    require(mallet)

    ## Loading required package: mallet
    ## Loading required package: rJava

import the documents from the folder each document is here its own text
file

    documents <- mallet.read.dir("mallet-2.0.7/sample-data/web/en/") 
    # windows users, remember: have the full path, ie "C:\\mallet-2.0.7\\sample-data\\web\\" and so on throughout this script

    mallet.instances <- mallet.import(documents$id, documents$text, "mallet-2.0.7/stoplists/en.txt", token.regexp = "\\p{L}[\\p{L}\\p{P}]+\\p{L}")

create topic trainer object

    n.topics <- 10
    topic.model <- MalletLDA(n.topics)

load documents

    topic.model$loadDocuments(mallet.instances)

    ## Get the vocabulary, and some statistics about word frequencies.
    ## These may be useful in further curating the stopword list.
    vocabulary <- topic.model$getVocabulary()
    word.freqs <- mallet.word.freqs(topic.model)
    ## Optimize hyperparameters every 20 iterations,
    ## after 50 burn-in iterations.
    topic.model$setAlphaOptimization(20, 50)

    ## Now train a model. Note that hyperparameter optimization is on, by default.
    ## We can specify the number of iterations. Here we'll use a large-ish round number.
    topic.model$train(200)

    ## NEW: run through a few iterations where we pick the best topic for each token,
    ## rather than sampling from the posterior distribution.
    topic.model$maximize(10)

Get the probability of topics in documents and the probability of words
in topics. By default, these functions return raw word counts. Here we
want probabilities, so we normalize, and add "smoothing" so that nothing
has exactly 0 probability.

    doc.topics <- mallet.doc.topics(topic.model, smoothed=T, normalized=T)
    topic.words <- mallet.topic.words(topic.model, smoothed=T, normalized=T)  ##adap jockers wordcloud script to use this variable

from <http://www.cs.princeton.edu/~mimno/R/clustertrees.R> transpose and
normalize the doc topics

    topic.docs <- t(doc.topics)
    topic.docs <- topic.docs / rowSums(topic.docs)
    write.csv(topic.docs, "topics-docs.csv" ) ## "C:\\Mallet-2.0.7\\topic-docs.csv"

Get a vector containing short names for the topics

    topics.labels <- rep("", n.topics)
    for (topic in 1:n.topics) topics.labels[topic] <- paste(mallet.top.words(topic.model, topic.words[topic,], num.top.words=5)$words, collapse=" ")

have a look at keywords for each topic

    topics.labels

    ##  [1] "equipartition theorem average energy system"
    ##  [2] "thespis gilbert sullivan opera theatre"     
    ##  [3] "test hill australian cricket including"     
    ##  [4] "zinta indian film actress hindi"            
    ##  [5] "gunnhild life norway needham london"        
    ##  [6] "thylacine tasmanian extinct tiger back"     
    ##  [7] "battle hawes union confederate kentucky"    
    ##  [8] "rings system dust ring number"              
    ##  [9] "sunderland echo world newspaper east"       
    ## [10] "yard national wilderness years park"

    write.csv(topics.labels, "topics-labels.csv") ## "C:\\Mallet-2.0.7\\topics-labels.csv")

Or we could do word clouds of the topics

    library(wordcloud)

    ## Loading required package: RColorBrewer

    for(i in 1:10){
      topic.top.words <- mallet.top.words(topic.model,
                                          topic.words[i,], 10)
      print(wordcloud(topic.top.words$words,
                      topic.top.words$weights,
                      c(4,.8), rot.per=0,
                      random.order=F))
    }

![](media/image1.png)

![](media/image2.png)

![](media/image3.png)

![](media/image4.png)

![](media/image5.png)

![](media/image6.png)

![](media/image7.png)

![](media/image8.png)

![](media/image9.png)

![](media/image10.png)
