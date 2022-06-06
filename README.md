# kafka-datagen
Repository for testing kafka transformations with kafka local infraestructure setup using Docker.

```
kakfa-datagen
|   docker-compose.yml -- Kafka Docker-compose Infraestructure (sets up the containers and creates the initial topics)
|   Dockerfile-KafkaConnect -- KafkaConnect Docker with Datagen Connector installed 
|   README.md -- :)
└───SparkStructuredStreamming -- Stream Processing Notebooks using PySpark Structured Streamming + Kafka
|   |PageviewsGroupByTransform.ipynb -- Notebook that consumes data from pageviews topic, groups it by userid and send it back to a topic called user_pageview_stats.
|   | README.md -- Instruction on how to run Notebooks
```

## Next Steps
* (WIP) Add PySpark Structured Stream Processing;
* (TODO) Add KSQL infraestructure;
* (TODO) Add KSQL streamming processing;
* (TODO) Add Kafka Streamming processing;