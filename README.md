# DuckRabbit: a dataset on taxonomic presupposition violations


The repository contains the dataset used in `On the Taxonomic Pittfalls of Transformer Networks` to probe the ability of neural models to capture semantic hierarchies and their use in constructions that enforce presuppositions on the taxonomic relation (“birds/sparrows”, “cities/Rome”) among two arguments.

The dataset was created by the authors as set of templates designed to be acceptable or not acceptable. Acceptability was treated as binary. Potentially problematic hierarchical relations were checked with the help of WordNET. The templates were expanded by the script,, generating a set of 8355 acceptable and 11697 unacceptable sentences, which may be used to test the ability of any artificial language processing system to detect pure semantic deviance (following much work on syntactic deviance, e.g. [Gulordava et al 2018](https://www.aclweb.org/anthology/N18-1108/) , [Willcox et al. 2018](https://www.aclweb.org/anthology/W18-5423/), [Futrell at al. 2019])(https://www.aclweb.org/anthology/N19-1004/).

To generate the templates, we considered a sample set of constructions that enforce presuppositions on the taxonomic status of their arguments, i.e. whether one argument can denote a subset of the other, and if so, which one should denote the superset. We then created cases which systematically obeyed or violated these presuppositions. To examplify,  comparatives (1) forbit taxonomic relations, while “in particular” (2) enforces it in a SUPERSET - SUBSET order.

```
1) a. I like birds more than dogs
    b. I like dogs more than birds
    c. *I like birds more than sparrows.
    d. *I like sparrows more than birds
2)  a. *I like birds, and dogs in particular.
     b. *I like dogs, and birds in particular
     c.  I like birds, and sparrows in particular.
     d. *I like sparrows, and birds in particular.
```     

In cases like (1a,b) where neither argument is supposed to be a subset of the other, we give both orders. 

This repository contains the pattern file used to generate the data (pattern_taxonomies-duckrabbit-dataset.txt) and the expanded dataset (duckrabbit_data.tsv). Both the semantic category of the linearly first argument (e.g. fruits, dogs...) and the type of construction are given in the ID of the examples.



## Template File:
File: pattern_taxonomies-duckrabbit-dataset.txt

To design the template, we selected different construction including: "except", "particular", "generally", "and too", "prefer", "comparatives" and "I'd rather". 

For each construction we used different domains such as: animals -- mammals, dogs, birds; objects -- cars, motorcycle, cutlery; food categories -- fruits, desserts, seafood etc.; furniture, names of -- famous actors, politicians, painters among others.

We then collected 4 hyponym per domain, for example: rain -- e.g. drizzle, downpours; cars -- e.g. Volvos, Fords; scientists -- e.g. geneticists, astronomers among others. Please check the below paper for more details:

Below is a snippet from the template file (except with noun-dog and andtoo with fruits as noun) used to generate the DUCKRABBIT datasets. 
The markers @@1@@, @@2@@, @@3@@-@@4@@ corresponds to >, < and NR (to represent no-relation and NR* is in iverted order), where as @@5@@ marks the presupposition/acceptable cases by the taxonomy. 

![template_snippet][template]

## Expanded File:
File: duckrabbit_data.tsv

The file includes the dataset with following columns:

<ID\>: Index the examples

<SENTENCE\>:	sentence used to probe the intend model

<BLOCK\>:	block id (this is unique to each pattern-type). This id also represent groups of sentences to be compared together for taxonomic relation or disjoint analysis.

<PATTERN_TYPE\>:	this include information for the construction and the domain as mentioned above

<ACTUAL\>:	the current situation in the example. NR=No-relation, NR*=No-relation with inverted orders, "\>"=subset - superset, "<"=superset - subset

<ACCEPTABLE\>:  the acceptability status of the sentence (Y=acceptable/N=not-acceptable)

For example:
```
ID	SENTENCE	BLOCK	PATTERN_TYPE	ACTUAL	ACCEPTABLE
0	I like huskies , except cats .	0	except-dogs	NR	N
1	I like cats , except huskies .	0	except-dogs	NR*	N
2	I like huskies , except dogs .	0	except-dogs	<	N
3	I like dogs , except huskies .	0	except-dogs	>	Y
```


* To cite the paper:
```
@inproceedings{Zamparelli2021,
Author = {Shammur Absar Chowdhury and Roberto Zamparelli},
Booktitle = {Arxiv},
Title = {On the Taxonomic Pitfalls of Transformer Networks},
Year = {2021}}
```

* Dedication:

This dataset is respectfully dedicated to _Amy Krouse Rosenthal_, for inspiring us with her amazing writings and her creation "Duck! Rabbit!".
[https://en.wikipedia.org/wiki/Amy_Krouse_Rosenthal]


[template]: img/templates.png "DUCKRABBIT Pattern Template"

