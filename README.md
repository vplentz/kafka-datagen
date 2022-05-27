# kafka-datagen

### To create topics:
```kafka-topics --bootstrap-server broker:9092 --topic TOPIC_NAME```

### To consume from topics:
```kafka-console-consume --bootstrap-server broker:9092 --topic TOPIC_NAME```  add ```--from-begginning``` if you want all messages.

### To manualy produce to topics:
```kafka-console-producer --bootstrap-server broker:9092 --topic TOPIC_NAME``` and then write your messages.

### To start generating orders:
```http POST http://localhost:8083/connectors @datagen-orders-config.json```
### To check the status:
```http http://localhost:8083/connectors/datagen-orders/status -b```
### To stop generating orders:
```http DELETE http://localhost:8083/connectors/datagen-orders -b```


# NEXT STEPS:
- Add a schema registry and create a schema for each table;
- Add KSQL capability and stream process some data to a new topic;
- Create a Kafka Stream data processing job;
- Add Schemma evolution; 