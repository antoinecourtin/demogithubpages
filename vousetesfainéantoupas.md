## Excerice pour le 26 janvier 2022

>  exercice : afficher dans une page markdown d'un répertoire github, la requête SPARQL ainsi que le résultat de la requête sous forme d'une carte 
>  la requête : toutes les sculptures de Rodin conservé dans un musée américain

#### Requête 1

````sparql
#defaultView:Map
SELECT ?item ?itemLabel ?lieuconservation ?lieuconservationLabel ?lieuconservationCoord ?datecreation
WHERE
{
  ?item wdt:P31 wd:Q860861 .
  ?item wdt:P170 wd:Q30755 .
  ?item wdt:P571 ?datecreation.

   ?item wdt:P276 ?lieuconservation .
   ?lieuconservation wdt:P17 wd:Q30. 
    ?lieuconservation wdt:P625 ?lieuconservationCoord.

    SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }

  }
````
<iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3AMap%0ASELECT%20%3Fitem%20%3FitemLabel%20%3Flieuconservation%20%3FlieuconservationLabel%20%3FlieuconservationCoord%20%3Fdatecreation%0AWHERE%0A%7B%0A%20%20%3Fitem%20wdt%3AP31%20wd%3AQ860861%20.%0A%20%20%3Fitem%20wdt%3AP170%20wd%3AQ30755%20.%0A%20%20%3Fitem%20wdt%3AP571%20%3Fdatecreation.%0A%0A%20%20%20%3Fitem%20wdt%3AP276%20%3Flieuconservation%20.%0A%20%20%20%3Flieuconservation%20wdt%3AP17%20wd%3AQ30.%20%0A%20%20%20%20%3Flieuconservation%20wdt%3AP625%20%3FlieuconservationCoord.%0A%0A%20%20%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%0A%20%20%7D" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups" ></iframe>
