# Multiple Replicas in Kubernetes ☸️
## What are multiple replicas?
- ### Running multiple Pod/Containers of the same application
- Imagine: A backend API application runs on only one Pod, What happen if that Pod craches, The application may become unavailable until Kubernetes replaces the Pod and the application becomes ready again.
Instead, we can run three replicas of the same application.

`Important: Multiple replicas improve availability and capacity, but they don't guarantee zero downtime. Your application, Service, readiness probes, and cluster infrastructure must also be configured appropriately.`

## What is a ReplicaSet?
- ### Kubernetes uses a controller called a ReplicaSet to maintain a specified number of Pod replicas.

`ℹ️ In real applications, we generally create a Deployment, which manages ReplicaSets for us.`

## Hands on: Running three Nginx replicas.

