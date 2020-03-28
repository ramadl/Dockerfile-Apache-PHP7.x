<p align="center">
<img src="https://ugeek.github.io/blog/images-blog/docker.png" width="250"> 
</p>

# Docker apache-php7.x
  
  _apache-php7.x_ is a project that contain a group of Dockerfiles for ease the task of get up and running an apache-php Docker container only for development and testing purposes. Each folder has a bunch of files to start our desired enviroment. Pick the one you need.  
  
  Altough this project is designed for those tech entusiasts thath want to learn the basis of Docker an get their hands dirty with conteinerization techniques. This repository can be used as a base to create more complex images for production.
  
  All the containers derived from this project has root access to make any change thath we want. If our intention is to used in production, this is a security concern so please make the necessary tweaks for thath purpouse.
  
  
## Getting started
  
The following steps will guide us to get a Doceker container running on our local machine for development and testing purpouses.
  
  
### Prerequisites
  
* _Fundamental knowledges about [Docker](https://docs.docker.com/get-started/) and [Dockerfiles](https://docs.docker.com/get-started/part2/)._
    
* _Docker installed. If we don't have it, [install Docker](https://docs.docker.com/install/) in our computer._
    
* _Clone the repository:_  
  
      git clone https://github.com/RamaDL/Docker-alpine-apache-php.git
  
  
### Installation
  
  1 - cd to the php version in the repository folder:
  
    cd repository_path/Docker-alpine-apache-php/php_version/
    
  2 - (Optional) Edit **_httpd.conf_** inside the php_version folder for apache2 configuration. 
  
  3 - (Optional) Edit **_Dockerfile_** inside the php versión folder and add the desired php modules in the **RUN** instruction.
    
  4 - Build the desired image ([php_version in Backus–Naur form](https://en.wikipedia.org/wiki/Backus–Naur_form)):
  
    docker build -t apache-php:<php_version> .
  
  5 - Create the container:
  
    docker build --name apache-php -p 127.0.0.1:80:80 -v /path/to/your/www/folder:/shared -d apache-php:<php_version>
    
  * **-p**    maps our localmachine port 80 to the container port 80. 
  * **-v**    allows us to enter the www folder from the shared folder inside the container.  
  * **-d**    starts the container in background.  
    
  6 - Gain access to the container:
  
    docker exec -it apache-php sh
    
  Once we are inside the container we have root access to play around.
    
    
  ### Running the tests
    
  After we have the running container is time to test it. Go to [http://localhost:80](http://localhost:80) and we have to see our/s web project/s.
    

### Authors

* Dutto Luquez, Ramiro ( [RamaDL](https://github.com/RamaDL) )

