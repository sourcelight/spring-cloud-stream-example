# spring-cloud-stream-example-binder


Basically we're not tied anymore to the message broker leveraging on the spring-cloud-stream dependency 

![delegating-filter-proxy](./multiple_brokers.png)

It's just enough change dependencies from **spring-cloud-stream-binder-kafka** to another binder.

![delegating-filter-proxy](./binder-kafka-dependencies.png)

In the java classes **@EnableBinding(Source.class)** stands for the publisher and **@EnableBinding(Sink.class)** for the consumer



###### Apache-Kafka Binary Distribution [Download](actual link: https://archive.apache.org/dist/kafka/2.3.1/kafka_2.11-2.3.1.tgz).

###### Start Zookeeper server
> zookeeper-server-start.bat <local_path>\config\zookeeper.properties

###### Start Kafka server 
> kafka-server-start.bat <local_path>\config\server.properties

###### Create Topic
> kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 -topic queue-test

###### List down all available topics
> kafka-topics.bat --list --zookeeper localhost:2181

###### Produce a message
> kafka-console-producer.bat --broker-list localhost:9092 --topic queue-test

###### Consume a message
> kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic queue-test


References: https://www.youtube.com/watch?v=1IgvFlyEPkY 
