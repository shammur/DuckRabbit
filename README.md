# Paper:On the Taxonomic Pitfalls of Transformer Networks 

The repository include a novel dataset: **DUCKRABBIT**, to probe the ability of neural models to capture semantic hierarchies in use.
The dataset include 

To design the template, we selected different construction including: "except", "particular", "generally",
"and too", "prefer", "comparatives" and "I'd rather". 

For each construction we used different domains such as: animals -- mammals, dogs, birds; objects -- cars, motorcycle, cutlery; food categories -- fruits, desserts, seafood etc.; furniture, names of -- famous actors, politicians, painters among others.

We then collected 4 hyponym per domain, for example: rain -- e.g. drizzle, downpours; cars -- e.g. Volvos, Fords; scientists -- e.g. geneticists, astronomers among others.


Below is a snippet from the template file (except with noun-dog and andtoo with fruits as noun) used to generate the DUCKRABBIT datasets. 
The markers @@1@@, @@2@@, @@3@@-@@4@@ corresponds to  and <img src="https://render.githubusercontent.com/render/math?math=\Disj>
, where as @@5@@ marks the presupposition/acceptable cases by the taxonomy. Upon acceptance, we will release the templates, scripts to extend and manually checked annotation files.



