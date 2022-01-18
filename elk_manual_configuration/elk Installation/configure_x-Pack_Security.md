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
PASSWORD apm_system = BDL5I4xGAAzwRSpEYEUZ

Changed password for user kibana_system
PASSWORD kibana_system = dn77RMXqhIAzJNowrXtP

Changed password for user kibana
PASSWORD kibana = dn77RMXqhIAzJNowrXtP

Changed password for user logstash_system
PASSWORD logstash_system = UqlgxQ8kKcZ7klM3I6gZ

Changed password for user beats_system:
PASSWORD beats_system = ex2aYCBoj37oHlxa9Lcm

Changed password for user remote_monitoring_user
PASSWORD remote_monitoring_user = zR9fXVtlIAzqB6d6wLg8

Changed password for user elastic
PASSWORD elastic = QAQLo4ooJyGwGlAEwHF7

## 5. Add the default username in kibana
elasticsearch.username: "kibana"

elasticsearch.password: "new_password"



