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

  - TIPOS DE BEATS
    Auditbeat: para llevar registro y control de los eventos del kernel Linux, así como las modificaciones a los ficheros. Es capaz de retener los mensajes que no ha enviado en caso de no haber conexión con nuestro servidor ElasticSearch. Esta característica acompaña también a los demás productos de esta lista.
    Filebeat: a pesar de su nombre no se refiere a ficheros normales, sino a los registros o logs. Viene preparado para detectar y enviar lo relacionado con auditd, Apache, NGINX, System, MySQL y otros más, ya sea en máquinas reales o en contenedores como Docker. Tiene la opción de enviarlos, ya sea a ElasticSearch y/o Logstash, a los cuales aludimos al principio.

    Heartbeat: para saber si están en línea por medio de ping, pero en un concepto ampliado, no solo ICMP sino también TCP, y HTTP o TLS. También puede autenticar y pasar por cualquier proxy. Sí, en sentido estricto de la definición -que todos y todas conocemos- eso no es un servicio ping, pero lo bueno del software libre es que lo podemos programar como nosotros lo necesitemos. Entrega a ElasticSearch y/o Logstash.

    MetricBeat: Ya en otra oportunidad hablamos sobre las métricas que realmente importan y sabemos que son variopintas. Por ello, Metricbeat se encargará de recogerlas para nosotros por medio de dos componentes: los módulos («modules») y los juegos de métricas («metricsets»).

    Los módulos especifican el servicio sobre el cual se va a recolectar la métrica, cómo conectar a ese servicio y cada cuánto tiempo hacer la consulta. Como cada servicio puede devolver muchos valores, Metricbeat los agrupa en un juego de métricas en formato normalizado antes de enviarlos. Aun cuando no reciba una respuesta efectiva tras varios intentos, Metricbeat siempre nos devolverá un informe indicando el fallo.

    Metricbeat entregará todos los datos recogidos a nuestro servidor, el cual habremos instalado con la orden «sudo apt-get install elasticsearch logstash kibana» (en el caso de Debian y similares). Nótese que deberemos instalar también Kibana, una herramienta para graficar la información procesada, y es el equivalente a la consola de Pandora FMS.

    Packetbeat: también trabaja con ElasticSearch y/o Logstash y se encarga de capturar el tráfico de nuestra red, determinar el protocolo utilizado y relacionar solicitudes y respuestas, para luego extraer campos tales como tiempo y estado, para agruparlos en formato adecuado antes de enviarlos. Funciona además como librería, así que nuestros programas en lenguaje Go tendrán una excelente herramienta o podremos crear nuestros propios detectores de protocolos (ya tiene integrado para detectar el tráfico de bases de datos como MySQL, PostgreSQL , MongoDB y más).
    Winlogbeat: es análogo a Filebeat, pero aplicado única y exclusivamente a todos los eventos del sistema operativo Windows®.


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


--TOOL LOG GENERATOR
java -jar log-generator-1.0.jar -l -20 d 10

--MONTAR DOCKER COMPOSE SQL SERVER EN LINUX
  https://aspnetcoremaster.com/slqserver/docker-compose-para-sql-server.html


--Diferentes videos sobre logstash
https://www.youtube.com/watch?v=_x26AMwAetQ  

--Cómo mantener Elasticsearch sincronizado con una base de datos relacional usando Logstash y JDBC
  https://www.elastic.co/es/blog/how-to-keep-elasticsearch-synchronized-with-a-relational-database-using-logstash