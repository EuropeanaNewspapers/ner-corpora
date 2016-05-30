<a href="http://www.europeana-newspapers.eu/"><img src=http://www.europeana-newspapers.eu/wp-content/uploads/2013/09/europeana_newspapers_forwebsite1.jpg></a> 
#ner-corpora
Named Entity Recognition corpora for Dutch, French, German from [Europeana Newspapers](http://www.europeana-newspapers.eu/named-entity-recognition-for-digitised-newspapers/).

### Introduction

The corpora consist of files divided by language, encoded in the BIO format ([Ramshaw & Marcus, 1995](http://www.aclweb.org/anthology/W/W95/W95-0107.pdf)). The BIO format is a simple, text-based format that divides texts into single tokens per line, and, separated by a whitespace, tags to indicate which ones are named entities. The most commonly used tags are *PER* (person), *LOC* (location) and *ORG* (organization). To indicate named entities that span multiple tokens, the tags have a prefix of either *B-* (begining of named entity) or *I-* (continuation of named entity). *O* tags are used to indicate that the token is not a named entity.

Example:
```
The O
NBA B-ORG
player O
Michael B-PER
Jordan I-PER
is O
from O
the O
United B-LOC
States I-LOC
of I-LOC
America I-LOC
. O
```

### Background

The BIO files in this repository are based on OCRed and manually annotated texts from the following libraries:

* [enp_at.bio](https://github.com/EuropeanaNewspapers/ner-corpora/tree/master/enp_at.bio) - newspapers from the [Austrian National Library](http://www.theeuropeanlibrary.org/tel4/newspapers/gallery?provider-id=P01252)
* [enp_de.bio](https://github.com/EuropeanaNewspapers/ner-corpora/tree/master/enp_de.bio) - newspapers from the [Dr Friedrich Teßmann Library](http://www.theeuropeanlibrary.org/tel4/newspapers/gallery?provider-id=P02013)
* [enp_fr.bio](https://github.com/EuropeanaNewspapers/ner-corpora/tree/master/enp_fr.bio) - newspapers from the [National Library of France](http://www.theeuropeanlibrary.org/tel4/newspapers/gallery?provider-id=P01190)
* [enp_nl.bio](https://github.com/EuropeanaNewspapers/ner-corpora/tree/master/enp_nl.bio) - newspapers from the [National Library of the Netherlands](http://www.theeuropeanlibrary.org/tel4/newspapers/gallery?provider-id=P01350)

For the full data set including the [ALTO](http://www.loc.gov/standards/alto/) OCR files and the binary classifiers derived, please go [here](http://lab.kbresearch.nl/static/html/eunews.html).

### License 

[CC0](https://creativecommons.org/publicdomain/zero/1.0/)

This means you are free to use this data without any restrictions - even in commercial applications. 

We're thankful if you give proper attribution though:  

*Europeana Newspapers NER corpora*  
*Europeana Newspapers Project, 2012-2015.*    
*https://github.com/EuropeanaNewspapers/ner-corpora/.*

### References

* [An Open Corpus for Named Entity Recognition in Historic Newspapers](http://www.lrec-conf.org/proceedings/lrec2016/pdf/110_Paper.pdf)  
Proceedings of the 10th edition of the Language Resources and Evaluation Conference, 23-28 May 2016, Portorož, Slovenia.

### Known issues

Due to the way the above corpora were initially constructed, some additional cleanup is required to really leverage the full potential of the data for demanding tasks such as evaluation, where high accuracy data is needed. At the moment, the files are not only full of OCR errors, but even worse, to optimise the classifiers, sentences (and in some cases, parts of sentences) containing a lot of noise have been filtered (i.e. cut). This makes it quite difficult to map the derived texts to the original source articles, and probably has some even worse effects (e.g. Stanford NER evaluates sentence position as a feature). 

Instructions how to help clean up the data can be found [here](https://github.com/EuropeanaNewspapers/ner-corpora/wiki/Corpus-cleanup).
