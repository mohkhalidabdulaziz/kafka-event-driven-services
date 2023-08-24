# Kafka setup with docker
The following instructions as part of building this project:

* run 'docker-compose up' command to spin up the broker with docker container
* Run from the Command Line
  docker-compose up -d ./mvnw spring-boot:run 


### Docker commands:
#### Create a Topic: 
docker exec broker \
kafka-topics --bootstrap-server broker:9092 \
--create \
--topic "customer.visit"

#### Command Line Consumer

docker exec --interactive --tty broker \
kafka-console-consumer --bootstrap-server broker:9092 \
--topic "customer.visit" \
--from-beginning


#### Command Line Producer

docker exec --interactive --tty broker \
kafka-console-consumer --bootstrap-server broker:9092 \
--topic "customer.visit" \
--from-beginning


### Jackson Dependencies

In order to use Jackson and the module for Java8 DateTimes, use the following dependencies:
<dependency>
<groupId>com.fasterxml.jackson.core</groupId>
<artifactId>jackson-databind</artifactId>
</dependency>
<dependency>
<groupId>com.fasterxml.jackson.datatype</groupId>
<artifactId>jackson-datatype-jsr310</artifactId>
</dependency>

