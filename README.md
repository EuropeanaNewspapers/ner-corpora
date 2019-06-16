<a href="http://www.europeana-newspapers.eu/"><img src=http://www.europeana-newspapers.eu/wp-content/uploads/2013/09/europeana_newspapers_forwebsite1.jpg></a> 

### ner-corpora
Named Entity Recognition corpus for (historical) Dutch, French and German from [Europeana Newspapers](http://www.europeana-newspapers.eu/named-entity-recognition-for-digitised-newspapers/).

### Introduction

The corpus comprises of one ``.tsv`` file per language following the [GermEval2014](https://sites.google.com/site/germeval2014ner/data) data format. The format is a simple tab-separated-values format that divides texts into single tokens per line with tab-separated annotations. The 1st column contains the token position in the sentence. The 2nd column contains  the token itself. The third column contains the named entity annotation. The fourth column can contain an embedded named entity annotation. Sentence boundaries are indicated with new lines, comments start with ```#```.

The most commonly used categories for tags are ```PER``` (person), ```LOC``` (location) and ```ORG``` (organization) with a prefix of either ```B-``` (beginning of named entity) or ```I-``` (inside of named entity). ```O``` (outside of named entity) is used for tokens that are not a named entity.

Example:
```
# This is an example
1 The O O
2 NBA B-ORG O
3 player  O O
4 Michael B-PER O
5 Jordan  I-PER O
6 is  O O
7 not  O O
8 the O O
9 President B-PER O
10  of  I-PER O
11  the I-PER O
# next we see the embedding structure
12  United  I-PER B-LOC
13  States  I-PER I-LOC
14  of  I-PER I-LOC
15  America I-PER I-LOC
16  . O O
```

### Background

The data in this repository are based on digitized and OCRed historical newspapers sourced from these libraries:

* [enp_DE](https://github.com/EuropeanaNewspapers/ner-corpora/tree/master/enp_DE.tsv) - newspapers from the [Austrian National Library](https://www.onb.ac.at/), [Berlin State Library](https://staatsbibliothek-berlin.de/) and [Dr Friedrich Teßmann Library](https://www.tessmann.it/)
* [enp_FR](https://github.com/EuropeanaNewspapers/ner-corpora/tree/master/enp_FR.tsv) - newspapers from the [National Library of France](https://www.bnf.fr/)
* [enp_NL](https://github.com/EuropeanaNewspapers/ner-corpora/tree/master/enp_NL.tsv) - newspapers from the [National Library of the Netherlands](https://www.kb.nl/)

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

The corpus contains many OCR errors, so further work is still needed to leverage it for demanding tasks like evaluation, where gold standard quality is required. 
Further information on data quality issues and instructions for data cleaning can be found in the [wiki](https://github.com/EuropeanaNewspapers/ner-corpora/wiki).
