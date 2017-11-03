<a href="http://www.europeana-newspapers.eu/"><img src=http://www.europeana-newspapers.eu/wp-content/uploads/2013/09/europeana_newspapers_forwebsite1.jpg></a> 

### ner-corpora
Named Entity Recognition corpora for Dutch, French, German from [Europeana Newspapers](http://www.europeana-newspapers.eu/named-entity-recognition-for-digitised-newspapers/).

### Introduction

The corpora comprise of files per by language that are encoded in the IOB format ([Ramshaw & Marcus, 1995](http://www.aclweb.org/anthology/W/W95/W95-0107.pdf)). The IOB format is a simple text chunking format that divides texts into single tokens per line, and, separated by a whitespace, tags to mark named entities. The most commonly used categories for tags are ```PER``` (person), ```LOC``` (location) and ```ORG``` (organization). To mark named entities that span multiple tokens, the tags have a prefix of either ```B-``` (beginning of named entity) or ```I-``` (inside of named entity). ```O``` (outside of named entity) tags are used to mark tokens that are not a named entity.

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

The IOB files in this repository are based on OCRed and manually annotated historical newspapers from these libraries:

* [enp_DE.onb.bio](https://github.com/EuropeanaNewspapers/ner-corpora/tree/master/enp_DE.onb.bio) - newspapers from the [Austrian National Library](http://www.theeuropeanlibrary.org/tel4/newspapers/gallery?provider-id=P01252)
* [enp_DE.lft.bio](https://github.com/EuropeanaNewspapers/ner-corpora/tree/master/enp_DE.lft.bio) - newspapers from the [Dr Friedrich Teßmann Library](http://www.theeuropeanlibrary.org/tel4/newspapers/gallery?provider-id=P02013)
* [enp_DE.sbb.bio](https://github.com/EuropeanaNewspapers/ner-corpora/tree/master/enp_DE.sbb.bio) - newspapers from the [Berlin State Library](http://www.theeuropeanlibrary.org/tel4/newspapers/gallery?provider-id=P01606)
* [enp_FR.bnf.bio](https://github.com/EuropeanaNewspapers/ner-corpora/tree/master/enp_FR.bnf.bio) - newspapers from the [National Library of France](http://www.theeuropeanlibrary.org/tel4/newspapers/gallery?provider-id=P01190)
* [enp_NL.kb.bio](https://github.com/EuropeanaNewspapers/ner-corpora/tree/master/enp_NL.kb.bio) - newspapers from the [National Library of the Netherlands](http://www.theeuropeanlibrary.org/tel4/newspapers/gallery?provider-id=P01350)

To download the the source [ALTO](http://www.loc.gov/standards/alto/) OCR files or the trained CRF classifier binaries, please go [here](http://lab.kb.nl/dataset/europeana-newspapers-ner#access).

### License 

[CC0](https://creativecommons.org/publicdomain/zero/1.0/)

### Attribution 

*Europeana Newspapers NER corpora*       
*https://github.com/EuropeanaNewspapers/ner-corpora/*    
*Europeana Newspapers Project, 2012-2015*     
*http://www.europeana-newspapers.eu/*   

### References

* [An Open Corpus for Named Entity Recognition in Historic Newspapers](http://www.lrec-conf.org/proceedings/lrec2016/summaries/110.html)  
Proceedings of the 10th edition of the Language Resources and Evaluation Conference (LREC 2016), 23-28 May 2016, Portorož, Slovenia.

### Known issues

The way the above corpora were produced, additional work is required to leverage the data for tasks such as evaluation, where gold standard quality is required as the data still contains many OCR errors. Also, due to post-processing, parts of sentences containing a high degree of noise were cut, which makes it difficult to map the annotated texts to the original newspaper articles and may entail unintended effects on classification.

Further information on data quality issues and instructions to clean up the data can be found in the [wiki](https://github.com/EuropeanaNewspapers/ner-corpora/wiki).
