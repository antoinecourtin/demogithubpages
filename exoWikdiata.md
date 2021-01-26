## Exo Wikidata

### 1ère requête

'''SPARQL
#1er: juste les peintures de monet 
SELECT ?item 
WHERE
{
  ?item wdt:P31 wd:Q3305213 .
  ?item wdt:P170 wd:Q296 .
}
'''
