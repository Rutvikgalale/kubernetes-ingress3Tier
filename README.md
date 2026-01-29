# 🚀 3-Tier Application on Kubernetes

A simple **3-tier application** deployed on **Kubernetes (Minikube)** demonstrating service exposure using  
**ClusterIP, NodePort, LoadBalancer, and Ingress**.

---

## 🏗️ Architecture

Nginx (Frontend)
↓
Flask (Backend)
↓
MySQL (Database)

yaml
Copy code

---

## ⚙️ Tech Stack

- Kubernetes (Minikube)
- Nginx
- Python / Flask
- MySQL
- Docker
- Ingress Controller (NGINX)

---

## 📂 Components

- **Frontend**: Nginx Deployment + Service  
- **Backend**: Flask Deployment + Service  
- **Database**: MySQL Deployment + Service  
- **Ingress**: Host-based & Path-based routing

---

## 🚀 Deployment

```bash
kubectl apply -f namespace.yaml
kubectl apply -f .
Enable ingress:

bash
Copy code
minikube addons enable ingress
🌍 Access Methods
ClusterIP (Internal)
bash
Copy code
minikube ssh
curl http://<pod-ip>
NodePort
bash
Copy code
curl http://<minikube-ip>:30003   # Nginx
curl http://<minikube-ip>:30004   # Flask
LoadBalancer
bash
Copy code
minikube tunnel
curl http://<external-ip>
Ingress
Host-based

bash
Copy code
http://nginx.local
http://python.local
Path-based

bash
Copy code
http://<minikube-ip>/nginx
http://<minikube-ip>/python
