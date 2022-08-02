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








