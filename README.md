# Knowledge graph from Um6p' chemistry papers using NLP and Graphs
![image](https://user-images.githubusercontent.com/56308112/127573839-f21498ce-15eb-4f27-a931-3bbbab6fba0b.png)
## Problem : 
Literature reviewing and documentation, since finding good and relatable scientific resources for your research can be challenging and time-consuming. 
## Solution :
Build a knowledge graph connecting scientific entities occurring in chemistry papers. This enables users to start from a simple query (a chemical substance name or a laboratory procedure) in order to find relatable papers for their quest. 
## How to build it? 
The pipeline starts with scientific entities' extraction from chemistry papers abstracts using a fine-tuned NLP  model on biomedical corpus maintained by Alan Turing Institute researchers. Those entities are then cross-matched with the UMLS database in order to label them. 
Finally, we can build the knowledge graph by connecting keywords that co-occurred in the same paper abstract. 
## Try it yourself! 
I uploaded commented notebooks detailing the pipeline :
> Chimestry-extract 

In this notebook, i use the Scpacy pipeline to extract and label keywords from  papers abstracts then save them to a JSON file with the paper id and other metadata 

- Data format (You can found it in chimestry_papers.json)

```json
{
  "paper_id": {
    "year": 2020,
    "title": "D",
    "paper_type": "Article",
    "keywords": [
      {
        "label": "",
        "canonical form": "",
        "type": ""
      },...
    ]
  },...
}
```
>  Chimestry-process 

The model used is finetuned on Biomedical data so we might have some false labeled keywords we use manual utils to fix the problem 
> Chimestry-graph 
 
In this notebook, we give the code for the knowledge graph creation

## Data 
The data is extracted from the Web of Science database, the papers used for the graph creation are chemistry papers

## Results 
- we use Gephy for graph visualition 
 ![image](https://user-images.githubusercontent.com/56308112/127575932-df2a58bd-dba9-475e-9768-9fe96edd7f0d.png)
![image](https://user-images.githubusercontent.com/56308112/127576019-1128e09a-5106-4d84-a406-18b1ef2f1e20.png)

- the graph can be used eventualy to feed a client app (to be done in the future)
- you can find edges list in the data folder 

