## Apply the app-config.yml and config-pod.yml manifest files
```bash
kubectl apply -f app-config.yml
kubectl apply -f config-pod.yml
```

### Inspect the result
```bash
kubectl get configmaps -n config-demo
kubectl describe configmap app-config -n config-demo

kubectl get pods -n config-demo
```

### Now Inspect the environment variables inside the container.
```bash
kubectl exec -n config-demo config-demo-pod -- printenv NODE_ENV
kubectl exec -n config-demo config-demo-pod -- printenv APP_NAME
kubectl exec -n config-demo config-demo-pod -- printenv LOG_LEVEL
```