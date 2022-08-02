# kubectl

kubectl is the command line utility for running commands against Kubernets clusters

## Basic commands

![Screenshot](img/kubectl.png)


### To create a resource from a file

````
kubectl create -f example.yaml
````
````
kubectl create -f pod-example.yaml
````
````
kubectl create -f deployment-example.yaml
````
````
kubectl create -f <directory>
````

### To list one or more resources

* To get all pods

  ````
  kubectl get pods <pod-name>
  ````
* To get a specific pod

  ````
  kubectl get pod <pod-name>
  ````
* To check pod along with the node it is running on

  ````
  kubectl get pods <pod-name> -o wide
  ````
* To list multiple resources

  ````
  kubectl get pods,deploy
  ````

### To display detailed state of one or more resources

* General syntax
  ````
  kubectl describe [TYPE] [NAME]
  ````
  
* To get details of a pod
  ````
  kubectl describe pod <pod_name>
  ````
  
* To get details of a node
  ````
  kubectl describe node <node_name>
  ````
  
### To delete resources

* To delete a pod
  ````
  kubectl delete -f pod.yaml
  ````

* To delete multiple resources
  ````
  kubectl delete pods,services -l name=<label-name>
  ````

* To delete all pods
  ````
  kubectl delete pods --all
  ````
  
### To interact and execute inside a running container

* If pod contains only one running container
  ````
  kubectl exec <pod-name> command
  ````

* If pod contains more than one running container
  ````
  kubectl exec <pod-name> --container <container-name> command
  ````
  
* To open a shell when pod has more than one running container
  ````
  kubectl exec -it <pod-name> --container <container-name> -- /bin/bash
  ````
  

