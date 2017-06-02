High available container
==========
Example showing high availability in docker-compose network using Keepalived (VRRP protocol)

### Setup two hosts
After running these commands ip address 172.20.0.66 will be shared between Host A (172.20.0.2) and Host B (172.20.0.3). 
You can check that Host A has higher VRRP priority by visiting http://172.20.0.66
```
docker network create --subnet 172.20.0.0/24 ha-container-network
docker-compose -f host-a/docker-compose.yml up -d
docker-compose -f host-b/docker-compose.yml up -d
```

### Setup failure for one of them
After running this command Host A will be unavailable and Host B will get its role.
You can try visiting http://172.20.0.66 again
```
docker-compose -f host-a/docker-compose.yml down
```
