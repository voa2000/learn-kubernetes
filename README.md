# Learn Kubernetes

A node is a worker machine in Kubernetes and may be a VM or physical machine, depending on the cluster. Multiple Pods can run on one Node.

* kubectl get - list resources
* kubectl describe - show detailed information about a resource
* kubectl logs - print the logs from a container in a pod
* kubectl exec - execute a command on a container in a pod

# Kubernetes Services

* ClusterIP (default) - Exposes the Service on an internal IP in the cluster. This type makes the Service only reachable from within the cluster.
* NodePort - Exposes the Service on the same port of each selected Node in the cluster using NAT. Makes a Service accessible from outside the cluster using <NodeIP>:<NodePort>. Superset of ClusterIP.
* LoadBalancer - Creates an external load balancer in the current cloud (if supported) and assigns a fixed, external IP to the Service. Superset of NodePort.
* ExternalName - Exposes the Service using an arbitrary name (specified by externalName in the spec) by returning a CNAME record with the name. No proxy is used. This type requires v1.7 or higher of kube-dns.

# Scaling an application
* In the previous modules we created a Deployment, and then exposed it publicly via a Service. The Deployment created only one Pod for running our application. When traffic increases, we will need to scale the application to keep up with user demand.

* Scaling is accomplished by changing the number of replicas in a Deployment
-  kubectl scale deployments/wordpress-mysql --replicas=4 // creates 4 including the one that already exist.
-  kubectl set image deployments/kubernetes-bootcamp kubernetes-bootcamp=jocatalin/kubernetes-bootcamp:v2 //update app
-  kubectl rollout status deployments/kubernetes-bootcamp // rollback app
-  kubectl rollout undo deployments/kubernetes-bootcamp //revert to the previous version 


Course on udemy
* https://classroom.udacity.com/courses/ud615

# Containers
Here are two articles with a good write-ups about containers, if you want to go more in-depth about container technology:

Containers bring a skinny new world of virtualization to Linux
What are containers and why do you need them?

# Cheatsheet for K8s
* https://kubernetes.io/docs/reference/kubectl/cheatsheet/

#  Shortcuts for running kubernetes on bash

* https://github.com/ahmetb/kubectx/blob/master/kubens
Can install this using '''brew install kubectx'''
