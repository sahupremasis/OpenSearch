Open Search Configurations

Start command:
docker-compose -f dashboard-docker-compose.yml up


Common error messages:
max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144]

Solution: 
sysctl -w vm.max_map_count=262144



# Start standalone 

docker run -d -p 9200:9200 -p 9600:9600 -e "discovery.type=single-node" -e "OPENSEARCH_INITIAL_ADMIN_PASSWORD=Scope@248" opensearchproject/opensearch:latest

From <https://opensearch.org/docs/latest/install-and-configure/install-opensearch/docker/> 




docker pull opensearchproject/opensearch-dashboards:2

From <https://opensearch.org/docs/latest/install-and-configure/install-dashboards/docker/> 

docker run opensearchproject/opensearch-dashboards:2 -p 5601:5601 -e "OPENSEARCH_HOSTS=https://localhost:9200"  -e "OPENSEARCH_INITIAL_ADMIN_PASSWORD=Scope@248" 



docker run opensearchproject/opensearch-dashboards:2 -p 5601:5601 -e 'OPENSEARCH_HOSTS=["https://localhost:9200","https://localhost:9200"]'  -e "OPENSEARCH_INITIAL_ADMIN_PASSWORD=Scope@248"   (not working, need to fix)


# Common Errors
opensearch-node1       | [1]: max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144]

sysctl -w vm.max_map_count=262144

