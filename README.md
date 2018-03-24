To run this example:

0. Build the project with `mvn package`, this will generate an word-count-jar with the streams app and all its dependencies.
1. Create a kafka-word-count-input topic:

    `bin/kafka-topics.sh --zookeeper localhost:2181 --create --topic kafka-word-count-input --partitions 1 --replication-factor 1`

2. Produce some text to the topic. 

   `bin/kafka-console-producer.sh --broker-list localhost:9092 --topic kafka-word-count-input`

3. Run the app:

    `java -cp target/kafka-word-count-test-1.0-SNAPSHOT.jar com.godpan.WordCount`

4. Take a look at the results:

    `bin/kafka-console-consumer.sh --topic kafka-word-count-output --from-beginning --bootstrap-server localhost:9092  --property print.key=true`





