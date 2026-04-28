

## 1. Installing ArgoCD (Manifest Way)

If you are using a Cloud Provider (like AWS) that supports LoadBalancers, your `patch` command is correct. If you are on a local VM or a simple EC2, you might need to use `NodePort`.

### **Step 1: Create Namespace and Install**
```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

### **Step 2: Expose the UI**
If you want to use a specific port (like your 31894), it is better to use **NodePort**:
```bash
kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "NodePort"}}'
```

### **Step 3: Get the Admin Password**
```bash
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
```
*(Note: I added `; echo` at the end so the password appears on a new line in your terminal).*

---

## 2. Installing ArgoCD using Helm (Recommended)

In a real company, we almost always use **Helm**. It allows you to manage versions and customize settings (like the admin password or server ports) in one `values.yaml` file.

### **Helm Installation Commands:**

1.  **Add the Argo Repo:**
    ```bash
    helm repo add argo https://argoproj.github.io/argo-helm
    helm repo update
    ```

2.  **Install with Custom Settings:**
    You can install it and set the service type to `NodePort` or `LoadBalancer` immediately in one command:
    ```bash
    helm install my-argocd argo/argo-cd \
      --namespace argocd \
      --create-namespace \
      --set server.service.type=NodePort
    ```



---

## 3. Important Note on Ports & Public IP

You mentioned ports **31894** and **31567**. 

* **The Rule:** If you are using **AWS EC2**, you must go to your **Security Group** and add an **Inbound Rule** to allow traffic on those specific ports. If you don't open them in the AWS Console, the browser will never connect.
* **The URL:** Always use the HTTPS protocol because ArgoCD is secure by default: `https://13.234.117.21:31894`



Commit Date: 28-April-2026
