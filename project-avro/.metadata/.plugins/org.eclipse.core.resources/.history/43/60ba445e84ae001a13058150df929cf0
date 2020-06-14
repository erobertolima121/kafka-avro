package com.example;

import io.confluent.kafka.serializers.KafkaAvroDeserializer;
import org.apache.kafka.clients.consumer.ConsumerRecord;
import org.apache.kafka.clients.consumer.ConsumerRecords;
import org.apache.kafka.clients.consumer.KafkaConsumer;
import org.apache.kafka.common.serialization.IntegerDeserializer;

import java.util.Collections;
import java.util.Properties;

public class MainC {

    public static void main(String[] args) {
        Properties properties = new Properties();
        properties.setProperty("bootstrap.servers", "127.0.0.1:9092");
        properties.put("group.id", "customer-group1");
        properties.setProperty("key.deserializer", IntegerDeserializer.class.getName());
        properties.setProperty("value.deserializer", KafkaAvroDeserializer.class.getName());
        properties.setProperty("schema.registry.url", "http://127.0.0.1:8081");
        properties.setProperty("specific.avro.reader", "true");

        String topic = "excel";

        KafkaConsumer<Integer, User> kafkaConsumer = new KafkaConsumer<Integer, User>(properties);
        kafkaConsumer.subscribe(Collections.singleton(topic));
        System.out.println("Waiting for data...");

        while (true) {
            System.out.println("Polling");
            ConsumerRecords<Integer, User> records = kafkaConsumer.poll(1000);

            for (ConsumerRecord<Integer, User> record : records) {
                System.out.println("Key" + record.key());
                System.out.println(record.value());
            }

            kafkaConsumer.commitSync();
        }
    }
}
