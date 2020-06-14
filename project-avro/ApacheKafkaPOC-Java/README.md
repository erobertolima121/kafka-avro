# Apache Kafka Producer and Consumer which uses Avro Serialization written in Java.


Steps for execution and corresponding explanation:

1. Download Confluent Open Source from https://www.confluent.io/download/ (Tested on v5.0).
2. Extract it and inside the directory, run the following command: bin/confluent start
3. This will start Kafka, Schema Registry, Zookeeper etc.
4. Create Topic using the following command which has the name 'excel': bin/kafka-topics --create --zookeeper localhost:2181 \    --replication-factor 1 --partitions 1 --topic excel
5. Run MainP.java which is a Kafka Producer which writes a .csv file to the topic created.
6. Run MainC.java which is a Kafka Consumer which reads the data from the topic.
