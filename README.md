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
docker-compose up --scale chrome=3 --scale firefox=3 (scaling)  

**Zalenium**  
docker pull elgalu/selenium  
docker pull dosel/zalenium  
 docker run --rm -ti --name zalenium -p 4444:4444 ^  
      -v /var/run/docker.sock:/var/run/docker.sock ^  
      -v /c/Users/your_user_name/temp/videos:/home/seluser/videos ^  
      --privileged dosel/zalenium start     
docker stop zalenium

**Create Jar**  
mvn clean package -DskipTests  

**Run Test**  
java -cp selenium-docker.jar;selenium-docker-tests.jar;libs/* org.testng.TestNG ../search-module.xml  
java -cp selenium-docker.jar;selenium-docker-tests.jar;libs/* -DBROWSER=firefox org.testng.TestNG ../search-module.xml

##Create Docker File##  
Create the file  
Build the image : docker build -t=userdocker/selenium-docker .  

**Acess Container**   
docker run -it --entrypoint=/bin/sh 217306aaaa/selenium-docker

**Run Test**
java -cp selenium-docker.jar:selenium-docker-tests.jar:libs/* -DHUB_HOST=192.168.0.139 org.test.TestNG search-module.xml






