# kafka-datagen

### To create topics:
```kafka-topics --bootstrap-server broker:9092 --topic TOPIC_NAME```

### To consume from topics:
```kafka-console-consume --bootstrap-server broker:9092 --topic TOPIC_NAME``` 
* add ```--from-begginning``` if you want all messages;
* add ```--property print.key=true`` if you want to print the keys.

### To manualy produce to topics:
```kafka-console-producer --bootstrap-server broker:9092 --topic TOPIC_NAME``` and then write your messages.

### To start generating orders:
```http POST http://localhost:8083/connectors @datagen-orders-config.json```
### To check the status:
```http http://localhost:8083/connectors/datagen-orders/status -b```
### To stop generating orders:
```http DELETE http://localhost:8083/connectors/datagen-orders -b```
