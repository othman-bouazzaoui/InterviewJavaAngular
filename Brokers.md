Rabbit-MQ & Kafka

Pour démarrer rabbit MQ avec docker :
1 - docker run -d --name rabbit -p 4369:4369 -p 5671:5671 -p 5672:5672 -p 15672:15672 rabbitmq:3.9.13

2 - docker container exec -it rabbit  rabbitmq-plugins enable rabbitmq_management