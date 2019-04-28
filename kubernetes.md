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

&nbsp;&nbsp;&nbsp; Then we will see that a **POD** is a group of:  
- an "IP" address,  
- one or more APPs and  
- one or more volumes  
- A pod represents a unit that can perform a task / service. <br/><br/>

&nbsp;&nbsp;&nbsp; We will use **Minikube**, a **lightweight implementation of Kubernetes** that uses a virtualized computer running on my real computer and that creates **a cluster of a single node**. It's simple and uses a virtual environment to mount (MiniKube). <br/><br/>

&nbsp;&nbsp;&nbsp; Finally we will use **Kubectl**, a command line type program that interacts with MiniKube (API). <br/><br/>

&nbsp;&nbsp;&nbsp;Now we are going to **install minikube and kubectl**. You can follow this documentation:
-  [minikube: Jugando con kubernetes](https://github.com/iesgn/cloudandrelated/blob/master/paas/doc/minikube.md)
-  [Kubernetes (Minukube y Kubectl) y Clusters](https://dockertips.com/kubernetes)

&nbsp;&nbsp;&nbsp;**Summary of the steps**:
1. Download minikube:
> $ curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.30.0/minikube-linux-amd64 && \
>   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        chmod +x minikube && \
>   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        sudo cp minikube /usr/local/bin/ && \
>   &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;       rm minikube
  
2. Download kubectl:
> $ curl -Lo kubectl https://storage.googleapis.com/kubernetes-release/release/v1.10.0/bin/linux/amd64/kubectl && \
>   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        chmod +x kubectl && \
>   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        sudo cp kubectl /usr/local/bin/ && \
>   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        rm kubectl
  
3. Start the virtual machine with minikube (this step start the installation of the cluster).
> $ minikube start --vm-driver=virtualbox
  
&nbsp;&nbsp;&nbsp; <br/>Finally, we are going to check the installation and add the component *ingress*:
> $ kubectl get nodes  --> We can check the number of nodes of the cluster.  
> $ minikube addons enable ingress  -> add the component ingress

<br/><br/>
####  Section 4.- Practices
&nbsp;&nbsp;&nbsp;  We will do these practices:  
1. Fault tolerance
2. Scalability
3. Load Balancing
4. Continuous updates
5. Rollback
6. Routing
7. Persistent volumes
<br/><br/>

#####  Practice 1.- Fault tolerance
1. Create a pod:
    > $kubectl run pagweb --image jlr2/aplicacionesweb:v1  
    
2. In case the pod stops working, K8S create another one:  
2.1. We will delete the pod:
    > $ kubectl delete pod/pagweb-bb599dd-pxs2d  
    
&nbsp;&nbsp;&nbsp;2.2. We can check a new pod has been created
    > $ kubectl get pod  
    

3. We can also check the resource *Deployment*:
    > $ kubectl get deploy  
4. And the resource *ReplicaSet*:
    > $ kubectl get rs  
    
<br/><br/>

#####  Practice 2.- Scalability
1. ReplicateSet may replicate the pods:
    > $ kubectl scale deploy pagweb --replicas=3  
2. Check (each pod is running in a different node):
    > $ kubectl get pod -o wide

<br/><br/>

#####  Practice 3.- Load Balancing
1. Create a resource Service to access to the app:
    > $ kubectl expose deployment pagweb --port=80 --type=NodePort
2. Get the port of the application:
    > $ kubectl get services
3. Get the IP addresses of the cluster where the app is running:
    > $ minikube ip → Aparece 192.168.99.100
4. Check the access is OK by the local web browser: 
    > http://ip:puerto → Example: 192.168.99.100:32245.

<br/><br/>
#####  Practice 4.- Continuous updates
1. Modify the app (we create a  new image + upload to dockerhub)
> $ echo "&lt;h1&gt;Prueba2&lt;/h1&gt;" > index.htm  
> $ docker build -t jlr2/aplicacionweb:v2
> $ docker push  jlr2/aplicacionesweb :v2
2. After modifying the app, the updating process in the deployment is very easy:
> $ kubectl set image deployment pagweb pagweb=jlr2/aplicacionesweb:v2

<br/><br/>
#####  Practice 5.- Rollback
<br/><br/>
#####  Practice 6.- Routing
<br/><br/>
#####  Practice 7.- Persistent volumes
<br/><br/>


<br/><br/>


---
This exercise  is part of the activity **Introduction to PaaS: develop, deploy, run and manage apps on the Cloud**



#### Disclaimer
&nbsp;&nbsp;&nbsp;  *"The European Commission support for the production of this publication does not constitute an endorsement of the contents which reflects the views only of the authors, and the Commission cannot be held responsible for any use which may be made of the information contained therein."*




#### Author

&nbsp;&nbsp;&nbsp;  This material has been produced by José Luis Rodríguez Rodríguez under the Creative Commons licence:  <img src="/img/Licencia-Tipo2.png" height="25" width="75">  




