## Excerice pour le 26 janvier 2022

>  exercice : afficher dans une page markdown d'un répertoire github, la requête SPARQL ainsi que le résultat de la requête sous forme d'une carte 
>  la requête : toutes les sculptures de Rodin conservé dans un musée américain

#### Requête

````sparql
#ceci est une fausse requête
SELECT ?item ?itemLabel ?itemdescription ?itemdescriptionEN ?image ?lieuconservation ?lieuconservationLabel ?lieuconservationCoord
WHERE
{
  ?item wdt:P31 wd:Q3305213 .
  ?item wdt:P170 wd:Q296 .
  OPTIONAL {
    ?item wdt:P18 ?image.

}
  ?item schema:description ?itemdescription.
  FILTER(LANG(?itemdescription) = "fr")
    ?item schema:description ?itemdescriptionEN.
  FILTER(LANG(?itemdescriptionEN) = "en")
  SERVICE wikibase:label { bd:serviceParam wikibase:language "fr,en". }
}
````

#### Résultats

<iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3AMap%0ASELECT%20%3Fitem%20%3FitemLabel%20%20%3Fimage%20%3Flieuconservation%20%3FlieuconservationLabel%20%3FlieuconservationCoord%0AWHERE%0A%7B%0A%20%20%3Fitem%20wdt%3AP31%2Fwdt%3AP279%2a%20wd%3AQ860861%20.%0A%20%20%3Fitem%20wdt%3AP170%20wd%3AQ30755%20.%0A%20%20OPTIONAL%20%7B%0A%20%20%20%20%3Fitem%20wdt%3AP18%20%3Fimage.%0A%20%20%20%20%3Fitem%20wdt%3AP276%20%3Flieuconservation%20.%0A%20%20%20%20%3Flieuconservation%20wdt%3AP17%20wd%3AQ30.%0A%20%20%20%20%3Flieuconservation%20wdt%3AP625%20%3FlieuconservationCoord.%0A%7D%0A%20%20%7D%0A" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups" ></iframe>
