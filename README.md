# Simple KAFKA uses in python and docker

To start we need to get required lib:

- Install the kafka lib in your venv. Also visit https://pypi.org/project/kafka-python/ for docs.
  ```
  >>> pip install kafka-python
  ```
- Pull the zookeeper and kafka images from docker hub. Visit https://hub.docker.com/r/bitnami/kafka and https://hub.docker.com/r/bitnami/zookeeper for documentation.

  >>> docker pull bitnami/zookeeper:3.8.1

  >>> docker pull bitnami/kafka:3.4.0

# How to RUN this project.

1. Run the kafka.yaml file using docker-compose.

   >>> docker-compose -f kafka.yaml up

2. After successfully running kafka.yaml file, open new terminal and start the messageConsumer.py file to start the message listening. We need to run messageConsumer.py before the messageProducer else there may be data loss.

   >>> python messageProducer.py

3. In another terminal we need to listen to the messageProducer.py to receive the messages.

   >>> python messageConsumer.py

After that we can see the output as below:

## messageProducer.py

    Message sent 1
    Message sent 2
    Message sent 3
    Message sent 4
    Message sent 5
    Message sent 6
    Message sent 7
    Message sent 8
    Message sent 9
    Message sent 10

## messageConsumer.py

    Starting the message queue
    Message 11:24:54.213386
    Message 11:24:56.215629
    Message 11:24:58.219172
    Message 11:25:00.221930
    Message 11:25:02.223259
    Message 11:25:04.242546
    Message 11:25:06.260914
    Message 11:25:08.269712
    Message 11:25:10.281718
    Message 11:25:12.292985
