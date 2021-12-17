# Installation and Configuration of ElasticSearch
# https://gitlab.com/LabIT/elasticsearch.git


# Manual ElK Stack Installation steps

## 1. Download and install public signing key 

    wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -

## 2. Install apt-transport-https package

    sudo apt-get install apt-transport-https -y

## 3. Save directory definitions

    echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-7.x.list


## 4. Update and Install elasticsearch

    sudo apt-get update && sudo apt-get install logstash

## 5. Changing the permissions on data folder

    chmod 777 /usr/share/logstash/data

## 6. stashing first event

   ./logstash -e 'input { stdin { } } output { stdout {} }'

