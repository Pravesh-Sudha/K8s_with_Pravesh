# 🚀 K8s with Pravesh — Part 01: Introduction to Kubernetes Deployments & Services

Welcome to the first part of the **K8s with Pravesh** series!
In this project, we deploy a simple **multi-tier application** using Kubernetes concepts like:

* Deployments
* Services
* Containerized Applications
* Internal Networking in Kubernetes

This part focuses on understanding how Kubernetes manages applications and enables communication between different components.

---

# 📺 Video Tutorial

Watch the complete walkthrough on YouTube:

[K8s with Pravesh — Part 01 YouTube Video](https://youtu.be/ZYlRwMf4lYA?si=bioWZV6WfohU2PNh&utm_source=chatgpt.com)

---

# 📝 Blog Post

Read the detailed beginner-friendly blog here:

[Kubernetes for Beginners — Deploying an NGINX + Node + Redis Application](https://blog.praveshsudha.com/kubernetes-for-beginners-deploying-an-nginx-node-redis-application?utm_source=chatgpt.com)

---

# 🏗️ Project Architecture

This project deploys a simple application composed of:

```text
NGINX  →  Node.js Backend  →  Redis
```

### Components

| Component | Purpose                    |
| --------- | -------------------------- |
| NGINX     | Reverse Proxy / Frontend   |
| Node.js   | Backend Application        |
| Redis     | In-memory Database / Cache |

---

# 📂 Repository Structure

```text
K8s_with_Pravesh/
└── part-01-introduction/
    ├── nginx/
    │   ├── deploy.yaml
    │   └── svc.yaml
    │
    ├── node/
    │   ├── deploy.yaml
    │   └── svc.yaml
    │
    └── redis/
        ├── deploy.yaml
        └── svc.yaml
```

---

# ⚙️ Kubernetes Concepts Covered

## 1️⃣ Deployments

Deployments help us:

* Manage Pods
* Scale applications
* Perform rolling updates
* Ensure high availability

Each component in this project has its own Deployment.

---

## 2️⃣ Services

Services provide:

* Stable networking
* Service discovery
* Communication between Pods

We use Kubernetes Services to allow:

* NGINX to communicate with Node.js
* Node.js to communicate with Redis

---

# 🚀 How to Run the Project

## Step 1 — Start Minikube

```bash
minikube start
```

---

## Step 2 — Apply Redis

```bash
kubectl apply -f redis/deploy.yaml
kubectl apply -f redis/svc.yaml
```

---

## Step 3 — Apply Node.js Backend

```bash
kubectl apply -f node/deploy.yaml
kubectl apply -f node/svc.yaml
```

---

## Step 4 — Apply NGINX

```bash
kubectl apply -f nginx/deploy.yaml
kubectl apply -f nginx/svc.yaml
```

---

# 🔍 Verify Resources

Check Pods:

```bash
kubectl get pods
```

Check Services:

```bash
kubectl get svc
```

---

# 🌐 Access the Application

If using Minikube:

```bash
minikube service nginx
```

This will open the application in your browser.

---

# 🧠 What You’ll Learn From This Part

By the end of this project, you’ll understand:

* How Kubernetes Deployments work
* How Services enable networking
* Pod-to-Pod communication
* Multi-container application architecture
* Basic Kubernetes workflow using `kubectl`

---

# 🔥 Upcoming Parts in the Series

Next parts of **K8s with Pravesh** may include:

* ConfigMaps & Secrets
* Monitoring & Observability
* Ingress Controllers
* Helm Charts
* GitOps with ArgoCD
* StatefulSets & Persistent Volumes
* Kubernetes Networking Deep Dive

---

# 👨‍💻 Connect With Me

* [Portfolio Website](https://praveshsudha.com)
* [LinkedIn](https://www.linkedin.com/in/pravesh-sudha)
* [YouTube Channel](https://www.youtube.com/@pravesh-sudha)
* [X / Twitter](https://x.com/praveshstwt?utm_source=chatgpt.com)

---

# ⭐ Support the Series

If you found this project helpful:

* Star the repository ⭐
* Share the blog/video 📢
* Subscribe to the YouTube channel 🚀

Happy Learning Kubernetes! ☸️
