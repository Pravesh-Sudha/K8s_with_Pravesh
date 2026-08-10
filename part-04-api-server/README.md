# K8s with Pravesh — Episode 04: Kubernetes API Server

In Episode 4 of **K8s with Pravesh**, we dive into one of the most important components of the Kubernetes Control Plane—the **API Server**.

Whenever you run a command like:

```bash
kubectl apply -f deployment.yaml
```

what actually happens behind the scenes?

This episode follows the complete journey of a request—from `kubectl` to the API Server—and explores how Kubernetes exposes its REST APIs, validates requests, stores the cluster's desired state, and becomes the central communication hub for every Kubernetes component.

---

## 📚 What You'll Learn

- What is the Kubernetes API Server?
- Why is it the heart of the Kubernetes Control Plane?
- How `kubectl` communicates with the API Server
- The lifecycle of a `kubectl apply` request
- Authentication & Authorization
- Admission Controllers
- Kubernetes REST APIs
- Core API vs Named API Groups
- How the API Server stores cluster state in etcd
- Why every Kubernetes component communicates through the API Server

---

## 📂 Project Structure

```
part-04-api-server/
├── deployment.yml
└── README.md
```

---

## 🚀 Getting Started

Clone the repository:

```bash
git clone https://github.com/Pravesh-Sudha/K8s_with_Pravesh.git
```

Navigate to Episode 4:

```bash
cd K8s_with_Pravesh/part-04-api-server
```

Deploy the sample application:

```bash
kubectl apply -f deployment.yml
```

Verify the Deployment:

```bash
kubectl get deployments
```

Verify the Pods:

```bash
kubectl get pods
```

---

## 🔍 Exploring the Kubernetes API Server

Start a local proxy to communicate with the Kubernetes API Server:

```bash
kubectl proxy
```

Now open the following endpoints in your browser.

### Discover the Core API

```
http://localhost:8001/api
```

### Explore Core Kubernetes Resources

```
http://localhost:8001/api/v1
```

Here you'll find resources such as:

- Pods
- Services
- ConfigMaps
- Secrets
- Namespaces
- Nodes
- Persistent Volumes
- Persistent Volume Claims

---

### View Running Pods Through the API

```
http://localhost:8001/api/v1/namespaces/default/pods
```

Notice how the same information returned by:

```bash
kubectl get pods
```

is actually fetched from the Kubernetes API Server.

---

### Explore Kubernetes API Groups

```
http://localhost:8001/apis
```

You'll discover additional API Groups such as:

- apps
- batch
- autoscaling
- networking.k8s.io
- rbac.authorization.k8s.io
- storage.k8s.io

For example, Deployments belong to the **apps** API Group:

```
http://localhost:8001/apis/apps/v1
```

This is why Deployment manifests use:

```yaml
apiVersion: apps/v1
```

while Pods use:

```yaml
apiVersion: v1
```

---

## 📖 Blog

Read the complete article:

🔗 **API Server Explained Like Never Before**

https://medium.com/devops-dev/api-server-explained-like-never-before-episode-4-56cc6ce090e8)

---

## 🎥 YouTube Video

Watch the complete walkthrough:

[![Watch the video](https://youtube.com)](https://youtu.be/IjN0IO6Ie-U)

---

## 🧠 Key Takeaways

- The API Server is the central communication hub of Kubernetes.
- Every Kubernetes component communicates through the API Server.
- `kubectl` is simply a client that sends HTTPS requests to the API Server.
- The API Server authenticates, authorizes, validates, and stores every Kubernetes object.
- Kubernetes exposes everything as REST APIs, which you can explore using `kubectl proxy`.

---

## 📺 K8s with Pravesh Series

| Episode | Topic | Status |
|----------|-------------------------------|--------|
| Episode 01 | Deployments & Services | ✅ |
| Episode 02 | StatefulSets | ✅ |
| Episode 03 | ConfigMaps & Secrets | ✅ |
| Episode 04 | Kubernetes API Server | ✅ |
| Episode 05 | Coming Soon | 🚧 |

---

## 🤝 Connect With Me

🌐 **Website:** https://praveshsudha.com

📝 **Blog:** https://blog.praveshsudha.com

💼 **LinkedIn:** https://www.linkedin.com/in/pravesh-sudha/

🐦 **X (Twitter):** https://x.com/praveshstwt

📺 **YouTube:** https://www.youtube.com/@pravesh-sudha

💻 **GitHub:** https://github.com/Pravesh-Sudha

---

⭐ If you found this project helpful, consider giving the repository a **Star** and following the **K8s with Pravesh** series for more deep dives into Kubernetes internals!