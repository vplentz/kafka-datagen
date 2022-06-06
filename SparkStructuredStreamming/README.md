# This directory has PySpark Structured Streamming Notebooks using the Kafka Datagen infraestructure
Each Notebook is used to understand how operations works.

## PageviewsGroupByTransform
This notebook consumes data from pageviews topic, groups it by userid and send it back to a topic called user_pageview_stats.

The purpose besides is to understand/test grouping streamming data, output modes and starting_offsets.

### To run it:
* Start kafka infraestructure with ```docker-compose up```;
    * Keep checking the logs to verify if topics were created - the init-kafka container should have exited;
* Start to generate data with ```http POST http://localhost:8083/connectors @datagen-pageviews-config.json```;
* Start pyspark docker and access the jupyter-notebook with ```docker run -p 8888:8888 --network='host' -v ${PWD}:/home/jovyan/work jupyter/pyspark-notebook```
* Run the notebook (and change variables as you wish);
    * To debug streamming operations, check the docker log from this container;
* Check the outputs in the topic doing:
    * Get into the broker ```docker exec -it broker bash```
    * Consume data from topic ```kafka-console-consumer --bootstrap-server broker:9092 --topic user_page_view_stats --from-beginning --property print.key=true```
### To stop it (removing topics data)
* From the project root run ```docker-compose down```

