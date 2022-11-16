![Alt text](reverse-proxy-1.png?raw=true "Title")

#follow insctruction this article in order to build and run the project

https://achrafbenalaya.com/2022/11/16/how-to-setup-nginx-reverse-proxy-for-aspnet-core-apps-with-and-without-docker-compose/

#used cmd

docker build -t backend  .

docker build -t frontend  .


#create network
docker network create demonetwork-001;

docker run -it --rm -p 5000:5000 --network=demonetwork-001  --name backend backend
docker run -it --rm -p 8082:80  --network=demonetwork-001  --name frontend frontend