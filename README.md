# kafka-datagen

### To create topics:
```kafka-topics --bootstrap-server broker:9092 --topic TOPIC_NAME```

### To consume from topics:
```kafka-console-consume --bootstrap-server broker:9092 --topic TOPIC_NAME```  add ```--from-begginning``` if you want all messages.

### To produce to topics:
```kafka-console-producer --bootstrap-server broker:9092 --topic TOPIC_NAME``` and then write your messages.

### To setup the Datagen Connector:
```
kafka-topics --bootstrap-server broker:9092 --create --topic orders-datagen
kafka-topics --bootstrap-server broker:9092 --create --config cleanup.policy=compact --topic connect-configs
kafka-topics --bootstrap-server broker:9092 --create --config cleanup.policy=compact --topic connect-status
kafka-topics --bootstrap-server broker:9092 --create --config cleanup.policy=compact --topic connect-offsets
```

### To start generating orders:
```http POST http://localhost:8083/connectors @datagen-orders-config.json```
### To check the status:
```http http://localhost:8083/connectors/datagen-orders/status -b```
### To stop generating orders:
```http DELETE http://localhost:8083/connectors/datagen-orders -b```