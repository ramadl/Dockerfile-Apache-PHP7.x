<p align="center">
<img src="https://ugeek.github.io/blog/images-blog/docker.png" width="250"> 
</p>

# Docker apache-php7.x
  
  _apache-php7.x_ is a project which contains a group of Dockerfiles to get up and running an apache-php Docker container for development and testing purposes. Each folder contains helpful and efficient files to start a desired environment. Pick the one you need. 
  
  This project is designed for tech enthusiasts who want to learn the basis of Docker and get their hands dirty with containerization techniques as well as for those who want to create complex images for production.
  
  You can make all the changes you want since all the containers derived from this project has root access. If your intention is to use this project for production enviroment, please make the necessary tweaks for that purpose due to security concerns.
  
  
## Getting started
  
The following steps will guide us to get a apache-php Docker container running on our local machine for development and testing purpouses.
  
  
### Prerequisites
  
* _Fundamental knowledges about [Docker](https://docs.docker.com/get-started/) and [Dockerfiles](https://docs.docker.com/get-started/part2/)._
    
* _Docker installed. If we don't have it, [install Docker](https://docs.docker.com/install/) in our computer._
    
* _Clone the repository:_  
  
      git clone https://github.com/RamaDL/Docker-alpine-apache-php.git
  
  
### Installation
  
  1 - cd to the php version (7.1 or 7.2 or 7.3 or 7.4) in the repository folder:
  
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

