Streamlit app Docker Image

1. Login with your AWS console and launch an EC2 instance
2. Run the following commands
 
Note: Do the port mapping to this port:- 8501

sudo apt-get update -y

sudo apt-get upgrade

#Install Docker

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker

#To clone from Github Repository 

git clone https://github.com/Divya196/Streamlit-App-Docker-Image.git

#Building Docker Image

docker build -t divyaramesh196/stapp:latest . 

#Listing the docker images present

docker images -a  

#After executing the below command,we can use Public IPv4 address to run the application 

docker run -d -p 8501:8501 divyaramesh196/stapp 

docker ps #get the container_id 

docker stop "container_id" 

#Removing the docker images

docker rm $(docker ps -a -q)

#Login into docker hub and pushing the docker image,later we can pull the image from docker hub.

docker login 

docker push divyaramesh196/stapp:latest 

docker rmi divyaramesh196/stapp:latest

docker pull divyaramesh196/stapp
