 **Project: “Cloud Computing in European schools”**  
<img src="/img/cloud-computing-logoproject.jpg" height="100" width="170">

 Number: Project: 2017-1-ES01-KA202-038471

<img src="/img/cofinanciadoEN.png" height="75" width="200"> <img src="/img/logoIES-Modificado.png" height="75" width="200">  




# Introduction to PaaS: develop, deploy, run and manage apps on the Cloud  



#### Disclaimer
&nbsp;&nbsp;&nbsp;  *"The European Commission support for the production of this publication does not constitute an endorsement of the contents which reflects the views only of the authors, and the Commission cannot be held responsible for any use which may be made of the information contained therein."*




#### Author

&nbsp;&nbsp;&nbsp;  This material has been produced by José Luis Rodríguez Rodríguez under the Creative Commons licence:  <img src="/img/Licencia-Tipo2.png" height="25" width="75">  




### Objective
&nbsp;&nbsp;&nbsp; Platform as a Service (PaaS), is a cloud computing model that allows the users to develop, deploy, run and manage applications without taking care about the underlying layers. The alternatives used today focus on the use of containers which promote the microservices based application development approach (vs monolithic applications), because the different services into which we the application is separated can easily run in different containers. We will make a study of Docker, Kubernates and OpenShift in order to develop, deploy, run and manage  microservices based applications.

&nbsp;&nbsp;&nbsp;This activity has been developed for developing the professional competence includes in the Erasmus+ project "Cloud Computing in European Schools".
<br>
<br> 

### Index
 1. Initial level
 2. Exercise no.1: Introduction to PaaS
 3. Exercise no.2: Docker
 4. Exercise no.3: Kubernetes
 5. Exercice no 4: OpenShift
 6. Final level
 7. Others
    1. Work methodology
    2. Documentation and exhibitions
    3. Mark
    4. Evaluation criteria evaluated
    5. Bibliography
 


###  Initial Level
&nbsp;&nbsp;&nbsp;  Do this [questionnarie](PENDING) to asses your initial level.  
<br><br>

### Exercise no. 1: Introduction to PaaS

