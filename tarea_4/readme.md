## Tarea 4: 
### Realizar una comparación entre las respuestas que puedan obtenerse a partir de los datos anteriores mediante RDF, SPARQL y Wikidata, con las respuestas que se obtienen a través de ChatGPT. Para realizar este ejercicio se recomienda ver este vídeo

#### Opcional 4: Identificar  casos de alucinaciones de ChatGPT que pueden resolverse mejor mediante datos en Wikidata y realizar una justificación de las mismas.


<p>1.- una vez hecho la consulta realizada a endpoint de Tarea 2 para obtener las diversas comunas de Santiago de Chile</p>
<p>2.- Posteriormente se realiza la misma consulta, esta vez tomando en wikidata con objetivo de validar la información obtenida desde el endpoint creado. El resultado fue el mismo.</p>

<pre>
SELECT ?comuna ?comunaLabel
WHERE {
  wd:Q45632 wdt:P150 ?comuna. # Q45632 representa Santiago (Región Metropolitana de Santiago)
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
</pre>


<pre>
  SELECT (COUNT(?comuna) AS ?total_comunas)
WHERE {
  wd:Q45632 wdt:P150 ?comuna. # Q45632 representa Santiago (Región Metropolitana de Santiago)
}
</pre>

<p>
  Análisis:</p>
<p>
La experiencia realizada expone la complejidad de ChatGPT para trabajar con ciertas consultas y destaca las ventajas de utilizar datos grafos. Mientras que ChatGPT utiliza cantidades gigantescas de datos y recursos computacionales, mientras que RDF tiende a utilizar N veces menos la cantidad de recursos que utiliza ChatGPT. Además, los resultados mediante consultas a RDF son precisos, mientras que ChatGPT como se menciona en la comparación anterior, tiende a ser un muy buen adivinador.
Finalmente se concluye el análisis con la siguiente frase: “¿Qué es mejor, pagar poco por información correcta o pagar mucho por información probablemente correcta?”
</p>
