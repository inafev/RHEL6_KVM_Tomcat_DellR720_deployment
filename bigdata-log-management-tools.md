
LOGSTASH, altenativa a otras Big Data Log Management Tools como Splunk,XpoLog, GrayLog2,fluentd, etc. Imprescindible para diagnosticar eficazmente muchos de los problemas de Infraestructura/Operaciones: 
http://www.elasticsearch.org/overview/logstash/

Se complementa bien con otra herramienta popular más enfocada a las métricas en tiempo real: Graphite + Highcharts. Por ejemplo, Graphite puede ser utilizado en los reportes como 'salida' de logstash. Recientemente he participado en proyectos de Gestión de Infraestructura WebApp donde se parsean logs de sistema y WebApp con scripts bash, enviando métricas/datos a Graphite+Highcharts. Esta 'tendencia' es plausible, pero no deja de ser una solución de código scripting lento y poco escalable (parseo de logs tradicional) en comparación a soluciones como Logstash+Kibana (no requiere código).

Kibana, también de elasticsearch.org, es el generador de reportes visuales para el análisis de datos (Big Data's Dashboard).

Logstash Presentation https://www.youtube.com/watch?v=U3m0jKygAqU

Using elasticsearch, logstash and kibana to create realtime dashboards (slides) https://speakerdeck.com/elasticsearch/using-elasticsearch-logstash-and-kibana-to-create-realtime-dashboards

Jordan Sissel - PuppetConf 2013 https://www.youtube.com/watch?v=fwMnb4-t8vo

Otras herramientas similares que permite al equipo de Operaciones analizar la causa raíz de una crisis en la infraestructura, ayudando también al equipo DevOps a analizar y diagnosticar fácilmente los incidentes en producción y desarrollo.
http://www.ravellosystems.com/blog/choosing-central-logging-tool-5-features-6-tools
