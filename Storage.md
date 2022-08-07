# Storage

#### Pods are ephemeral and stateless
* How can data persist throughout lifecycle of Pod?
* How can data persist beyond life-cycle of Pod?
* How can containers share files between containers in Pod?

### Volumes bring persistence to Pod

#### Advantages of Kubernetes Volumes vs. Docker Volumes
* Once we attach Volume to a Pod, all the containers running in that Pod has access to it
* Volumes are associated with Lifecycle of Pod. But in Docker Volumes are associated with Lifecycle of Container
* When containers in Docker restarts, Data inside the Volume will be erased where as in Pod data is preserved across container restarts
* Kubernetes supports multiple volume types

#### Volume Types
<table>
  <tr><td><b>Ephemeral</b></td><td>Same lifetime as pods</td></tr>
  <tr><td><b>Durable</b></td><td>Beyond pods lifetime</td></tr>
</table>

