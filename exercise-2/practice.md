## Apply the backend-deployment.yml
```bash
kubectl apply -f backend-deployment.yml
```

### Check rollout report progress.
```bash
kubectl rollout status backend/backend-deployment -n selector-demo
```
You would see "deployment "backend-deployment" successfully rolled out"

### Inspect the pods and their labels
```bash
kubeclt get pods -n selector-demo --show-labels
```

## Finding Pods using selectors
```bash
kubectl get pods -n selector-demo --selector app=backend
```

```bash
kubectl get pods -n selector-demo -l environment=production
```

Using multiple selectors:
```bash
kubectl get pods -n selector-demo -l "app=backend,environment=production"
```