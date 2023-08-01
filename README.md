# mti_web_semantica
Repositorio de archivos para entrega de tareas

## Fuente de datos y transformación a RDF
### Regiones, Provincias y Comunas de Chile
https://colab.research.google.com/drive/1h98O-QYeMRsBBsv8ibM0SzV1I74maZXh?usp=sharing#scrollTo=TKlKn_qe01BZ

## SPARQL 
### Listado de todas las comunas de la provincia de "Santiago"

PREFIX name: <http://example.org/name#>
PREFIX sc: <http://purl.org/science/owl/sciencecommons/>
prefix : <http://example.org/>
prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
prefix rdfs:<http://www.w3.org/2000/01/rdf-schema#>
prefix schema: <http://schema.org/>

SELECT  ?nombre_region ?nombre_provincia ?nombre_comuna WHERE {
  ?provincia schema:en_region ?region .
  ?region schema:name ?nombre_region .
  ?comuna schema:en_provincia ?provincia .
  ?provincia schema:name ?nombre_provincia .
  ?provincia schema:name "Santiago" .
  ?comuna a :comuna .
  ?comuna schema:name ?nombre_comuna
}
