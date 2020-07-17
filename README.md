# WebDriverDockerAws
Selenium WebDriver with Docker, Jenkins &amp; AWS

## Useful Docker Commands
**docker pull image**: pulls an image from DockerHub  
**docker image**: show all images in our machine  
**docker ps**: show all running containers  
**docker ps -a**: show all containers including stopped containers  
**docker run image**: creates a container from an image  
**docker stop container id/container name**: stop running container  
**docker system prune -f**: remove all stopped containers  
**docker system prune -a**: remove all stopped containers + unused  

## Create Selenium Grid Environment

**First**  
docker pull selenium/hub:3.14  
docker pull selenium/node-firefox:3.14  
docker pull selenium/node-chrome:3.14  

**Second**   
Create docker compose file  
docker-compose up or docker-compose up-d
