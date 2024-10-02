# Fastapi-docker-aws
Create docker container with Fastapi and deploy the container on aws

mkdir Myproject #Create Directory MyProject
python3 -m venv fs-env #Create virtual env
source fs-env/bin/activate #activate env
pip3 install fastapi[standard] # install fastapi with all the dependencies
pip freeze > requirements.txt #create requirements.txt
mkdir app > Create app directory for fastapi project
touch main.py > Create main.py file
create simple get api in main.py

#docker setup
Install docker and docker desktop and login
touch Dockerfile #create docker file for fastapi project
add necessary commands
docker build -t my-image . - Create docker image
docker run -d -p 80:80 my-image -  run image docker locally
Create repository on docker-hub.com - will further use this for cloud deployment
docker tag my-image repository_name -  create matching repo image using tag
docker push repository_name - push to docker hub

#Aws Deployment for Container
We will use ECS of aws 
create/login aws console 
Goto ECS
task definition > create task > add containers and other setup
goto cluster
create cluster > create service for api

Once deployed use task IP for running it make sure to add custom inbound rule in service so that you can access the public IP address
🎉 Our api is live 🎉 
