# nexus-repository
first, you have to make network for nexus service. 
\\\\
docker network create --driver overlay nexus-network
\\\\


\\\\
docker service create --name nexus --network nexus-network -p 8081:8081 sonatype/nexus3:latest
\\\\

\\\\
And you have you connect volume to nexus service. 
login portrainer.
\\\\



