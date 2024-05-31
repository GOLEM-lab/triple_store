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
```
PREFIX golem: <https://golemlab.eu/graph/> 
SELECT ?o WHERE
{
  ?s golem:keyword "Depression" .
  ?s golem:language  "Deutsch" .
  ?s golem:title ?o .
}
```

```
PREFIX golem: <https://golemlab.eu/graph/>
SELECT (COUNT(?s) as ?sCount) WHERE {
	?s golem:fandom "Star Trek: Voyager" .
	?s golem:socialRelationships ?rel .
   	FILTER(CONTAINS(?rel, 'Janeway')||
	CONTAINS(?rel, 'Kathryn') )
}
```
