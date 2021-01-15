# Documentation

More information is provided in the README.md file of each microservice

## NGINX Ingress

Installing:

```bash
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
helm install nginx-ingress ingress-nginx/ingress-nginx
```

Checking status:

```bash
kubectl --namespace default get services -o wide -w nginx-ingress-ingress-nginx-controller
```
