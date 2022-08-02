# Pod Config

## Pod mainfest - Example (pod-spec.yaml)

````
apiVersion: v1
kind: Pod
metadata:
  name: nginx

spec:
  containers:
  - name: nginx
    image: nginx:1.14.2
    ports:
    - containerPort: 80
````

## Create a pod
````
kubectl create -f pod-spec.yaml
````

## Expose a pod using NodePort service
````
kubectl expose pod <pod-name> --type=NodePort --port=80
````
