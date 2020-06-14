# kafka-avro
Projeto contem exemplo do uso de Kafka | Schema Registry | Avro | Docker | Producer | Consumer

- Git clone: https://github.com/erobertolima121/kafka-avro.git
- Acessar a pasta: 'confluent\cp-docker-images\examples\kafka-single-node' e execute o comando 'docker-compose up'.
- Abrir com sua IDE de preferência o projeto localizado na pasta 'project-avro\ApacheKafkaPOC-Java'
- Rodar o MainP.java, será produzido mensagens no tópico 'excel' utilizando o avro schema a partir da massa de dados contida no arquivo 'C2ImportCalEventSample.csv'
- Rodar o MainC.java, será consumido mensagens do tópico 'excel'

# referências e agradecimentos

* https://github.com/confluentinc/cp-docker-images
* https://github.com/SharanRajani/ApacheKafkaPOC-Java
