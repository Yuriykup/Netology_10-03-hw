# Домашнее задание к занятию «ELK»

### Задание 1. Elasticsearch 

Установите и запустите Elasticsearch, после чего поменяйте параметр cluster_name на случайный. 

*Приведите скриншот команды 'curl -X GET 'localhost:9200/_cluster/health?pretty', сделанной на сервере с установленным Elasticsearch. Где будет виден нестандартный cluster_name*.

---
### ОТВЕТ НА ЗАДАНИЕ 1.

![Скриншот-1](https://github.com/Yuriykup/Netology_10-03-hw/blob/main/img/img1.png)

---

### Задание 2. Kibana

Установите и запустите Kibana.

*Приведите скриншот интерфейса Kibana на странице http://<ip вашего сервера>:5601/app/dev_tools#/console, где будет выполнен запрос GET /_cluster/health?pretty*.

---
### ОТВЕТ НА ЗАДАНИЕ 2.
![Скриншот-2](https://github.com/Yuriykup/Netology_10-03-hw/blob/main/img/img2.png)

---
### Задание 3. Logstash

Установите и запустите Logstash и Nginx. С помощью Logstash отправьте access-лог Nginx в Elasticsearch. 

*Приведите скриншот интерфейса Kibana, на котором видны логи Nginx.*

---
### ОТВЕТ НА ЗАДАНИЕ 3. НУЖНА ПОМОЩЬ!!!

#### На этапе выполнения задания №3 не могу отправить запросы в Logstash и просмотреть их в Kibana!

- Logstach запущен в Docer-compose 
- Порты проброшены.
![Скриншот-3](https://github.com/Yuriykup/Netology_10-03-hw/blob/main/img/img3.png)

- Сервер Nginx запущен.

![Скриншот-4](https://github.com/Yuriykup/Netology_10-03-hw/blob/main/img/img4.png)

- К Kibana доступ есть.

![Скриншот-5](https://github.com/Yuriykup/Netology_10-03-hw/blob/main/img/img5.png)

- В меню "Dev Tools" запросы обрабатываются

` GET /_cluster/health?pretty `
![Скриншот-6](https://github.com/Yuriykup/Netology_10-03-hw/blob/main/img/img6.png)

` GET /_cat/indices `
![Скриншот-7](https://github.com/Yuriykup/Netology_10-03-hw/blob/main/img/img7.png)

- В меню "Stack Managemet - Kibana/Index Patern" не могу выбрать ничего кроме `filebeat-%{[agent.version]}-2026.03.1`.
![Скриншот-8](https://github.com/Yuriykup/Netology_10-03-hw/blob/main/img/img8.png)

- В меню "Analytics/Discovery" при запросе в Logstash ничего не отбражается. В принципе ничего не отображается.
![Скриншот-8](https://github.com/Yuriykup/Netology_10-03-hw/blob/main/img/img9.png)

- Командой `echo '192.168.0.1 internal 500' | nc localhost 5044` пытался отправить принудительный запрос в Logstash, но в логах Logstash ничего не отображается.
![Скриншот-8](https://github.com/Yuriykup/Netology_10-03-hw/blob/main/img/img10.png)

#### Файлы:
- [Docker-compose.yml](configs/docker-compose.yml)
- [Config/Elastics](configs/elasticsearch/config.yml)
- [Config/Kibana](configs/kibana/configs.yml)
- [Config/Logstash](configs/logstash/piplines.yml)
- [Config/Nginx](configs/logstash/piplines/nginx.yml)
---

### Задание 4. Filebeat. ` НЕ ПРИСТУПАЛ ` 

Установите и запустите Filebeat. Переключите поставку логов Nginx с Logstash на Filebeat. 

*Приведите скриншот интерфейса Kibana, на котором видны логи Nginx, которые были отправлены через Filebeat.*
