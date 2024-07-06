
# Most used Kafka commands:
This file contains a summary of Kafka's most used commands.

## Index
- [Most used Kafka commands:](#most-used-kafka-commands)
  - [Index](#index)
- [Topic](#topic)
  - [Create topic:](#create-topic)
  - [List all topics:](#list-all-topics)
  - [Describing a topic (see details including partitions and replicas):](#describing-a-topic-see-details-including-partitions-and-replicas)
  - [Delete topic:](#delete-topic)
- [Producer and Consumer](#producer-and-consumer)
  - [Produce messages:](#produce-messages)
  - [Consuming messages:](#consuming-messages)
- [Consumer Groups:](#consumer-groups)
  - [List consumer groups:](#list-consumer-groups)
  - [Describe a consumer group (see details of offset, lag, etc.):](#describe-a-consumer-group-see-details-of-offset-lag-etc)
- [Administrative Operations:](#administrative-operations)
  - [Rebalancing a topic (splitting partitions between brokers):](#rebalancing-a-topic-splitting-partitions-between-brokers)
  - [Verify the integrity of the cluster:](#verify-the-integrity-of-the-cluster)
- [Utility tools:](#utility-tools)
  - [Verify the status of the cluster:](#verify-the-status-of-the-cluster)
  - [Control Center:](#control-center)
  - [Running an interactive Kafka console:](#running-an-interactive-kafka-console)


# Topic
## Create topic:
```
kafka-topics --bootstrap-server localhost:9092 --create --topic <nombre_del_topic> --partitions <número_de_particiones> --replication-factor <factor_de_replicación>
```

## List all topics:
```
kafka-topics --bootstrap-server localhost:9092 --list
```

## Describing a topic (see details including partitions and replicas):
```
kafka-topics --bootstrap-server localhost:9092 --describe --topic <nombre_del_topic>
```

## Delete topic:
```
kafka-topics --bootstrap-server localhost:9092 --delete --topic <nombre_del_topic>
```

# Producer and Consumer
## Produce messages:

```
kafka-console-producer --broker-list localhost:9092 --topic <nombre_del_topic>
```

## Consuming messages:
```
kafka-console-consumer --bootstrap-server localhost:9092 --topic <nombre_del_topic> [--from-beginning]
```
Optionally, "--from-beginning" to read from the beginning of the topic.


# Consumer Groups:
## List consumer groups:
```
kafka-consumer-groups --bootstrap-server localhost:9092 --list
```

## Describe a consumer group (see details of offset, lag, etc.):
```
kafka-consumer-groups --bootstrap-server localhost:9092 --describe --group <nombre_del_grupo>
```

# Administrative Operations:
## Rebalancing a topic (splitting partitions between brokers):
```
kafka-preferred-replica-election --bootstrap-server localhost:9092
```

## Verify the integrity of the cluster:
```
kafka-broker-api-versions --bootstrap-server localhost:9092
```

# Utility tools:

## Verify the status of the cluster:
```
kafka-topics --bootstrap-server localhost:9092 --describe
```

## Control Center:
```
confluent-control-center
```

## Running an interactive Kafka console:
```
kafka-console
```
