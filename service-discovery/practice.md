# A Service is an abstract way to expose an application running on a set of Pods as a single network service
### Imagine an application with two services
- Frontend: React application
- Backend: Node.js + Express API
backend runs inside a Kubernetes Pod. The frontend needs to send HTTP requests to it.
The problem is that Pod IP addresses can change when Pods are recreated or rescheduled. If frontend connects directly to a Pod IP, that connection may stop working.

Kubernetes solves this with a Service.