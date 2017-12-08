
# make network
first, you have to make network for nexus service. (if you not use docker swarm, pass!) 
```
docker network create --driver overlay nexus-network
```


# service run
our company used docker swarm. so if you want to docker service, you have to change command. (e.g: docker run ~~ ) 
What is important here is that you have to bind volume to nexus service. I used glusterfs. 
```
docker service create --name nexus --network nexus-network --mount type=bind,src=/gluster-mount/nexus-data,dst=/nexus-data  -p 8081:8081 -p 12000:12000 -p 13000:13000 sonatype/nexus3:latest

```
nexus web port is 8081.
if you add repository, you have to open port when creating service. (so I opened extra 12000,13000 port)
