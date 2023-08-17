# Lets Encrypt Installation

- Install CRD must this first
```bash
kubectl get crd | grep cert-manager.io
```

- Install CRDs according to version
```bash
kubectl apply -f https://github.com/jetstack/cert-manager/releases/download/v1.12.3/cert-manager.crds.yaml
```

```bash
helm repo add jetstack https://charts.jetstack.io
helm repo update
helm repo ls
helm search repo jetstack
helm search repo jetstack/cert-manager --versions
helm show values jetstack/cert-manager --version v1.12.3
helm show values jetstack/cert-manager --version v1.12.3 > cert-manager-values.yaml
helm upgrade --install cert-manager jetstack/cert-manager --version v1.12.3 --namespace cert-manager --create-namespace --values cert-manager-values.yaml
```

- Nginx Ingress https://www.youtube.com/watch?v=l5sofll5OBA&t=472s
