版本，ELK版本中会存在版本不兼容的问题，所以最好使用别人做过的，或者按照我的来做

elasticsearch-5.3.1.tar.gz
kibana-5.3.1-linux-x86_64.tar.gz
logstash-6.6.1.tar.gz

jdk-8u141-linux-x64.tar.gz

kafka_2.11-2.1.1.tar
zookeeper-3.4.10.tar.gz

filebeat version 6.5.1  收集日志

安装

基本全部都是解压之后，然后放到指定目录下即可，不需要变异

环境变量

export JAVA_HOME=/usr/local/java
export ZK_HOME=/usr/local/zookeeper
export KAFKA_HOME=/usr/local/kafka
export CLASSPATH=.:$JAVA_HOME/jre/lib/rt.jar:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
export PATH=$PATH:$JAVA_HOME/bin:$ZK_HOME/bin:$KAFKA_HOME/bin
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/lib

重要的主要是配置文件中
## 自己详细写配置文件，然后放链接在这里
kafka的配置文件
broker.id=1
num.network.threads=3
num.io.threads=8
socket.send.buffer.bytes=10240000
socket.receive.buffer.bytes=10240000
socket.request.max.bytes=1048576000
message.max.bytes=100000000
queued.max.requests=1000
log.dirs=/data/kafka/kafkalogs
num.partitions=3
num.recovery.threads.per.data.dir=1
offsets.topic.replication.factor=1
transaction.state.log.replication.factor=1
transaction.state.log.min.isr=1
log.retention.hours=168
log.segment.bytes=1073741824
log.retention.check.interval.ms=300000
zookeeper.connect=172.31.120.20:2181
zookeeper.connection.timeout.ms=6000
group.initial.rebalance.delay.ms=0
advertised.port=9092
advertised.host.name=172.31.120.20
port=9092















