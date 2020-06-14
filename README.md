# kafka-avro
Projeto contem exemplo do uso de Kafka | Schema Registry | Avro | Docker | Producer | Consumer

- Git clone: https://github.com/erobertolima121/kafka-avro.git
- Acessar a pasta: 'confluent\cp-docker-images\examples\kafka-single-node' e execute o comando 'docker-compose up'.
- Abrir com sua IDE de preferência o projeto localizado na pasta 'project-avro\ApacheKafkaPOC-Java'
- Rodar o MainP.java (Run Java Application), será produzido mensagens no tópico 'excel' utilizando o avro schema a partir da massa de dados contida no arquivo 'C2ImportCalEventSample.csv'
- Rodar o MainC.java (Run Java Application), será consumido mensagens do tópico 'excel'

# apoio: comandos básicos do Kafka

- Criando um tópico chamado 'meu-topico-legal' no Kafka:
docker-compose exec kafka kafka-topics --create --topic meu-topico-legal --partitions 1 --replication-factor 1 --if-not-exists --zookeeper zookeeper:2181

- Verificando o tópico criado:
docker-compose exec kafka  \  kafka-topics --describe --topic meu-topico-legal --zookeeper zookeeper:2181

- Criando um producer:
docker-compose exec kafka bash -c "seq 100 | kafka-console-producer --request-required-acks 1 --broker-list localhost:9092 --topic meu-topico-legal && echo 'Produced 100 messages.'"

- Consumindo mensagem:
docker-compose exec kafka kafka-console-consumer --bootstrap-server localhost:9092 --topic meu-topico-legal --from-beginning --max-messages 100

# referências e agradecimentos

* https://github.com/confluentinc/cp-docker-images
* https://github.com/SharanRajani/ApacheKafkaPOC-Java
