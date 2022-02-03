# CUROS-ELK

- Beats: Recolección de logs / cualquier tipo no solo logs
- Logstash: Tratamiento de logs / Tambien puede recolectarla.
- Elastisearch: Almacenamiento / Indexación  y procesamiento
- Kibano: display/consulta / Explotación de dadtos.

Cada herramienta enn producción suelen correr en maquinas diferentes.
Por ejemplo cada "Beat" correra en las maquinas que generan los logs.
Una o varias maquinas con Logstash a cuales les llegan los logs para procesarlos.
Un cluser de Elastisearch con distintos nodos para almacer y responder  a las consultas que se le hagan
Una o varias maquinas con kibana 


docker run -d^
  --name=metricbeat^
  --user=root^
  --volume="C:\DEVLAB\CURSOS_UDEMY\CUROS-ELK\beatmetricbeat.docker.yml:/usr/share/metricbeat/metricbeat.yml:ro"^
  docker.elastic.co/beats/metricbeat:7.17.0 metricbeat -e^
  -E output.elasticsearch.hosts=["9200"]


  --volume="$(pwd)/metricbeat.docker.yml:/usr/share/metricbeat/metricbeat.yml:ro" \
  --volume ./beat/:/usr/share/metricbeat/metricbeat.yml:ro^
  --volume ./beat/metricbeat.yml::/usr/share/metricbeat/metricbeat.yml
  --volume %cd%/:/opt -w /opt michaelbrooks/node npm i vuepress
  --volume /beat/:/etc/^