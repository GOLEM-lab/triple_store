# Golem Triple Store repository
Here, you will find data, code and notebooks related to the GOLEM lab triple store.
## GOLEM predicates
These are the predicates that are currently available:
![screenshot](https://github.com/GOLEM-lab/triple_store/assets/155955568/7815fde7-a71b-42b7-bc40-59fe1331da3f)


## Example Queries
```
PREFIX golem: <https://golemlab.eu/graph/> 
SELECT ?o (COUNT(?o) as ?oCount) WHERE
{
  ?s golem:fandom "Biohazard"  .
  ?s golem:language ?o  .
}

GROUP BY ?o
ORDER BY DESC(?oCount)
```
[Try me!](http://194.171.203.17:8890/sparql/?default-graph-uri=&qtxt=PREFIX%20golem%3A%20%3Chttps%3A%2F%2Fgolemlab.eu%2Fgraph%2F%3E%20%0ASELECT%20%3Fo%20(COUNT(%3Fo)%20as%20%3FoCount)%20WHERE%0A%7B%0A%20%20%3Fs%20golem%3Afandom%20%22Biohazard%22%20%20.%0A%20%20%3Fs%20golem%3Alanguage%20%3Fo%20%20.%0A%7D%0A%0AGROUP%20BY%20%3Fo%0AORDER%20BY%20DESC(%3FoCount)%0A&format=text%2Fhtml&timeout=0&signal_void=on)

```
PREFIX golem: <https://golemlab.eu/graph/> 
SELECT ?o WHERE
{
  ?s golem:keyword "Depression" .
  ?s golem:language  "Deutsch" .
  ?s golem:title ?o .
}
```
[Try me!](http://194.171.203.17:8890/sparql/?default-graph-uri=&qtxt=%0APREFIX%20golem%3A%20%3Chttps%3A%2F%2Fgolemlab.eu%2Fgraph%2F%3E%20%0ASELECT%20%3Fo%20WHERE%0A%7B%0A%20%20%3Fs%20golem%3Akeyword%20%22Depression%22%20.%0A%20%20%3Fs%20golem%3Alanguage%20%20%22Deutsch%22%20.%0A%20%20%3Fs%20golem%3Atitle%20%3Fo%20.%0A%7D&format=text%2Fhtml&timeout=0&signal_void=on)

```
PREFIX golem: <https://golemlab.eu/graph/>
SELECT (COUNT(?s) as ?sCount) WHERE {
	?s golem:fandom "Star Trek: Voyager" .
	?s golem:socialRelationships ?rel .
   	FILTER(CONTAINS(?rel, 'Janeway')||CONTAINS(?rel, 'Kathryn') )
}
```
[Try me!](http://194.171.203.17:8890/sparql/?default-graph-uri=&qtxt=PREFIX%20golem%3A%20%3Chttps%3A%2F%2Fgolemlab.eu%2Fgraph%2F%3E%0ASELECT%20(COUNT(%3Fs)%20as%20%3FsCount)%20WHERE%20%7B%0A%09%3Fs%20golem%3Afandom%20%22Star%20Trek%3A%20Voyager%22%20.%0A%09%3Fs%20golem%3AsocialRelationships%20%3Frel%20.%0A%20%20%20%09FILTER(CONTAINS(%3Frel%2C%20'Janeway')%7C%7CCONTAINS(%3Frel%2C%20'Kathryn')%20)%0A%7D&format=text%2Fhtml&timeout=0&signal_void=on)
