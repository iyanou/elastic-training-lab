Dans ce TP, nous allons déployer 4 machines virtuelles en utilisant Vagrant. Suivez les instrucstions dans le document https://github.com/iyanou/elastic-training-lab/blob/main/TP%20-%20Monitoring%20des%20Logs%20Spring%20Boot%20avec%20ELK.pdf pour une bonne realisation de ce TP.

![image](https://github.com/user-attachments/assets/079d5532-46e9-4739-bede-99dc5081b278)

Un cluster Elasticsearch de 3 nœuds sera formé avec chaque nœud installé sur une machine virtuelle. 
Le cluster sera sécurisé et les nœuds auront des certificats. 
Sur la quatrième machine, on installera Kibana, Logstash et Filebeat. 
Le but du TP consiste à collecter des fichiers de logs d’une application Spring Boot avec Filebeat. 
Filebeat enverra les logs a Logstash qui se chargera de les formater avant de les envoyer à Elasticsearch. 

![image](https://github.com/user-attachments/assets/96511576-8a00-46e8-9d97-ade549c9e235)

Ensuite on fera une visualisation  sur Kibana qui indiquera en temps réel les différents types de logs reçus et les détails des logs d’erreur. 

![image](https://github.com/user-attachments/assets/6b2ba178-7f80-482e-9761-4b20e8ad5406)
![image](https://github.com/user-attachments/assets/8b9fa55d-1cc3-4dc6-b665-cce112126135)

