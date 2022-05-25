# kafka-datagen

### To create topics:
```kafka-topics --bootstrap-server broker:9092 --topic TOPIC_NAME```

### To consume from topics:
```kafka-console-consume --bootstrap-server broker:9092 --topic TOPIC_NAME```  add ```--from-begginning``` if you want all messages.

### To produce to topics:
```kafka-console-producer --bootstrap-server broker:9092 --topic TOPIC_NAME``` and then write your messages.