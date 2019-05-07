 **Project: “Cloud Computing in European schools”**  
<img src="/img/cloud-computing-logoproject.jpg" height="100" width="170">

 Number: Project: 2017-1-ES01-KA202-038471

<img src="/img/cofinanciadoEN.png" height="50" width="200"> <img src="/img/logoIES-Modificado.png" height="75" width="200">  




### Exercise no. 4: Openshift ... or minishift
&nbsp;&nbsp;&nbsp; Minishift is an application that can be used to deploy "easily" **a Openshift cluster on one node** . This exercise is structured in the sections:
   1. Definition
   2. Installation
   3. Characteristics
   4. Resouces
   5. Versions
   6. Practices
   
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
    > $ minishift start --vm-driver=virtualbox
    
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
<br/><br/>
&nbsp;&nbsp;&nbsp;  And **you should not never forget that you are a developer** and Openshift is the *tool* to create Docker images, manage them by Kubernetes and so on.  **You must only think to develop the application** by using *GIT* (or a similar control version system), synchronize to a remote repository (GitHub for example). Openshift will do the rest (pull the source code to inject to a base docker image in order to create the docker image).


<br/><br/>
####  Section 4.- Resources
&nbsp;&nbsp;&nbsp; Openshift uses these resources (more details in [Openshift resources](https://iesgn.github.io/cloudandrelated/deploying_apps_openshift.html#/2) ):
- Projects
- Applications
- Builds
- Image registry
- Routes
- Service catalog
- Web console
- cli oc


####  Section 5.- Versions
&nbsp;&nbsp;&nbsp;  Openshift can be used by differents ways:  
1. OKD
2. Online
3. Dedicated
4. Container Platform

You get details about it in [Soluciones disponibles de Openshift](https://iesgn.github.io/cloudandrelated/es_openshift.html#/3)

<br/><br/>


####  Section 5.- Practices
&nbsp;&nbsp;&nbsp;  We will do these practices:  
1. Static web application
2. Updating and Rolling back the application
3. Deploying a PHP application
4. Deploying a PHP application with persistent volumes


<br/><br/>

#####  Practice 1.- Static web application
&nbsp;&nbsp;&nbsp; Read the documentation [Creating the first application](https://iesgn.github.io/cloudandrelated/deploying_apps_openshift.html#/3). You will deploy a static web application on OpenShift. The documentation includes a video-tutorial explaining the steps.

&nbsp;&nbsp;&nbsp; A summary is:
1. Create a project
2. Create an application: choose a catalog image +  write the GIT Repository URL (where the source code is).

&nbsp;&nbsp;&nbsp;After these steps:
1. Openshift will create a docker image (Use Docker)
2. Openshift will create a pod, a service and a route (Use K8S). So, Openshift has deployed the application.
3. The application can be accessed
    
<br/><br/>

#####  Practice 2.- Updating and Rolling back the application
&nbsp;&nbsp;&nbsp;  Read the documentation [Updating and rolling back the application](https://iesgn.github.io/cloudandrelated/deploying_apps_openshift.html#/4).  The documentation shows how Openshift deploys an update and how to roll back.

&nbsp;&nbsp;&nbsp; A **summary** is:
- **Updating**: After you modify the application, you only has to choose your application (Overview) and select "Start Build".  Openshift will deploy automatically the new version.  In Deployments we can see all the versions of the application
- **Rollback**:  It is so easy as to choose a previous deployment and click "Roll back".
<br/><br/>


#####  Practice 3.- Deploying a PHP application
&nbsp;&nbsp;&nbsp;  Read the documentation [Deploying a PHP application](https://iesgn.github.io/cloudandrelated/deploying_apps_openshift.html#/6). This practice deploys a CMS (CMSPHP)
<br/><br/>

&nbsp;&nbsp;&nbsp; A **summary** is:
1. Choose "PHP" from OpenShift image catalog.
2. Configure "https://github.com/ilosuna/phpsqlitecms.git" as the source code
3. The image is created and the other K8S resources: pod, services, route. We can check that the app is running by its DNS name.
4. Try to make some change in the source code and create a new version of the docker image (*Start build*). It is interesting to realize how the old pod is deleted and a new pod is created.  Connect again and check the changes was made.
5. In case we scale our application, we can realize that no all pods contains the same content. So it is necessary **persistent volumes**.
&nbsp;&nbsp;&nbsp; 


#####  Practice 4.- Deploying a PHP application with persistent volumes
&nbsp;&nbsp;&nbsp;  Read the documentation [Deploying a PHP application with persistent volume on Openshift V3](https://iesgn.github.io/cloudandrelated/deploying_apps_openshift.html#/7/1). This practice continues the previous practice but using an external storage (volume) for the database.
&nbsp;&nbsp;&nbsp; A **summary** is:
1. Fork the repository with the CMS into your Github account. Remember: "https://github.com/ilosuna/phpsqlitecms.git".
2. Make a copy from the directory  *cms/data* and called it *cms/datos*.
3. Build the image in OpenShift (remember the rest -pods, services, route, deployment will be created automatically).
4. Create a volume in OpenShift (called *disco1*). Thes volume will the disk where the data will be saved from the CMS to get the persistent volume.
5. Associate the volume *disco1* to the pod. This action will mount the *disco1*  on the path */opt/app-root/src/cms/data*. Go to *Deployment* to do it.
6. Initially, the *disco1* doesn't have any data; we need to copy the data from  */cms/datos* to this directory. Connect to the pod by its terminal and lauch the command 'cp /opt/apt-root/src/cms/datos /opt/apt-root/src/cms/data'.
7. Now, we can modify our application and launch several pods; they all will have the same content after any modification. 
 

<br/><br/>
---
This exercise  is part of the activity **Introduction to PaaS: develop, deploy, run and manage apps on the Cloud**



#### Disclaimer
&nbsp;&nbsp;&nbsp;  *"The European Commission support for the production of this publication does not constitute an endorsement of the contents which reflects the views only of the authors, and the Commission cannot be held responsible for any use which may be made of the information contained therein."*




#### Author

&nbsp;&nbsp;&nbsp;  This material has been produced by José Luis Rodríguez Rodríguez under the Creative Commons licence:  <img src="/img/Licencia-Tipo2.png" height="25" width="75">  




