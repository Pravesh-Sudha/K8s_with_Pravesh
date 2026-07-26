# K8s with Pravesh - Episode 3

# What Really Happens When You Run `kubectl apply`?

> Ever wondered what happens after you run `kubectl apply -f deployment.yaml`? This episode takes you behind the scenes and traces the complete journey of a Kubernetes Deployment—from your terminal to a running container inside the cluster.

---

## 📺 Watch the Video

**YouTube:**  
https://youtu.be/<VIDEO_LINK>

---

## 📝 Read the Blog

https://dev.to/aws-builders/what-really-happens-when-you-run-kubectl-apply-episode-3-22kp

---

## 📚 Series Playlist

Follow the complete **K8s with Pravesh** series:

https://youtube.com/playlist?list=PLlens1h3v6tf1apwqaJDYjtdry-uFTUH2&si=8cwr0bJ7ba7EPXOk

---

## 🚀 What You'll Learn

In this episode, we'll answer one simple question:

> **What really happens when we run `kubectl apply`?**

Instead of just deploying an application, we'll dive into Kubernetes internals and understand how different control plane components work together.

Topics covered:

- How `kubectl` communicates with the cluster
- Kubernetes API Server
- ETCD and Desired State
- Controller Manager
- Deployment Controller
- ReplicaSet Controller
- Kubernetes Scheduler
- Kubelet
- Container Runtime (containerd)
- Complete workflow of `kubectl apply`

---

## 🏗️ Workflow Covered

```text
kubectl apply
        │
        ▼
  API Server
        │
        ▼
      ETCD
        │
        ▼
Controller Manager
        │
        ▼
   Deployment
        │
        ▼
   ReplicaSet
        │
        ▼
      Pods
        │
        ▼
   Scheduler
        │
        ▼
 Worker Node
        │
        ▼
    Kubelet
        │
        ▼
 Container Runtime
        │
        ▼
 Running Container
```

---

## 🎯 Prerequisites

This episode assumes you already understand:

- Pods
- Deployments
- StatefulSets
- Services

If not, start with the previous episodes in the playlist.

---

## 📂 Repository Structure

```text
episode-03/
│
├── README.md
├── diagrams/
│   ├── kubectl-apply-workflow.png
│   └── architecture.png
│
├── manifests/
│   └── deployment.yaml
│
└── assets/
```

*(Update the structure based on the files in your repository.)*

---

## 💡 Key Takeaways

- `kubectl` doesn't create Pods directly.
- Every request first reaches the API Server.
- ETCD stores the desired state of the cluster.
- Controllers continuously reconcile the desired and current state.
- Deployments create ReplicaSets, and ReplicaSets create Pods.
- The Scheduler chooses the best node for pending Pods.
- Kubelet communicates with the container runtime to start containers.
- Kubernetes works through continuous reconciliation rather than magic.

---

## 📖 Recommended Resources

- Kubernetes Documentation
- Kubernetes Components
- Kubernetes Architecture
- Kubernetes the Hard Way
- Kubernetes in Action (Second Edition)

---

## 🤝 Connect With Me

🌐 **Blog**  
https://blog.praveshsudha.com

💼 **LinkedIn**  
https://linkedin.com/in/praveshsudha

🐦 **X (Twitter)**  
https://x.com/praveshstwt

💻 **GitHub**  
https://github.com/Pravesh-Sudha

📺 **YouTube**  
https://www.youtube.com/@PraveshSudha

---

## ⭐ Support the Series

If you found this project helpful:

- ⭐ Star this repository
- 👍 Like the video
- 📺 Subscribe to the YouTube channel
- 🔁 Share it with fellow Kubernetes learners

---

## 📚 K8s with Pravesh

A beginner-friendly series focused on understanding **how Kubernetes works under the hood**, rather than just memorizing commands.

See you in the next episode!

**Happy Learning! 🚀**
