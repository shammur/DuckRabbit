# Paper:On the Taxonomic Pitfalls of Transformer Networks 

The repository include a novel dataset: **DUCKRABBIT**, to probe the ability of neural models to capture semantic hierarchies in use.
The dataset include 

## Template File:
File: 

To design the template, we selected different construction including: "except", "particular", "generally", "and too", "prefer", "comparatives" and "I'd rather". 

For each construction we used different domains such as: animals -- mammals, dogs, birds; objects -- cars, motorcycle, cutlery; food categories -- fruits, desserts, seafood etc.; furniture, names of -- famous actors, politicians, painters among others.

We then collected 4 hyponym per domain, for example: rain -- e.g. drizzle, downpours; cars -- e.g. Volvos, Fords; scientists -- e.g. geneticists, astronomers among others. Please check the below paper for more details:

Below is a snippet from the template file (except with noun-dog and andtoo with fruits as noun) used to generate the DUCKRABBIT datasets. 
The markers @@1@@, @@2@@, @@3@@-@@4@@ corresponds to >, < and NP (to represent no-relation)
, where as @@5@@ marks the presupposition/acceptable cases by the taxonomy. 

![template_snippet][template]



[template]: img/template.png "DUCKRABBIT Pattern Template"