&nbsp;&nbsp;&nbsp;**Read** the [Introduction to PaaS - English version](https://iesgn.github.io/cloudandrelated/paas.html#/) or [Introducción a PaaS - Spanish version](https://iesgn.github.io/cloudandrelated/es_paas.html#/) to learn about what is PaaS, differences with SaaS and IaaS, and the big players (companies) about PaaS.
<br><br>


### Exercise no. 2: Docker
&nbsp;&nbsp;&nbsp;After learning what is the scope of PaaS,  now it is time to start the study of the first level: the **containers**.  Docker is the most used solution nowaday.  We are going to structure the learning of Docker in the next sections:
   1. Docker installation: virtual machine managed by Vagrant.
   2. Docker applications lifecycle.
   3. Docker containers: not persistent.
   4. Docker commands summary.
   5. Docker applications example: Wordpress.
   
&nbsp;&nbsp;&nbsp;The sections will be explained by following a Spanish documentation, but you can also read an English version: [Docker - English version](https://iesgn.github.io/cloudandrelated/docker.html#/).

####  Section 1.- Docker installation: virtual machine managed by Vagrant
&nbsp;&nbsp;&nbsp;  We will practice Docker by using a virtual machine managed by **Vagrant**.
<br/><br/>
 &nbsp;&nbsp;&nbsp; Vagrant is a tool for building and managing virtual machine environments in a single workflow. With an easy-to-use workflow and focus on automation, Vagrant lowers development environment setup time, increases production parity, and makes the "works on my machine" excuse a relic of the past. Machines are provisioned on top of VirtualBox, VMware, AWS, or any other provider. Go to [Vagrant](https://www.vagrantup.com/intro/index.html) for more details.
<br/><br/>
 &nbsp;&nbsp;&nbsp; Vagrant is useful for developers, for operators, for designers, for everyone.
 <br/><br/>
 &nbsp;&nbsp;&nbsp; Instead of building a virtual machine from scratch, which would be a slow and tedious process, Vagrant uses a base image to quickly clone a virtual machine. These base images are known as "boxes" in Vagrant, and specifying the box to use for your Vagrant environment is always the first step after creating a new Vagrantfile. We can access to these boxes in [Vagrant Boxes](https://app.vagrantup.com/boxes/search).
 <br/><br/>
 &nbsp;&nbsp;&nbsp;  The next **commands** are the basic ones:
   1. **vagrant box add …** →  download image / box from Vagrant repository.  Example: vagrant box add ubuntu/bionic64 --provider virtualbox  --> download an image (box) of Ubuntu verson Bionic 64 bits for VirtualBox.
   2. **vagrant box list** →   list all downloaded images / boxes.
   3. **mkdir FOLDER**  → create folder where we will create the Vagrantfile file that will contain the definition of the MV.
   4. **cd FOLDER**  →  go in inside the folder.
   5. **vagrant init BOX**  →    The MV files are located in the directory where the hypervisor (VirtualBox, VMWare ...) stores its MVs. In FOLDER, the VagrantFile file, a log file and a hidden .vagrant folder will be saved.  Example: vagrant init ubuntu/bionic64 --> the box used is ubuntu bionic 64.
   7. **vagrant up**  →  start the MV  --> We can check the virtual machine runnning by open the VirtualBox app.
   5. **vagrant ssh** →  connect to the MV
   6. **vagrant halt** → stop the MV
 <br/><br/>
 &nbsp;&nbsp;&nbsp;  Now, we know the basic concepts in order to install a virtual machine by using a Vagrant box. The next steps are:
   1. Install vagrant    
   > $ sudo apt install vagrant  -->  We can verify the installation by *$ vagrant --version*<br/>
   > $ sudo apt install virtualbox  -->  Install Virtualbox<br/>
   
 &nbsp;&nbsp;&nbsp;The article [How to install Vagrant on Ubuntu 18.04](https://linuxize.com/post/how-to-install-vagrant-on-ubuntu-18-04/) explains the steps.

<br/><br/>
 &nbsp;&nbsp;&nbsp; 
   Finally, we are going to **install a virtual machine with Docker**. Follow [Installation of Docker - Spanish version](https://github.com/iesgn/cloudandrelated/blob/master/paas/doc/docker.md) to do it. Note: We don't use *vagrant init BOX*; instead of this, we create a Vagrantfile with the content that appears in the previous link.
   <br/><br/>
 &nbsp;&nbsp;&nbsp;  Have you been able to connect to the virtual machine and check whether "Docker" is running? *Which Docker version do you have?*
<br><br>


#### Section 2.- Docker applications lifecycle
&nbsp;&nbsp;&nbsp;After installing an environment with Docker, we are going to develop Docker images and deploy containers to run our applications. The documentation to read is [Lifecycle of Docker based applications - Spanish version](https://iesgn.github.io/cloudandrelated/es_docker.html#/). 
<br/><br/>
&nbsp;&nbsp;&nbsp;The reading must have taught you (it is showed a summary:
   1. **Create the application**. We are going to create a web page *index.html* that will be served by a web server that will run in a Docker container. The web page  and it will be saved in */home/vagrant/public_html/*: <br/>
   > $ mkdir public_html <br/>
   > $ cd public_html<br/>
   > $ echo "&lt;h1&gt;Prueba&lt;/h1&gt;" > index.html <br/>

   
<br/><br/>
 
   2. **Create a Docker image**. <br/>
   2.1.- Using a **Dockerfile** we define how we are going to create our image:
    <pre>&nbsp;&nbsp;&nbsp;
    FROM -->       Which base image we are going to use
    RUN  -->       Which packages we are going to install
    COPY -->       Where we copy our source code (web page)
    ENTRYPOINT --> We indicate the service that will run the container (apache server) </pre>

 &nbsp;&nbsp;&nbsp; Example.  Define an image with debian, install Apache2, copy our webpage to the public directory of Apache and start Apache. Note: the image *debian* is downloaded from [dockerhub](https://hub.docker.com/)
   <pre>&nbsp;&nbsp;&nbsp; FROM debian
    RUN apt-get update -y && apt-get install -y \
        apache2 \
        && apt-get clean && rm -rf /var/lib/apt/lists/*
    COPY ./public_html /var/www/html/
    ENTRYPOINT ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]  </pre>
 &nbsp;&nbsp;&nbsp;  2.2.- **Create the Docker image**
   > $ docker build -t jlr2/aplicacionesweb:v1 .  <br/>
   > $ docker image ls  --> list the docker images created  <br/>
   <br/><br/>
 &nbsp;&nbsp;&nbsp;  3. **Create/Run a container in the development environment**.
   > docker run --name aplweb -d -p 80:80   jlr2/aplicacionesweb:v1
   > docker container ls --> list the containers created
   We can check our web page by a web browser. Connect locally by using, for example, the text web browser links (URL = http://127.0.0.1).
   
   4.- **Distribute/Share the Docker image; dockerhub**
   > Create a Docker account: https://hub.docker.com 
   > docker push jlr2/aplicacionesweb :v1  --> Upload the image
   We can check it by 2 ways:
   > docker search jlr2/aplicacioneseweb 
   > Look for in our Docker account. 

   5.- **Deploy the application in the production environment**
   >  docker pull jlr2/aplicacionesweb:v1  --> download the image from the dockerhub
   >  docker run --name aplweb -d -p 80:80   jlr2/aplicacionesweb:v1   --> create/run the container

   6.- **Modify the application** In case we modify the application it is necessary to build a new image:
   >  echo "<h1>Prueba 2</h1>" > index.htm   -->  modify the application
   >  docker build -t josedom24/aplicacionweb:v2  -->  create the new image (in the development environment)
   >  docker push jlr2/aplicacionesweb :v2  --> upload the new image
   >  docker pull  jlr2/aplicacionesweb :v2  --> (download the new image to the production environment)
   >  docker container rm -f aplweb  -->  delete the current container  (in the production environment)
   >  docker run --name aplweb2 -d -p 80:80   jlr2/aplicacionesweb:v2  --> run the new container (in the production environment)
   
<br><br>

#### Section 3.- Docker containers: not persistent.
 - Data stored in a container is not persistent.
 - When data must be stored persistently, volumes must be used.
 - The scenario is: the application is decoupled from the data, that is, the application will run in a container and the data in a persistent medium external to the container. Advantages:
+ If the container fails, information is not lost, you only need to create a new container.
+ If the data is updated it is not necessary to build a new image.
 - Example: 
 * we are going to create a container with a MySQL server; the data is stored in a persistent volume:
  > $ docker run --name some-mysql -v /opt/mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=asdasd -d mysql
 * Create a database called *dbtest*
 > $ docker exec -it some-mysql bash
   > root@75544a024f9b:/# mysql -u root -p -h localhost
   > ...
  > create database dbtest;
 * Delete the container.
 > $ docker container rm -f some-mysql
 * Create a new container:
 > $ docker run --name some-mysql2 -v /opt/mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=asdasd -d mysql
 * Verify that the database is still created
 > $ docker exec -it some-mysql bash
   > root@75544a024f9b:/# mysql -u root -p -h localhost
   > ...
  > show  databases;

<br><br>


#### Section 4.- Docker commands summary
  This section shows a summary of Docker commands. We can see examples in [Ejercicios con Docker](https://github.com/iesgn/cloudandrelated/blob/master/paas/doc/ejercicios_docker.md).
  
- List containers
    > $ docker ps
    > $ docker container ls 
- List images
    > $ docker image ls
- Create a container and establish an interactive session
    > $ docker run -it --name CONTAINER-NAME ubuntu /bin/bash
- Stop a container when we are inside it
    > exit
- Stop a container without being inside it
    > $ docker stop CONTAINER-NAME
- Start a stopped container
    > $ docker start CONTAINER-NAME
- Connect to a container
    > $ docker attach CONTAINER-NAME
- Create a daemon container  
    > $ docker run -d --name CONTAINER-NAME ubuntu /bin/sh -c "while true; do echo hello world; sleep 1; done"
- Check what a container is doing
    > docker logs CONTAINER-NAME
- Delete a container
    > $ docker rm  CONTAINER-NAME

<br><br>

#### Section 5.- Docker applications example:  Wordpress
   Wordpress installation needs 2 containers: one for Wordpress and other for the database:
- Database server. Container: servidor_mariadb
> $ docker run --name servidor_mariadb -e MYSQL_ROOT_PASSWORD=asdasd -e MYSQL_DATABASE=wordpress -d mariadb

- Wordpress. Container: servidor_wp. This container links to the database container
> $ docker run --name servidor_wp -p 8000:80 --link servidor_mariadb:mariadb -d wordpress


Now, check the installation process is working (use 'links' and connect to the URL "http://IP_servidor_wp"). The IP of the servidor_wp can get by "$docker logs servidor_wp".
<br><br>


### Exercise no. 3: Kubernetes



### Exercice no. 4: OpenShift



###  Final Level
&nbsp;&nbsp;&nbsp;  Do this [questionnarie](https://docs.google.com/forms/d/e/1FAIpQLSdYfxr0NwK-qqOg-6vPN-WtizHAmeuRz5MwX6N9NXM9W3W-Cg/viewform) to asses your initial level.  





### Work methodology


 1. Collaborative team work.
 2. The class will be distributed in groups and each group have to practice the exercises proposed in this activity.
 3. The practices must be documentated.


### Documentation and exhibition
 1. Only delivery for each group.
 2. The documentation must include practices about exercises 2 and 3 and explain the relationship between GIT in Eclipse/ Eclipse Che with GIT commands. 
 3. The documentation format is a videotutorial. It must follows the guide for [videotutorials](https://docs.google.com/document/d/1WV89OADdWK86i5uplX4zYoLHmDxdDgc-HiDkf1QdzN4/edit?usp=sharing).
 4. These videotutoriales will be uploade to the IT Department account on YouTube.
 5. Students who have been selected for mobility must submit the documentation in English.
 6. All the groups will do a  presentation  of the activity in class.
 7. Students selected for mobility to Italy must prepare a 1-hour workshop to teach the rest of the students from the other participating centers. The objective of the workshop is that attendees learn the most theoretical aspects of GIT and doing the practices. The generated documentation must be oriented for this workshop. Suggestion: use tools such as Google Form to gather information or Kahoot to prepare interactive questions. The creativity of the presented workshop will be valued.


### Mark
&nbsp;&nbsp;&nbsp;This activity is part of the Erasmus + project "Cloud Computing in  European schools". All students must complete it. An increase up to 1 point will be added in the final mark of the professional module where the activity is developed, provided that the grade obtained in the evaluation of the associated learning results is equal to or greater than 5.      






### Evaluation criteria evaluated
	
&nbsp;&nbsp;&nbsp;The activity will serve as an improvement / recovery of the following criteria (in addition to it was indicated in the previous section):  

  * 2d + 2e + 2f  
  * 3e + 3f + 3g + 3h  
  * 4a + 4b

This criteria mark will be increased even whether grade obtained in the evaluation of the associated learning results is equal to or greater than 4.5, but only in the case the project requested for these criterio have been developed by using GIT with, at least, 2 people in the same group.  



### Bibliography
 
 1. [Introduction to PaaS - English version](https://iesgn.github.io/cloudandrelated/paas.html#/)
 2. [Introducción a PaaS - Spanish version](https://iesgn.github.io/cloudandrelated/es_paas.html#/)
 3. [Docker - English version](https://iesgn.github.io/cloudandrelated/docker.html#/)
 4. [Installation of Docker - Spanish version](https://github.com/iesgn/cloudandrelated/blob/master/paas/doc/docker.md) 
 5. [Lifecycle of Docker based applications - Spanish version](https://iesgn.github.io/cloudandrelated/es_docker.html#/)
 6. [Vagrant](https://www.vagrantup.com/intro/index.html)
 7. [Vagrant Boxes](https://app.vagrantup.com/boxes/search)
 8. [How to install Vagrant on Ubuntu 18.04](https://linuxize.com/post/how-to-install-vagrant-on-ubuntu-18-04/)
 9. [dockerhub](https://hub.docker.com/)
 10. [Ejercicios con Docker](https://github.com/iesgn/cloudandrelated/blob/master/paas/doc/ejercicios_docker.md)



 


