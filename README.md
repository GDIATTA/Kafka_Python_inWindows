# Kafka_Python_inWindows
#### Install and run Apache Kafka & Integration with Python using Kafka-Python
-- Firstime, I need to go the website to download Kafka and then extract the file from zip ://
https://Kafka.apache.org/downloads

-- I need to create 2 folders in my C drive-- :
Kafka_logs--zookeeper
kafka_logs--server_logs

-- I need to go a folder from config/zookeeper.properties to change some properties :

dataDir=C:/kafka_logs/zookeeper
maxClientCnxns=1

-- I need also to go a folder from config/server to change a little bit :

uncomment listeners
log.dirs=C:/kafka_logs/server_logs
zookeeper.connect=localhost:2181
zookeeper.connection.timeout.ms=60000

--I need to start Zookeeper(Recommande: Try to make sure java is installed before):
C:/kafka_2.12-3.7.0/bin/windows/zookeeper-server-start.bat C:/kafka_2.12-3.7.0/config/zookeeper.properties


--I need to start Kafka-server :
C:/kafka_2.12-3.7.0/bin/windows/kafka-server-start.bat C:/kafka_2.12-3.7.0/config/server.properties

--I need to create topic:
C:/kafka_2.12-3.7.0/bin/windows/kafka-topics.bat --create --topic hello_world --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1

--I need to start Producer:
C:/kafka_2.12-3.7.0/bin/windows/kafka-console-producer.bat --topic hello_world --bootstrap-server localhost:9092

--I need to start Consumer:
C:/kafka_2.12-3.7.0/bin/windows/kafka-console-consumer.bat --topic hello_world --from-beginning --bootstrap-server localhost:9092

pip install kafka-python
