## Les fromages
### Le jeu de données 
Le jeu de données est disponible [ici](https://data.opendatasoft.com/explore/dataset/fromagescsv-fromagescsv%40public/information/?disjunctive.fromage)
<iframe src="https://data.opendatasoft.com/explore/embed/dataset/fromagescsv-fromagescsv@public/table/?disjunctive.fromage&static=false&datasetcard=false" width="900" height="450" frameborder="0"></iframe>

> Il est rigolo de voir içi que certains fromages sont encore peu connus et n'ont pas de page wikipedia en anglais ! 

### Qui fait le plus de fromage ? Ou il fait froid ?

<iframe frameborder="0" width="900" height="600" src="https://data.opendatasoft.com/map/embed/carte_des_fromages/?&static=false&scrollWheelZoom=false"></iframe>

### De la Vache ou de la brebis ?

<iframe src="https://data.opendatasoft.com/chart/embed/?dataChart=eyJ0aW1lc2NhbGUiOiIiLCJxdWVyaWVzIjpbeyJjaGFydHMiOlt7ImFsaWduTW9udGgiOnRydWUsInR5cGUiOiJ0cmVlbWFwIiwiZnVuYyI6IkNPVU5UIiwic2NpZW50aWZpY0Rpc3BsYXkiOnRydWUsImNvbG9yIjoicmFuZ2UtY3VzdG9tIn1dLCJjb25maWciOnsiZGF0YXNldCI6ImZyb21hZ2VzY3N2LWZyb21hZ2VzY3N2QHB1YmxpYyIsIm9wdGlvbnMiOnt9fSwieEF4aXMiOiJsYWl0IiwibWF4cG9pbnRzIjoyMDAsInNvcnQiOiIiLCJzZXJpZXNCcmVha2Rvd24iOiIiLCJzZXJpZXNCcmVha2Rvd25UaW1lc2NhbGUiOiIifV0sImFsaWduTW9udGgiOnRydWUsImRpc3BsYXlMZWdlbmQiOnRydWV9&static=false&datasetcard=true" width="900" height="450" frameborder="0"></iframe>

> on voit tout de suite un soucis dans les données avec vache**s**


### Autre type de graphique 

<iframe src="https://data.opendatasoft.com/chart/embed/eer/?&static=false&datasetcard=false" width="800" height="950" frameborder="0"></iframe>
### Et ils sont beau ces fromages ?

Grâce à petite requête wikidata, on peut voir ces fameux fromage
```sparql
#defaultView:ImageGrid
PREFIX wd: <http://www.wikidata.org/entity/>
PREFIX wdt: <http://www.wikidata.org/prop/direct/>
PREFIX wikibase: <http://wikiba.se/ontology#>
PREFIX psv: <http://www.wikidata.org/prop/statement/value/>
PREFIX p: <http://www.wikidata.org/prop/>
PREFIX schema: <http://schema.org/>
SELECT distinct ?dept ?deptLabel ?fromage ?fromageLabel ?img WHERE {
 ?fromage wdt:P279 wd:Q2223649 .
 ?fromage wdt:P1071 ?dept .
 ?dept wdt:P31 wd:Q6465 .
 ?dept p:P625 ?loc .
 ?fromage wdt:P18 ?img .

 SERVICE wikibase:label {
 bd:serviceParam wikibase:language "fr" 
 }
}
```
<iframe style="width: 70vw; height: 4600vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3AImageGrid%0APREFIX%20wd%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fentity%2F%3E%0APREFIX%20wdt%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fprop%2Fdirect%2F%3E%0APREFIX%20wikibase%3A%20%3Chttp%3A%2F%2Fwikiba.se%2Fontology%23%3E%0APREFIX%20psv%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fprop%2Fstatement%2Fvalue%2F%3E%0APREFIX%20p%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fprop%2F%3E%0APREFIX%20schema%3A%20%3Chttp%3A%2F%2Fschema.org%2F%3E%0ASELECT%20distinct%20%3Fdept%20%3FdeptLabel%20%3Ffromage%20%3FfromageLabel%20%3Fimg%20WHERE%20%7B%0A%20%3Ffromage%20wdt%3AP279%20wd%3AQ2223649%20.%0A%20%3Ffromage%20wdt%3AP1071%20%3Fdept%20.%0A%20%3Fdept%20wdt%3AP31%20wd%3AQ6465%20.%0A%20%3Fdept%20p%3AP625%20%3Floc%20.%0A%20%3Ffromage%20wdt%3AP18%20%3Fimg%20.%0A%0A%20SERVICE%20wikibase%3Alabel%20%7B%0A%20bd%3AserviceParam%20wikibase%3Alanguage%20%22fr%22%20%0A%20%7D%0A%7D" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups" ></iframe>
