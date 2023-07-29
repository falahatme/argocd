![image](https://github.com/falahatme/argocd/assets/7458874/6266063b-d083-481c-bf24-0c196833b09e)

# Installing Argo-CD

```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
kubectl -n argocd get deployment
```

