
# Kafka server
In this small project we see how to install the kafka server and zookeeper using Docker-compose.
It also contains a series of commands to create, list, consume and view detailed information about the topics.

## Execute Kafka
```bash
docker-compose up -d
````

## Try :

### Create topic:
```bash
docker exec -it <id-container-kafka> kafka-topics --create --topic test-topic --bootstrap-server localhost:9092 --partitions 1 --replication-factor 1
```


### List topics:

```
docker exec -it <id-container-kafka> kafka-topics --list --bootstrap-server localhost:9092
```



### Send message to topic:
```
docker exec -it <id-container-kafka> kafka-console-producer --topic test-topic --bootstrap-server localhost:9092

```

### Read messages of the topic 
```
docker exec -it <id-container-kafka> kafka-console-consumer --topic test-topic --from-beginning --bootstrap-server localhost:9092
```

### View information about a topic

```
kafka-topics --bootstrap-server localhost:9092 --describe --topic topic-test
```