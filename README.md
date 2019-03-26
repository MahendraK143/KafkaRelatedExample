# KafkaRelatedExample
KafkaRelatedExample


Kafka
touch: /usr/local/Homebrew/.git/FETCH_HEAD: Permission denied
==> Installing dependencies for kafka: zookeeper
==> Installing kafka dependency: zookeeper
==> Downloading https://homebrew.bintray.com/bottles/zookeeper-3.4.13.high_sierra.bottle.tar.gz
######################################################################## 100.0%
==> Pouring zookeeper-3.4.13.high_sierra.bottle.tar.gz
==> Caveats
To have launchd start zookeeper now and restart at login:
  brew services start zookeeper
Or, if you don't want/need a background service you can just run:
  zkServer start
==> Summary
🍺  /usr/local/Cellar/zookeeper/3.4.13: 244 files, 33.4MB
==> Installing kafka
==> Downloading https://homebrew.bintray.com/bottles/kafka-2.1.1.high_sierra.bottle.tar.gz
######################################################################## 100.0%
==> Pouring kafka-2.1.1.high_sierra.bottle.tar.gz
==> Caveats
To have launchd start kafka now and restart at login:
  brew services start kafka
Or, if you don't want/need a background service you can just run:
  zookeeper-server-start /usr/local/etc/kafka/zookeeper.properties & kafka-server-start /usr/local/etc/kafka/server.properties
==> Summary
🍺  /usr/local/Cellar/kafka/2.1.1: 162 files, 52.7MB
==> `brew cleanup` has not been run in 30 days, running now...
Pruned 1 symbolic links and 1 directories from /usr/local
==> Caveats
==> zookeeper
To have launchd start zookeeper now and restart at login:
  brew services start zookeeper
Or, if you don't want/need a background service you can just run:
  zkServer start
==> kafka
To have launchd start kafka now and restart at login:
  brew services start kafka
Or, if you don't want/need a background service you can just run:
zookeeper-server-start /usr/local/etc/kafka/zookeeper.properties & kafka-server-start /usr/local/etc/kafka/server.properties
You can use jps command and check whether two Kafka processes are running as follows -
Jus




Install kafka/zookeeper and start servers
$ brew install kafka
$ brew install zookeeper
$ zkServer start
$ kafka-server-start /usr/local/etc/kafka/server.properties
Create a topic
$ kafka-topics --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
Update a topic
$ kafka-topics —alter --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
Or 
./bin/kafka-topics.sh --alter --zookeeper localhost:2181 --topic my-topic --partitions 3 
You can verify whether partitions have been increased by using describe command as follows - 
./bin/kafka-topics.sh --describe --zookeeper localhost:2181 --topic my-topic
Verify that topics have been created successfully using following command -
./bin/kafka-topics.sh --list --zookeeper localhost:2181
Send a message
$ kafka-console-producer --broker-list localhost:9092 --topic test
>HELLO Kafka
Receive a message
$ kafka-console-consumer --bootstrap-server localhost:9092 --topic test --from-beginning
HELLO Kafka

Best : https://www.allprogrammingtutorials.com/tutorials/storm-integration-with-kafka.php 
Ut https://www.youtube.com/watch?v=0mIEUibjtzk 
https://www.signifytechnology.com/blog/2018/06/stream-processing-with-spring-kafka-spark-and-cassandra-part-3-and-4 	
https://github.com/spember/spark-cass-spring-demo 
