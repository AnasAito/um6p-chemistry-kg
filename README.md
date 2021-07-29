# Knowledge graph from Um6p' chimestry papers using NLP and Graphs
![image](https://user-images.githubusercontent.com/56308112/127573839-f21498ce-15eb-4f27-a931-3bbbab6fba0b.png)
## Problem : 
literature reviewing and documentation, since finding good and relatable  scientific resources for your research can be challenging and  time-consuming. 
## Solution :
build a knowledge graph connecting scientific entities occurring in chemistry papers. This enables users to start from a simple query (a chemical substance name or a laboratory procedure) in order to find relatable papers for their quest. 
## How to build it ? 
The pipeline start with scientific entities' extraction from chemistry papers abstracts using a fine-tuned NLP  model on biomedical corpus maintained  by Alan Turing Institute researchers. Those entities are then cross-matched with the UMLS database in order to label them. 
Finally, we can build the knowledge graph by connecting keywords that co-occurred in the same paper abstract. 
## Try it yourself ! 
i uploaded commented notebooks detailing the pipeline :
> Chimestry-extract 
in ths notebook i use  Scpacy pipeline to extract and label keywords from  papers abstracts then save them to ajson file with the paper id and other meta data 

>  Chimestry-process 
the model used is finetuned on Biomedical data so we might have some false labeled keywords we use manual utils to fix the problem 
> Chimestry-graph 
In this notebook we give the code for the knowledge graph creation

## Data 
the data is extracted from Web of science database , the paper used for the graph creation are chimestry papers

