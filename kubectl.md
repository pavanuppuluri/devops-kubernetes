# kubectl

* kubectl is the command line utility for running commands against Kubernets clusters

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

### Display detailed state of one or more resources

* General syntax
  ````
  kubectl describe [TYPE] [NAME]
  ````
