# ConfigMaps
* ConfigMaps decouples configuration from pods and components
* Stores configuration data as Key-value pairs
* It is similar to secrets but don't contain sensitive information
* We must create a ConfigMap before referencing it in Pod spec
* if we reference non-existing ConfigMap inside the Pod then Pod will be in Pending state only
* SImilarly if we reference non-existing Keys inside the Pod then Pod will be in Pending state only


## How do we make the containers portable?

* Containers expect configuration from
  * Configuration files
  * Command line arguments
  * Environment variables


### Creating ConfigMap

````
kubectl create configmap <map-name> <datasource>

datasource can be directory/file/literal  --from-file / --from-literal
````

### Creating & Using ConfigMap In A Pod

**app.properties**

````
system.type="TESTING CONFIGMAP"
system.number=12345
````

**Create ConfigMap**

````
kubectl create configmap app-configmap --from-file=configmap-example/app-basic.properties
````

**Create Pod & Use ConfigMap**

````
apiVersion: v1
kind: Pod
metadata:
name: configmap-example-pod
spec:
containers:
- name: configmap-example-busybox
image: k8s.gcr.io/busybox
command: [ "/bin/sh", "-c", "env" ]
envFrom:
# Load the Complete ConfigMap
- configMapRef:
name: app-configmap
restartPolicy: Never
````

### Mounting ConfigMap In A Pod

````
apiVersion: v1
kind: Pod
metadata:
  name: configmap-example-pod
spec:
  containers:
    - name: configmap-example-busybox
      image: k8s.gcr.io/busybox
      command: [ "/bin/sh", "-c", "ls /etc/config/" ]
      volumeMounts:
      - name: config-volume
        mountPath: /etc/config

  volumes:
    - name: config-volume
      configMap:
        # Provide the name of the ConfigMap containing the files you want
        # to add to the container
        name: special-config
  restartPolicy: Never
````

**Note**: A ConfigMap can only be referenced by pods residing in the same namespace



