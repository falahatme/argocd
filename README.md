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

## Use Argo-CD By CLI

```
# Expose argocd-server service
kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "NodePort"}}'
kubectl -n argocd get services
```

## Dashboard Password
```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d && echo 
```

```
kubectl port-forward svc/argcd-server -n argocd 8080:443
```

## Browse Dashboard

in browser: [clusterIP]:8080

default user: admin

## Change Argo-CD admin password using CLI

```
argocd login localhost:8080
argocd account update-password
```


# Deploy docker image with Argo-CD



