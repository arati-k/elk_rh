# Installation and Configuration of ElasticSearch
# https://gitlab.com/LabIT/elasticsearch.git
# Pre-requisites 

## Download ZIP
    https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.16.3-windows-x86_64.zip
    https://artifacts.elastic.co/downloads/kibana/kibana-7.16.3-windows-x86_64.zip

    
## Run elasticsearch from command line
    .\bin\elasticsearch.bat

    touch /etc/yum.repos.d/elasticsearch.repo
    touch /etc/yum.repos.d/kibana.repo
    touch /etc/yum.repos.d/logstash.repo

    ### Add the following to elasticsearch.repo
    [elasticsearch]
    name=Elasticsearch repository for 7.x packages
    baseurl=https://artifacts.elastic.co/packages/7.x/yum
    gpgcheck=1
    gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch
    enabled=0
    autorefresh=1
    type=rpm-md

    ### Add the following to kibana.repo
    [kibana-7.x]
    name=Kibana repository for 7.x packages
    baseurl=https://artifacts.elastic.co/packages/7.x/yum
    gpgcheck=1
    gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch
    enabled=1
    autorefresh=1
    type=rpm-md

    ### Add the following to Kibana.repo
    [logstash-7.x]
    name=Elastic repository for 7.x packages
    baseurl=https://artifacts.elastic.co/packages/7.x/yum
    gpgcheck=1
    gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch
    enabled=1
    autorefresh=1
    type=rpm-md


## Install elasticsearch 
    sudo yum install --enablerepo=elasticsearch elasticsearch
    

## Install Kibana   
    sudo yum install kibana

## Install logstash
    sudo yum install logstash


## 5. configure elasticsearch

    sudo su
    nano /etc/elasticsearch/elasticsearch.yml

    change cluster name
    cluster.name: demo-elk  

    give the cluster a descriptive name
    node.name: elk-1 

    change network binding
    network.host: 0.0.0.0  

    setup discovery.type as single node
    discovery.type: single-node

## 6. Start Elasticsearch service

    sudo systemctl start elasticsearch

## 7. validate Elasticsearch cluster health

    curl -XGET http://localhost:9200/_cluster/health?pretty

## 8. configure kibana
    
    nano /etc/kibana/kibana.yml

    uncomment server.port
    server.port: 5601

    server base url however this needs to be corrected everytime you start and stop the server
    server.publicBaseUrl: "http://192.168.1.3:5601/"

    change server.host
    server.host: "0.0.0.0"
    
    change server.name
    server.name: "demo-kibana"
    
    uncomment elasticsearch.host
    elasticsearch.hosts: ["http://localhost:9200"]
    
## 9. start Kibana service

    systemctl start kibana
    
## 10. enable elasticsearch and kibana

    systemctl enable elasticsearch
    systemctl enable kibana
    
  