# Paper:On the Taxonomic Pitfalls of Transformer Networks 

The repository include a novel dataset: **DUCKRABBIT**, to probe the ability of neural models to capture semantic hierarchies in use.
The dataset was collected by the authors and checked with the help of WordNET. Acceptability was treated as binary.
The data include examples which are either in a taxonomic relation or disjoint. In addition, for disjoint example we also added its inverse. This yielding cases where the presuppositions are satisfied and cases where they are violated due to the unwanted presence/absence of a taxonomic relation or to its wrong order.

This repositoy contains the pattern file used to generate the data (pattern_taxonomies-duckrabbit-dataset.txt) and the expanded dataset (duckrabbit_data.tsv).


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
@inproceedings{Zamparelli20202,
Author = {Shammur Absar Chowdhury and Roberto Zamparelli},
Booktitle = {Arxiv},
Title = {On the Taxonomic Pitfalls of Transformer Networks},
Year = {2021}}
```

* Dedication:

This dataset is respectfully dedicated to [https://en.wikipedia.org/wiki/Amy_Krouse_Rosenthal]_Amy Krouse Rosenthal_, for inspiring us with her amazing writings and her creation "Duck! Rabbit!".



[template]: img/templates.png "DUCKRABBIT Pattern Template"

