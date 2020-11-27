# monitoring-dse-nosqlbench

monitoring both dse and nosqlbench

# Install guide

edit prometheus/tg\_dse.json:

replace node1, node..., nodeN by IP address list of your DSE cluster nodes

check DSE has prometheus export activated

Run:
```
docker-compose up -d
```
wait until grafana is available (http://localhost:3000/)
then:
```
curl -ik -X POST -H "Content-Type:application/json;charset=UTF-8" --data-binary '@new-nb-dashboard.json' --user admin:admin "http://localhost:3000/api/dashboards/db"
```
