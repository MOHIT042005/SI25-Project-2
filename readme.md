
---

## 🚀 CI/CD Flow

1. **Code Push to GitHub** triggers the GitHub Action
2. `tfsec` scans Terraform files
3. Docker image is built
4. `Trivy` scans the Docker image for vulnerabilities
5. If all passes, deployment can proceed

---

## 🔐 Sealed Secrets

- Created a Kubernetes `Secret` (`mysecret.yaml`)
- Encrypted it using `kubeseal` → `sealed-mysecret.yaml`
- Applied it to the cluster securely

---

## ✅ How to Run

```bash
# Clone the repo
git clone https://github.com/MOHIT042005/SI25-Project-2.git
cd DEVSECOPS-PROJECT

# Build the Docker image
cd app
docker build -t si25-task2-app .

# Apply sealed secret (only on Kubernetes cluster)
kubectl apply -f sealed-mysecret.yaml
