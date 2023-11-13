# Hadoop-Hive-Spark кластер + Jupyter в Docker

## Компоненты

* [Hadoop 3.3.4](https://hadoop.apache.org/)

* [Hive 3.1.3](http://hive.apache.org/)

* [Spark 3.3.1](https://spark.apache.org/)

## Старт

Для запуска кластера необходимо последовательно выполнить команды:
```
make
docker-compose up
```

## Сервисы доступны по следующим ссылкам:

### Hadoop

ResourceManager: http://localhost:8088

NameNode: http://localhost:9870

HistoryServer: http://localhost:19888

Datanode1: http://localhost:9864
Datanode2: http://localhost:9865

NodeManager1: http://localhost:8042
NodeManager2: http://localhost:8043

### Spark
master: http://localhost:8080

worker1: http://localhost:8081
worker2: http://localhost:8082

history: http://localhost:18080

### Hive
URI: jdbc:hive2://localhost:10000

### Jupyter Notebook
URL: http://localhost:8888

Пример: [jupyter/notebook/pyspark.ipynb](jupyter/notebook/pyspark.ipynb)

За основу взят исходный код этого репозитория:\
https://github.com/shailendra-repo/Pyspark-hadoop-hive-docker

Изменения:
1. Вырезан dev образ из-за проблем с библиотекой tensorflow на платформе AMD.
2. Отключена поддержка GPU (также для корректного запуска на AMD).
3. Отключена проверка загружаемого spark образа.
4. Удален volume для jupyter notebook. 