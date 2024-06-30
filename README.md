Open Search Configurations

Start command:
docker-compose -f dashboard-docker-compose.yml up


Common error messages:
max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144]

Solution: 
sysctl -w vm.max_map_count=262144
