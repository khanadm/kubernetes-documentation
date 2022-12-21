#### Kubernetes-Documentation

![K8S](https://user-images.githubusercontent.com/106643382/207097871-755caa25-8efd-4ad9-9ccd-f05aa017b2e0.png "K8S")



#### WHAT IS KUBERNETES ??

K8S is a system for deploying, scaling and managing containerized applications across a cluster of nodes.

 The K8S cluster has 2 main components:

 1 Master Node (Control Plane) : this node hosts the Kubernetes control plane and manages the cluster


  2 Worker Node : runs your containerized applications


![K8S Architecture Diagram](https://user-images.githubusercontent.com/106643382/207097457-327ada1d-d15e-4bec-b394-5af451be0379.png "K8S Architecture Diagram")



#### Now Let’s dive into each of these components.


Master Components
---

It manages the K8S cluster and performs all administrative tasks.

API Server
---

It is the front-end of the K8S control plane where all other components interact, to talk with the K8S cluster. It validates and processes the REST requests.

Controller Manager
---

It continuously watches the shared state of the cluster and makes corrective changes to bring the current state to the desired state.



Examples of controllers:
---

- Replication controller

- Namespace controller

- Endpoint controller

- Service account controller




Scheduler
---

It is responsible for distributing the workload to available nodes across the cluster, based on resource utilization.



etcd
---

It is a simple, distributed and consistent key-value store. It stores all the relevant data to manage the cluster.




Few examples of data stored are:

* State and details of pods, services.

* Data on scheduled, created and deployed jobs.

* Details about subnets, configmaps, and secrets.

---

 Worker Components
---


Physical server or VM that runs applications using pods.

Kubelet
---

It monitors the API server for pods that are scheduled to the node and start the pod’s container by instructing the container runtime engine, 
then reports the status of the running containers back to the API server.

Kubelet is the technology that applies, creates, updates, and destroys containers on a Kubernetes node.

Kube Proxy
---

It makes services available to the external hosts, manages network rules and port forwarding. It also serves as a Network proxy and Load balancer and handles the network routing for TCP and UDP packets.

Container Runtime
---

It is the underlying software that runs the containers and handles the container’s lifecycle in an isolated but lightweight environment.


Platforms that use containers as a container runtime are:

* Docker

* Containerd

* Cri-o

* rktlet


Kubectl
---

It is the command-line tool to communicate with the API server and send commands to the master node.



Examples of few frequently used commands are:


---

kubectl apply -f file.yaml   #Create a resource from file

kubectl get pods             #List all pods in the default namespace

kubectl describe svc my_svc  #Describes about the specified service

---


Replica controller vs Replica set
---


![Difference](https://user-images.githubusercontent.com/106643382/208720074-67e34382-76e0-4bc4-9910-5a6a9e42c857.png "Difference")

---


Persistent Volume (PV)
---



Kubernetes makes physical storage devices such as our SSDs, NFS servers available to your cluster in the form of objects called Persistent Volumes.

---

Persistent Volume Claims
---



A persistent volume claim (PVC) is a request for storage by a user from a PV. Claims can request specific size and access modes 
(e.g: they can be mounted once read/write or many times read-only).

If none of the static persistent volumes match the user’s PVC request, the cluster may attempt to dynamically create a PV that
matches the PVC request based on storage class.

---


What are the types of Kubernetes services?
---

ClusterIP.   Exposes a service which is only accessible from within the cluster.

NodePort.    Exposes a service via a static port on each node’s IP.

LoadBalancer.  Exposes the service via the cloud provider’s load balancer.

---

What is the Kubernetes ClusterIP service?
---

ClusterIP is the default type of service, which is used to expose a service on an IP address internal to the cluster. 
Access is only permitted from within the cluster.

---

What is the Kubernetes NodePort service ?
---

It is an open port on every worker node in the cluster that has a pod for that service. When traffic is received on that open port, 
it directs it to a specific port on the ClusterIP for the service it is representing
























