# Installation and Configuration of ElasticSearch
# https://gitlab.com/LabIT/elasticsearch.git
# Pre-requisites 

## 1. Download software
    ### 1. Elasticsearch
    https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.16.3-windows-x86_64.zip
    ### 2. Kibana
    https://artifacts.elastic.co/downloads/kibana/kibana-7.16.3-windows-x86_64.zip
    ### 3. NSSM 
    https://nssm.cc/download
    ### 4. 7zip
    https://www.7-zip.org/download.html
    ### 5. Visual studio code
    https://code.visualstudio.com/download

## 2. Extract elasticsearch and kibana using 7zip

## 3. configure elasticsearch

    
    Open  elasticsearch/config/elasticsearch.yml in an editor

    change cluster name
    cluster.name: demo-elk  

    give the cluster a descriptive name
    node.name: elk-1 

    change network binding
    network.host: 0.0.0.0  

    setup discovery.type as single node
    discovery.type: single-node

## 4. Configure Kibana
    
    Open kibana/config/kibana.yml

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
    



    
## 5. Run elasticsearch from command line
    .\bin\elasticsearch-service.bat install

## 6. Start elasticsearch service 
    services.msc -> start service

    ### Test connectivity
    url -XGET "http://localhost:9200/_cluster/health?pretty


## 6. Install Kibana using NSSM
    cd nssm/win64/
    ./nssm install kibana

    ####Add Kibana service path from kibana/bin/kibana

    ###Start Kibana service from NSSM or services.msc
 
    ### Test connectivity
    http://10.0.2.15:5601 or http://localhost:5601





    
  