## Tarea 2:
### Crear un endpoint SPARQL para almacenar los datos RDF anteriores y realizar consultas SPARQL interesantes sobre dicho endpoint indicando los resultados obtenidos.

<p>1.- Se Instala Fuseki en equipo local http://localhost:3030</p>

<p>2.- Se carga Dataset RDF Turtle: "comunas.ttl"</p>

<p>3.- Se realiza la siguiente Query Sparql</p>

SPARQL
<pre>
prefix : &lt;http://example.org/>
prefix rdf: &lt;http://www.w3.org/1999/02/22-rdf-syntax-ns#>
prefix rdfs: &lt;http://www.w3.org/2000/01/rdf-schema#>
prefix schema: &lt;http://schema.org/>

SELECT  ?nombre_region ?nombre_provincia ?nombre_comuna WHERE {
  ?provincia schema:en_region ?region .
  ?region schema:name ?nombre_region .
  ?comuna schema:en_provincia ?provincia .
  ?provincia schema:name ?nombre_provincia .
  ?provincia schema:name "Santiago" .
  ?comuna a :comuna .
  ?comuna schema:name ?nombre_comuna
}
</pre>
