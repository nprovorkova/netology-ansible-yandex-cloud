### 8.3 Использование Yandex Cloud - Наталия Проворкова
#### Kibana
###### 1. Допишите playbook: нужно сделать ещё один play, который устанавливает и настраивает kibana.
###### 2. При создании tasks рекомендую использовать модули: `get_url`, `template`, `yum`, `apt`.
###### 3. Tasks должны: скачать нужной версии дистрибутив, выполнить распаковку в выбранную директорию, сгенерировать конфигурацию с параметрами.
###### 4. Приготовьте свой собственный inventory файл `prod.yml`.
#### 5. Запустите `ansible-lint site.yml` и исправьте ошибки, если они есть.
![kibana_5](imgs/kibana_5.png)
#### 6. Попробуйте запустить playbook на этом окружении с флагом `--check`.
ansible-playbook -i inventory/prod site.yml --check
![kibana_6](imgs/kibana_6.png)
#### 7. Запустите playbook на `prod.yml` окружении с флагом `--diff`. Убедитесь, что изменения на системе произведены.
ansible-playbook -i inventory/prod site.yml --diff
![kibana_7_1](imgs/kibana_7_0.png)
![kibana_7_1](imgs/kibana_7_1.png)
![kibana_7_2](imgs/kibana_7_2.png)
![kibana_7_3](imgs/kibana_7_3.png)
![kibana_7_4](imgs/kibana_7_4.png)
![kibana_7_5](imgs/kibana_7_5.png)
![kibana_7_6_1](imgs/kibana_7_6_1.png)
Доступность Elasticsearch:
![elastic_available](imgs/elastic_available.png)
Доступность Kibana:
![kibana_available](imgs/kibana_available.png)
#### 8. Повторно запустите playbook с флагом `--diff` и убедитесь, что playbook идемпотентен.
![kibana_8](imgs/kibana_8.png)
###### 9. Проделайте шаги с 1 до 8 для создания ещё одного play, который устанавливает и настраивает filebeat.
#### Filebeat
###### 1. Допишите playbook: нужно сделать ещё один play, который устанавливает и настраивает kibana.
###### 2. При создании tasks рекомендую использовать модули: `get_url`, `template`, `yum`, `apt`.
###### 3. Tasks должны: скачать нужной версии дистрибутив, выполнить распаковку в выбранную директорию, сгенерировать конфигурацию с параметрами.
###### 4. Приготовьте свой собственный inventory файл `prod.yml`.
#### 5. Запустите `ansible-lint site.yml` и исправьте ошибки, если они есть.
![filebeat_5](imgs/filebeat_5.png)
#### 6. Попробуйте запустить playbook на этом окружении с флагом `--check`.
![filebeat_6_1](imgs/filebeat_6_1.png)
![filebeat_6_2](imgs/filebeat_6_2.png)
#### 7. Запустите playbook на `prod.yml` окружении с флагом `--diff`. Убедитесь, что изменения на системе произведены.
![filebeat_7_1](imgs/filebeat_6_1.png)
![filebeat_7_2](imgs/filebeat_6_2.png)
Доступность Filebeat:
![filebeat_available](imgs/filebeat_available.png)
#### 8. Повторно запустите playbook с флагом `--diff` и убедитесь, что playbook идемпотентен.
![filebeat_8_1](imgs/filebeat_8_1.png)
![filebeat_8_2](imgs/filebeat_8_2.png)
#### 10. Подготовьте README.md файл по своему playbook. В нём должно быть описано: что делает playbook, какие у него есть параметры и теги.\
Playbook
1. Устанавливает Elasticsearch:
* Скачивает Elasticsearch
* Устанавливает Elasticsearch
* Экспортирует переменные окружения Elasticsearch из шаблона
2. Устанавливает Kibana:
* Скачивает Kibana
* Устанавливает Kibana
* Экспортирует переменные окружения Kibana из шаблона
3. Устанавливает Filebeat:
* Скачивает Filebeat
* Устанавливает Filebeat
* Экспортирует переменные окружения Filebeat из шаблона
* Запускает Filebeat

Параметры Playbook:
* elk_stack_version