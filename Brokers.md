Rabbit-MQ & Kafka

Pour démarrer rabbit MQ avec docker :
1 - docker run -d --name rabbit -p 4369:4369 -p 5671:5671 -p 5672:5672 -p 15672:15672 rabbitmq:3.7.17-management

2 - docker container exec -it rabbit  rabbitmq-plugins enable rabbitmq_management (si vous avez pas telecharger management pour UI)

3 - docker container exec -it rabbit  rabbitmq-plugins enable rabbitmq_delayed_message_exchange ( to enable rabbitmq_delayed_message_exchange plugin)

Pour exporter la configuration du Rabbit MQ
curl -u guest:guest -X GET http://localhost:15672/api/definitions > rabbit-MQ.json


Pour importer la configuration Rabbit MQ
curl -u guest:guest -X POST -H "content-type:application/json" -d @rabbit-MQ.json http://localhost:15672/api/definitions

1 - docker run -d --name rabbit -p 4369:4369 -p 5671:5671 -p 5672:5672 -p 15672:15672 rabbitmq:3.7.17-management

Comme il est possible d'exporter et d'importer depuis l'UI en se connectent http://localhost:15672

un projet spring boot avec rabbit-MQ est en cours de developpement :)