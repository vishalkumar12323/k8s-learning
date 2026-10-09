# Kubernetes - Labels and Selectors

Labels and selectors are one of the most important concepts in Kubernetes because they allow Kubernetes resources to identify and work with groups of Pods.

## What are Labels?

### A Label is a key-value pair that we attach to a kubernetes object, most commonly a Pod.

For Example:

```bash
labels:
    app: nginx
```

It means:

- This pod belongs to the nginx application.

### Create Label using simple nginx pod.

nginx-label-pod.yml

```bash
apiVersion: v1
kind: Pod

metadata:
  name: nginx-label-pod
  labels:
    app: nginx
    environment: development

spec:
  containers:
    - name: nginx
      image: nginx
```

A Pod can have multiple labels:

```bash
app: nginx
environment: development
version: v2
```

Create a Pod with label

```bash
kubectl apply -f nginx-label-pod.yml
```

Check the Pod

```bash
kubectl get pods
```

Inspect Pod labels:

```bash
kubectl get pods nginx-label-pod --show-labels
```

### Querying Pods using label

Show me Pods whose label app is nginx

```bash
kubectl get pods -l app=nginx
# or
kubectl get pods -l environment=development
```
