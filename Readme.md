download the Kafka server from offical site
  https://kafka.apache.org/downloads

Go to bin directory
/home/nishant/Downloads/kafka_2.12-3.9.0/bin

### Start the Zookeeper-server [default running port is 2181]
    Run the below Command to start the zookeeper server :
      kafka_2.12-3.9.0/bin/zookeeper-server-start.sh kafka_2.12-3.9.0/config/zookeeper.properties

### Start Kafka-Server[default running port is 9092]
    Run the below Command to start the Kafka Server :
      kafka_2.12-3.9.0/bin/kafka-server-start.sh kafka_2.12-3.9.0/config/server.properties

### Create a topic in Kafka-Server
    Run the below command to create a topic
      kafka_2.12-3.9.0/bin/kafka-topic.sh bootstrap-server localhost:9092 --create --topic java-topic1 --partitions 3 replications-factor 1
      kafka_2.12-3.9.0/bin/kafka-topic.sh bootstrap-server localhost:9092 --create --topic java-topic2 --partitions 4 replications-factor 1
      kafka_2.12-3.9.0/bin/kafka-topic.sh bootstrap-server localhost:9092 --create --topic java-topic3 --partitions 5 replications-factor 1

### To View all the topic in particular server/broker
    Run the below command to views the topics on particular server
      kafka_2.12-3.9.0/bin/kafka-topic.sh bootstrap-server localhost:9092 --list 

### To describe the individual topic 
    Run the below command to describe the topic 
    kafka_2.12-3.9.0/bin/kafka-topic.sh --bootstrap-server localhost:9092 --describe --topic java-topic1

### Start the Produer 
    Run the below command to start the producer
      kafka_2.12-3.9.0/bin/kafka-console-producer.sh --broker-list localhost:9092 --topic java-topic1

### Start the Consumer 
    Run the below command to start the consumer
      kafka_2.12-3.9.0/bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic java-topic1 --from-beginning

# Confluent Kafka Community Edition in local
------------------------------------------------------------------------------------------------------------------
## Start Zookeeper Server
    Run the below Command to start the zookeeper server :
      bin/zookeeper-server-start etc/kafka/zookeeper.properties

## Start Kafka Server / Broker
    Run the below Command to start the Kafka server :
       bin/kafka-server-start etc/kafka/server.properties

## Create topic
    Run the below command to create a topic
      bin/kafka-topics --bootstrap-server localhost:9092 --create --topic NewTopic1 --partitions 3 --replication-factor 1

## List out all topic names
    Run the below command to views the topics on particular server
      bin/kafka-topics --bootstrap-server localhost:9092 --list

## Describe topics
    Run the below command to describe the topic 
      bin/kafka-topics --bootstrap-server localhost:9092 --describe --topic NewTopic1

## Produce message
    Run the below command to start the producer
      bin/kafka-console-producer --broker-list localhost:9092 --topic NewTopic1

## Consumer message
    Run the below command to start the consumer
      bin/kafka-console-consumer --bootstrap-server localhost:9092 --topic NewTopic1 --from-beginning 

## Send CSV File data to kafka
    Run the below command to start the producer
      bin/kafka-console-producer --broker-list localhost:9092 --topic NewTopic1 <bin/customers.csv
