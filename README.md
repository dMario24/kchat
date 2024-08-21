# kchat
- Python chat program using Apache Kafka

![kchat](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSXU0lEqTt92-OvzuYaFMV5za5weXUKnaB26Q&s) 

### Tested environment
```
- python 3.8.19
- kafka_2.13-3.8.0
- java -version
openjdk version "17.0.12" 2024-07-16
OpenJDK Runtime Environment (build 17.0.12+7-Ubuntu-1ubuntu222.04)
OpenJDK 64-Bit Server VM (build 17.0.12+7-Ubuntu-1ubuntu222.04, mixed mode, sharing)
```
### Run Kafka
```bash
$ cd $KAFKA_HOME
$ bin/zookeeper-server-start.sh config/zookeeper.properties
$ bin/kafka-server-start.sh config/server.properties
```
### How to use 
- Send chat messages
```bash
$ python src/kchat/kafka/pchat.py
채팅 프로그램 - 메시지 발신자
메시지를 입력하세요. (종료시 'exit' 입력)
YOU: 카프카를 이용해서 파이썬으로 채팅을 만들어야 합니다.
YOU: 놀라셨나요?
YOU: 그럼 이만
YOU: eXit
채팅 종료
```

- Receive chat messages
```bash
$ python src/kchat/kafka/cchat.py
채팅 프로그램 - 메시지 수신
메시지 대기 중 ...
```


### Test
#### KAFKA Producer
```bash
$ python src/kchat/kafka/pro.py
[DONE]: 0.029494762420654297
```

```bash
$ $KAFKA_HOME/bin/kafka-console-consumer.sh --topic topic1 --from-beginning --bootstrap-server localhost:9092

{"str": "value0"}
{"str": "value1"}
{"str": "value2"}
{"str": "value3"}
{"str": "value4"}
{"str": "value5"}
{"str": "value6"}
{"str": "value7"}
{"str": "value8"}
{"str": "value9"}
```
