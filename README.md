![image](https://github.com/falahatme/argocd/assets/7458874/6266063b-d083-481c-bf24-0c196833b09e)

# Installing Argo-CD

## Deploy Argo-CD on kubernetes

```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

```
kubectl -n argocd get deployment
kubectl -n argocd get srvice
kubectl -n argocd get statefulset
```

## Install Argo-CD CLI on HOST

```
curl -sSL -o argocd-linux-amd64 https://github.com/argoproj/argo-cd/releases/latest/download/argocd-linux-amd64
sudo install -m 555 argocd-linux-amd64 /usr/local/bin/argocd
rm argocd-linux-amd64
argocd version --client
```

```
kubectl -n argocd get all
```

