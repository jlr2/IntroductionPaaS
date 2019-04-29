 **Project: “Cloud Computing in European schools”**  
<img src="/img/cloud-computing-logoproject.jpg" height="100" width="170">

 Number: Project: 2017-1-ES01-KA202-038471

<img src="/img/cofinanciadoEN.png" height="50" width="200"> <img src="/img/logoIES-Modificado.png" height="75" width="200">  




### Exercise no. 4: Openshift ... or minishift
&nbsp;&nbsp;&nbsp; Minishift is an application that can be used to deploy "easily" **a openshift cluster on one node** . This exercise is structured in the sections:
   1. Definition
   2. Installation
   3. Characteristics
   4. Practices
   
&nbsp;&nbsp;&nbsp;The sections will be explained by following a English documentation [Deploying applications on Openshift](https://iesgn.github.io/cloudandrelated/deploying_apps_openshift.html#/), but you can also read an Spanish version: [Introducción a Openshift. Aplicaciones orientadas a microservicios](https://iesgn.github.io/cloudandrelated/es_openshift.html#/)

<br/><br/>



####  Section 1.- Definition
&nbsp;&nbsp;&nbsp; Read this [documentation](https://iesgn.github.io/cloudandrelated/deploying_apps_openshift.html#/1/1).
<br/><br/>
####  Section 2.- Installation  
&nbsp;&nbsp;&nbsp; Read the [Minishift: Playing around with OpenShift v3](https://github.com/iesgn/cloudandrelated/blob/master/minishift.md).

&nbsp;&nbsp;&nbsp; The steps are:  
1. Go to [github minishift](https://github.com/minishift/minishift/releases)
2. Download the latest version for the desired operating system.
3. Decompress. A folder with the name of minishift is created.
4. We only need to launch minishift (minishift start) indicating that we want to execute the MV in VirtualBox (--vm-driver = virtualbox).
    > $ minishift start --vm-driver = virtualbox
    
The process takes a while. We must wait for the message to appear:  
 <pre>OpenShift server started.
    The server is accessible via web console at:
        https://192.168.99.128:8443

    You are logged in as:
        User: developer
        Password: developer

    To login as administrator:
        oc login -u system: admin </pre>  
5. If it failed to start, we can stop and restart:  
    > $ minishift stop  
    > $ minishift start --vm-driver = virtualbox  

####  Section 3.- Characteristics
&nbsp;&nbsp;&nbsp; Read this [documentation](https://iesgn.github.io/cloudandrelated/deploying_apps_openshift.html#/1/2).
<br/> 
&nbsp;&nbsp;&nbsp; It is important that you realize that:
1. Openshift simplifies the life cycle of our applications offered by **Docker**. It is very simple.
2. Openshift offers us all the advantages of **Kubernetes** (error tolerance, dynamic scalability, continuous updates, automatic deployments, routing to the applications, load balancing, persistent volumes).
3. Openshift gives us **more**: projects&users management, set of base images, volume management, integrated IC/CD flows, etc
<br/>
&nbsp;&nbsp;&nbsp;  And you should not never forget that **you are a developer** and Openshift is the *tool* to create Docker images, manage them by Kubernetes and so on.  **You must only think to develop the application** by using *GIT* (or a similar control version system), synchronize to a remote repository (GitHub for example). Openshift will do the rest (pull the source code to inject to a base docker image in order to create the docker image).


<br/><br/>
####  Section 4.- Practices
&nbsp;&nbsp;&nbsp;  We will do these practices:  
1. 
2. 
3. 
4. 


<br/><br/>

#####  Practice 1.- 

    
<br/><br/>

#####  Practice 2.- 


<br/><br/>

#####  Practice 3.-

<br/><br/>
#####  Practice 4.- 

<br/><br/>



---
This exercise  is part of the activity **Introduction to PaaS: develop, deploy, run and manage apps on the Cloud**



#### Disclaimer
&nbsp;&nbsp;&nbsp;  *"The European Commission support for the production of this publication does not constitute an endorsement of the contents which reflects the views only of the authors, and the Commission cannot be held responsible for any use which may be made of the information contained therein."*




#### Author

&nbsp;&nbsp;&nbsp;  This material has been produced by José Luis Rodríguez Rodríguez under the Creative Commons licence:  <img src="/img/Licencia-Tipo2.png" height="25" width="75">  




