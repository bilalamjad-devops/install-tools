

```argocd
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```


```argocd
kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'
```

```argocd
kubectl get svc argocd-server -n argocd
```

My ports are 31894 and 31567, so I need to open the ports of my server:

Access ArgoCD UI:

Open your browser and go to <servier-publicIP>:<service-port>., 13.234.117.21:31894 or 13.234.117.21:31567:

```argocd
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```

- Username: admin
- Password: (The password retrieved from the command above)

Commit Date: 28-April-2026
