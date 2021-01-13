### Le jeu de données 
Le jeu de données est disponible [ici](https://data.opendatasoft.com/explore/dataset/fromagescsv-fromagescsv%40public/information/?disjunctive.fromage)
<iframe src="https://data.opendatasoft.com/explore/embed/dataset/fromagescsv-fromagescsv@public/table/?disjunctive.fromage&static=false&datasetcard=false" width="900" height="450" frameborder="0"></iframe>

### Qui fait le plus de fromage ? Ou il fait froid ?

<iframe frameborder="0" width="900" height="600" src="https://data.opendatasoft.com/map/embed/carte_des_fromages/?&static=false&scrollWheelZoom=false"></iframe>

### De la Vache ou de la brebis ?

<iframe src="https://data.opendatasoft.com/chart/embed/?dataChart=eyJ0aW1lc2NhbGUiOiIiLCJxdWVyaWVzIjpbeyJjaGFydHMiOlt7ImFsaWduTW9udGgiOnRydWUsInR5cGUiOiJ0cmVlbWFwIiwiZnVuYyI6IkNPVU5UIiwic2NpZW50aWZpY0Rpc3BsYXkiOnRydWUsImNvbG9yIjoicmFuZ2UtY3VzdG9tIn1dLCJjb25maWciOnsiZGF0YXNldCI6ImZyb21hZ2VzY3N2LWZyb21hZ2VzY3N2QHB1YmxpYyIsIm9wdGlvbnMiOnt9fSwieEF4aXMiOiJsYWl0IiwibWF4cG9pbnRzIjoyMDAsInNvcnQiOiIiLCJzZXJpZXNCcmVha2Rvd24iOiIiLCJzZXJpZXNCcmVha2Rvd25UaW1lc2NhbGUiOiIifV0sImFsaWduTW9udGgiOnRydWUsImRpc3BsYXlMZWdlbmQiOnRydWV9&static=false&datasetcard=true" width="900" height="450" frameborder="0"></iframe>

### Et ils sont beau ces fromages ?

<iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#PREFIX%20wd%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fentity%2F%3E%0APREFIX%20wdt%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fprop%2Fdirect%2F%3E%0APREFIX%20wikibase%3A%20%3Chttp%3A%2F%2Fwikiba.se%2Fontology%23%3E%0APREFIX%20psv%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fprop%2Fstatement%2Fvalue%2F%3E%0APREFIX%20p%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fprop%2F%3E%0APREFIX%20schema%3A%20%3Chttp%3A%2F%2Fschema.org%2F%3E%0ASELECT%20distinct%20%3Fdept%20%3FdeptLabel%20%3Flat%20%3Flon%20%3Ffromage%20%3FfromageLabel%20%3Farticle%20%3Fimg%20WHERE%20%7B%0A%20%3Ffromage%20wdt%3AP279%20wd%3AQ2223649%20.%0A%20%3Ffromage%20wdt%3AP1071%20%3Fdept%20.%0A%20%3Fdept%20wdt%3AP31%20wd%3AQ6465%20.%0A%20%3Fdept%20p%3AP625%20%3Floc%20.%0A%20%3Floc%20psv%3AP625%20%3Fcoord%20.%0A%20%3Fcoord%20wikibase%3AgeoLatitude%20%3Flat%20.%0A%20%3Fcoord%20wikibase%3AgeoLongitude%20%3Flon%20.%0A%20%3Ffromage%20wdt%3AP18%20%3Fimg%20.%0A%20OPTIONAL%20%7B%0A%20%3Farticle%20schema%3Aabout%20%3Ffromage%20.%0A%20%3Farticle%20schema%3AinLanguage%20%22fr%22%20.%0A%20FILTER%20(SUBSTR(str(%3Farticle)%2C%201%2C%2025)%20%3D%20%22https%3A%2F%2Ffr.wikipedia.org%2F%22)%0A%20%7D%0A%20%0A%20SERVICE%20wikibase%3Alabel%20%7B%0A%20bd%3AserviceParam%20wikibase%3Alanguage%20%22fr%22%20%0A%20%7D%0A%7D%0AORDER%20BY%20%3FdeptLabel%20" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups"></iframe>
