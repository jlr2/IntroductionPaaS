 **Project: “Cloud Computing in European schools”**  
<img src="/img/cloud-computing-logoproject.jpg" height="100" width="170">

 Number: Project: 2017-1-ES01-KA202-038471

<img src="/img/cofinanciadoEN.png" height="50" width="200"> <img src="/img/logoIES-Modificado.png" height="75" width="200">  




### Exercise no. 3: Kubernetes
&nbsp;&nbsp;&nbsp;The next level of our study of Paas is Kubernetes (K8S), an **application container orchrestator** . The study of K8S will be divided in the next sections:
   1. Definition
   2. Resources
   3. Minikube
   4. Practices
   
&nbsp;&nbsp;&nbsp;The sections will be explained by following a Spanish documentation, but you can also read an English version: [Kubernetes - English version](https://iesgn.github.io/cloudandrelated/kubernetes.html#/).
<br/><br/>

####  Section 1.- Definition
&nbsp;&nbsp;&nbsp; Read this [documentation](https://iesgn.github.io/cloudandrelated/es_kubernetes.html#/1).
<br/><br/>
####  Section 2.- Resources  
&nbsp;&nbsp;&nbsp; Read the [documentation](https://iesgn.github.io/cloudandrelated/es_kubernetes.html#/2).  
&nbsp;&nbsp;&nbsp; As you have read the next figure shows the different parts:  
    <img src="/img/kubernetes1.png" height="300" width="600">  
&nbsp;&nbsp;&nbsp;The resources showed are:<br/>
   -  Pods
   -  ReplicaSet
   -  Deployment
   -  Service
   -  Ingress
<br/><br/>
####  Section 3.- minikube
&nbsp;&nbsp;&nbsp; The concept of **Kubernetes** is to assemble a **cluster** where they can run containers, there is a "Manager" node that can send tasks / containers to other "Workers" nodes to execute them. Each node is a virtual or physical team where **Containers / PODs** will run.<br/><br/>

&nbsp;&nbsp;&nbsp; Then we will see that a POD is a group of "IP", one or more APPs and one or more volumes, represents a unit that can perform a task / service. <br/><br/>

&nbsp;&nbsp;&nbsp; We will use **Minikube**, a **lightweight implementation of Kubernetes** that uses a virtualized computer running on my real computer and that creates **a cluster of a single node**. It's simple and uses a virtual environment to mount (MiniKube). <br/><br/>

&nbsp;&nbsp;&nbsp; Finally we will use **Kubectl**, a command line type program that interacts with MiniKube (API). <br/><br/>

&nbsp;&nbsp;&nbsp;Now we are going to install minikube and kubectl. You can follow this documentation:
-  [minikube: Jugando con kubernetes](https://github.com/iesgn/cloudandrelated/blob/master/paas/doc/minikube.md)
-  [Kubernetes (Minukube y Kubectl) y Clusters](https://dockertips.com/kubernetes)

The summary of the steps is:
1. Download minikube
> $ curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.30.0/minikube-linux-amd64 && \
>         chmod +x minikube && \
>         sudo cp minikube /usr/local/bin/ && \
>         rm minikube

<br/><br/>
####  Section 4.- Practices
<br/><br/>


---
This exercise  is part of the activity **Introduction to PaaS: develop, deploy, run and manage apps on the Cloud**



#### Disclaimer
&nbsp;&nbsp;&nbsp;  *"The European Commission support for the production of this publication does not constitute an endorsement of the contents which reflects the views only of the authors, and the Commission cannot be held responsible for any use which may be made of the information contained therein."*




#### Author

&nbsp;&nbsp;&nbsp;  This material has been produced by José Luis Rodríguez Rodríguez under the Creative Commons licence:  <img src="/img/Licencia-Tipo2.png" height="25" width="75">  




