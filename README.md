# k8s-prestashop-mysql

## Getting Started with Kubernetes

### 🛠️ Setting Up the Stage

- **Initialize your Cluster:** First things first, let's get your cluster up and running. Run `kubeadm init`. This command is like starting the engine of your car – necessary before you can drive off.

### 📦 Deploying MySQL

- **Securing MySQL:** Time to keep your secrets safe. Use `kubectl create secret` to secure your MySQL creds.
- **MySQL, Deploy!** Write a MySQL deployment file (let’s call it `mysql-deployment.yaml`). Deploy it using `kubectl apply -f mysql-deployment.yaml` in your namespace.
- **Remember the Volumes:** Make sure your MySQL has a home for its data with volume configurations.

### 🛍️ Setting Up PrestaShop

- **PrestaShop Time:** Now, for PrestaShop. Same drill – create a deployment file and apply it.
- **Storage is Key:** Include Persistent Volume (PV) and Persistent Volume Claim (PVC) in your YAML.
- **Making it Public:** Use NodePort in your service YAML to let people access your PrestaShop from the outside world.

### 🎛️ Managing Your K8s Resources

- **Handle Your Pods:** Launch and manage pods with `kubectl run` or `kubectl apply`.
- **Keep Them in Line:** Use ReplicaSets to control how many copies of a pod you want running.
- **Connecting the Dots:** Create services with `kubectl expose` to let your pods talk to each other or the outside world.

### 🔍 Monitoring and Troubleshooting

- **Stay Informed:** Keep an eye on your pods with `kubectl get pods`, `kubectl describe pod <pod-name>`, and `kubectl logs <pod-name>`. It’s like checking on your pets to make sure they’re doing okay.

### ⚙️ Keeping Things Up-to-Date

- **Update Time:** Run `apt-get update && apt-get upgrade kubeadm`, then `apt-get update && apt-get upgrade kubelet kubectl` to keep your tools fresh.
- **Restart to Refresh:** Don’t forget to restart the kubelet service with `systemctl restart kubelet`.

### 🔄 Continuous Deployment with Flux CD and Helm

- **Auto-Deploy with Flux CD:** Set up Flux CD for hands-off deployment.
- **Package Management with Helm:** Use Helm to handle Kubernetes packages.
