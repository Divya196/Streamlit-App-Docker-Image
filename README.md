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

git clone "your-project"

docker build -t divyaramesh196/stapp:latest . 

docker images -a  

docker run -d -p 8501:8501 divyaramesh196/stapp 

docker ps  

docker stop container_id 

docker rm $(docker ps -a -q)

docker login 

docker push divyaramesh196/stapp:latest 

docker rmi divyaramesh196/stapp:latest

docker pull divyaramesh196/stapp
