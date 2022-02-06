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



  --REPOSITORIO COMPLETO CON ELK
  https://github.com/deviantony/docker-elk





  -NOTAS
  Hola Luis.

Respecto a tu primera pregunta, sí que es posible activar este tipo de seguridad con Elasticsearch. Cuando grabé el curso, todas estas características requerían licencia, así que no pude añadirlas al curso. Desde hace unas versiones, todo esto ya se puede activar con la licencia básica. Si todo va bien, la semana que viene publicaré un video en el curso explicando cómo funciona este tipo de seguridad. Entre tanto, te paso un enlace donde explica eso (no podrás activar todas las funcionalidades, porque algunas siguen necesitando una licencia de pago, pero sí podrás activar lo que necesitas): https://www.elastic.co/guide/en/elasticsearch/reference/current/configuring-security.html

En cuanto a tu segunda pregunta, te dejo un enlace con lo que permite Kibana. Como en el caso anterior, algunas de estas funcionalidades requerirán licencia de pago: https://www.elastic.co/guide/en/kibana/7.6/kibana-privileges.html#kibana-feature-privileges

Un saludo, Alberto.