goto ~/workdir
extract the kafka tar,
tar -xvf kafka_2.10-0.9.0.0.tar

goto ~/workdir/kafka_2.10-0.9.0.0

create the data & log directories for both zookeeper & Kafka

mkdir /tmp/zookeeper (if zookeeper is installed, create zoo.cfg file, having client port,
mkdir /tmp/kafka-logs ( this is the default name, logs name can be create in 

start zookeeper from kafka installation itself:
./bin/zookeeper-server-start.sh config/zookeeper.properties &

./bin/kafka-server-start.sh config/server.properties &


./bin/kafka-topics.sh --create --zookeeper localhost:2181 --partitions 1 --replication-factor 1 --topic lakkiTest

./bin/kafka-topics.sh --describe --zookeeper localhost:2181 --topic lakkiTest

./bin/kafka-console-producer.sh --broker-list localhost:9092 --topic lakkiTest

