# kafka-topics

Tasks


Task 1: Create Topics

1. Create two Ka fka topics:
   - practice-topic with 3 par  titions.
   - ```
     ./kafka-topics.sh --create --topic practice-topic --partitions 3 --bootstrap-server broker:29092
     ```
   - dead-letter-topic with 1 par  titions for handling failed messages.
   - ```
     ./kafka-topics.sh --create --topic dead-letter-topic --partitions 1 --bootstrap-server broker:29092
     ```
2. Verify the topics using the Ka fka CLI.
   - ```
     ./kafka-topics.sh --describe --topic practice-topic --bootstrap-server broker:29092
     ```
   Output: Topic: practice-topic	TopicId: EfgY42TiQIypn3kKONoZ-A	PartitionCount: 3	ReplicationFactor: 1	Configs: 
	         Topic: practice-topic	Partition: 0	Leader: 1	Replicas: 1	Isr: 1	Elr: 	LastKnownElr: 
	         Topic: practice-topic	Partition: 1	Leader: 1	Replicas: 1	Isr: 1	Elr: 	LastKnownElr: 
	         Topic: practice-topic	Partition: 2	Leader: 1	Replicas: 1	Isr: 1	Elr: 	LastKnownElr:


Task 2: Produce Messages

1. Write a producer script or use the CLI to send the following messages to practice-topic:
  Key-value pairs like:
  key1:Message for Partition 1
  key2:Message for Partition 2
  key3:Message for Partition 3

  Use keys to control par titi on assignment.


2. Observe which par  tition each message is sent to.
   Producer code or CLI commands.
   -
     ```
     - ./kafka-console-producer.sh \
     --topic practice-topic \
     --bootstrap-server broker:29092 \
     --property "parse.key=true" \
     --property "key.separator=:"
     ```
     
  Confirmati on of messages sent to respec tive parti  ons.
   -
     ```
      ./kafka-console-consumer.sh \
      --topic practice-topic \
      --bootstrap-server broker:29092 \
      --property print.key=true \
      --property key.separator=":" \
      --property print.partition=true
      --from-beginning

     ```








  


