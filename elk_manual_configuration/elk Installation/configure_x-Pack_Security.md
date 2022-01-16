# Configure X-Pack Security 

## 1. stop kibana

    sudo systemctl stop kibana

## 2. Stop elasticsearch 

    sudo systemctl stop elasticsearch

## 3. enable xpack in elasticsearch.yml

    sudo nano /etc/elasticsearch/elasticsearch.yml
    xpack.security.enabled: true

## 4. Setup default user passwords

    sudo systemctl start elasticsearch
    cd /usr/share/elasticsearch/bin
    sudo ./elasticsearch-setup-passwords auto


## System Passwwords 

### << Default user passwords go here >>



Changed password for user apm_system
PASSWORD apm_system = v36QtoSu8ATwwaYWCkrG

Changed password for user kibana_system
PASSWORD kibana_system = Er4aLuGEOSpn24j7tsu1

Changed password for user kibana
PASSWORD kibana = Er4aLuGEOSpn24j7tsu1

Changed password for user logstash_system
PASSWORD logstash_system = 6zWtKJEm2yNpiTNJ4QvD

Changed password for user beats_system
PASSWORD beats_system = t0fk31dO1pGNwSQlUi8z

Changed password for user remote_monitoring_user
PASSWORD remote_monitoring_user = hCwxqGoShJNoV524wrqK

Changed password for user elastic
PASSWORD elastic = R7nqEiPrj652b68frbwP

## 5. Add the default username in kibana
elasticsearch.username: "kibana"

elasticsearch.password: "new_password"



