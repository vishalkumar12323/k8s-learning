## Checking Cluster status, and exisiting pods

```bash
minikube status
kubectl get pods -o wide # -o wide gives extra info
```

## Creating a dedicated Namesapce for the exercise

```bash
kubectl create namespace labels-lab
kubectl get namespace # verify namesapce
```

## Apply the manifest:

```bash
kubectl apply -f labels-lab.yml
```

## Checking the Pods with their labels:

```bash
kubectl get pods -n labels-lab --show-labels -o wide
```

## Practice Set

### find Frontend pods

```bash
kubectl get pods -n labels-lab -l "app=frontend"
```

### find Backend pods

```bash
kubectl get pods -n labels-lab -l "app=backend"
```
