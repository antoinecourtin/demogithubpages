## Exo Wikidata

### 1ère requête

>  juste les peintures de monet

````sparql
#1er: juste les peintures de monet 
SELECT ?item 
WHERE
{
  ?item wdt:P31 wd:Q3305213 .
  ?item wdt:P170 wd:Q296 .
}
````
##### Résultat 
<iframe style="width: 60vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%231er%3A%20juste%20les%20peintures%20de%20monet%20%0ASELECT%20%3Fitem%20%0AWHERE%0A%7B%0A%20%20%3Fitem%20wdt%3AP31%20wd%3AQ3305213%20.%0A%20%20%3Fitem%20wdt%3AP170%20wd%3AQ296%20.%0A%7D%0A" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups" ></iframe>

### 2ème requête

> avec les labels (via le service wikibase:label) et les images associées

````sparql
SELECT ?item ?itemLabel ?pic ?CollectionLabel
WHERE
{
  ?item wdt:P31 wd:Q3305213 .
  ?item wdt:P170 wd:Q296 .
  ?item wdt:P18 ?pic .
  SERVICE wikibase:label { 
bd:serviceParam wikibase:language "fr,en"}
}
````
##### Résultat 
<iframe style="width: 60vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3AImageGrid%0ASELECT%20DISTINCT%20%3Fitem%20%3FitemLabel%20%3Fpic%20%3FCollectionLabel%0AWHERE%0A%7B%0A%20%20%3Fitem%20wdt%3AP31%20wd%3AQ3305213%20.%0A%20%20%3Fitem%20wdt%3AP170%20wd%3AQ296%20.%0A%20%20%3Fitem%20wdt%3AP18%20%3Fpic%20.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20%0Abd%3AserviceParam%20wikibase%3Alanguage%20%22fr%2Cen%22%7D%0A%7D" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups" ></iframe>

### 3ème requête

>  avec en option (via OPTIONAL) les collections/lieux de conservation

````sparql
SELECT ?item ?itemLabel ?pic ?CollectionLabel
WHERE
{
  ?item wdt:P31 wd:Q3305213 .
  ?item wdt:P170 wd:Q296 .
  ?item wdt:P18 ?pic .
  SERVICE wikibase:label { 
bd:serviceParam wikibase:language "fr,en"}
  OPTIONAL { 
  ?item wdt:P195 ?Collection
    }
}
````
##### Résultat 

<iframe style="width: 60vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3AMap%0ASELECT%20DISTINCT%20%3Fitem%20%3FitemLabel%20%3Fpic%20%3FCollectionLabel%20%3FLocalisation%0AWHERE%0A%7B%0A%20%20%3Fitem%20wdt%3AP31%20wd%3AQ3305213%20.%0A%20%20%3Fitem%20wdt%3AP170%20wd%3AQ296%20.%0A%20%20%3Fitem%20wdt%3AP18%20%3Fpic%20.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20%0Abd%3AserviceParam%20wikibase%3Alanguage%20%22fr%2Cen%22%7D%0A%20%20OPTIONAL%20%7B%20%0A%20%20%3Fitem%20wdt%3AP195%20%3FCollection.%0A%20%20%3FCollection%20wdt%3AP625%20%3FLocalisation%20%20%0A%20%20%20%20%7D%0A%7D" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups" ></iframe>

### 4ème requête

>  compter le nombre de Monet dans chaque collection/lieux de conservation et les afficher par odre décroissant

````sparql
SELECT ?CollectionLabel (COUNT(?item) AS ?count)
WHERE
{
  ?item wdt:P31 wd:Q3305213 .
  ?item wdt:P170 wd:Q296 .
  ?item wdt:P18 ?pic .
  SERVICE wikibase:label { 
bd:serviceParam wikibase:language "fr,en"}
  OPTIONAL { 
  ?item wdt:P195 ?Collection
    }
}
GROUP BY ?CollectionLabel
ORDER BY DESC (?count)
````
##### Résultat 
<iframe style="width: 60vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3ABarChart%0ASELECT%20%3FCollectionLabel%20%28COUNT%28%3Fitem%29%20AS%20%3Fcount%29%0AWHERE%0A%7B%0A%20%20%3Fitem%20wdt%3AP31%20wd%3AQ3305213%20.%0A%20%20%3Fitem%20wdt%3AP170%20wd%3AQ296%20.%0A%20%20%3Fitem%20wdt%3AP18%20%3Fpic%20.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20%0Abd%3AserviceParam%20wikibase%3Alanguage%20%22fr%2Cen%22%7D%0A%20%20OPTIONAL%20%7B%20%0A%20%20%3Fitem%20wdt%3AP195%20%3FCollection%0A%20%20%20%20%7D%0A%7D%0AGROUP%20BY%20%3FCollectionLabel%0AORDER%20BY%20DESC%20%28%3Fcount%29" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups" ></iframe>
