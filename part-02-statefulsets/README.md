# K8s with Pravesh — Episode 02: StatefulSets

In the second episode of **K8s with Pravesh**, we explore one of the biggest misconceptions in Kubernetes:

> **"Deployments lose data, StatefulSets preserve it."**

But is that actually true?

Through a hands-on demonstration using **MySQL**, **Persistent Volume Claims (PVCs)**, **Deployments**, and **StatefulSets**, we uncover the real purpose of StatefulSets and learn why they exist beyond just data persistence.

---

## 📚 What You'll Learn

- Understanding StatefulSets
- Deployment vs StatefulSet
- Persistent Volumes (PV) & Persistent Volume Claims (PVC)
- Why data survives even in a Deployment
- Stable Pod Identity
- Dedicated Storage per Replica
- When to use Deployments vs StatefulSets

---

## 📂 Project Structure

```
part-02-statefulsets/
├── configs/
│   ├── deployment.yml
│   ├── statefulset.yml
│   └── secrets-and-config.yml
└── README.md
```

---

## 🚀 Getting Started

Clone the repository:

```bash
git clone https://github.com/Pravesh-Sudha/K8s_with_Pravesh.git
```

Navigate to Episode 2:

```bash
cd K8s_with_Pravesh/part-02-statefulsets/configs
```

Apply the Secrets and ConfigMaps:

```bash
kubectl apply -f secrets-and-config.yml
```

### Deployment Demo

Deploy MySQL using a Deployment:

```bash
kubectl apply -f deployment.yml
```

Create a sample record, delete the Pod, and observe that the data still survives because the Persistent Volume Claim is reattached to the newly created Pod.

---

### StatefulSet Demo

Deploy MySQL using a StatefulSet:

```bash
kubectl apply -f statefulset.yml
```

Repeat the same experiment and observe:

- Data persists
- Pod identity remains the same (`mysql-0`)
- Each replica gets its own dedicated storage

---

## 📖 Blog

Read the complete article here:

🔗 **If Data Survives in Deployments, Why Do We Need StatefulSets?**

https://medium.com/@programmerpravesh/if-data-survives-in-deployments-why-do-we-need-statefulsets-70fc1f27f8c7

---

## 🎥 YouTube Video

Watch the complete walkthrough:

https://youtu.be/nSmIGlH9VN0

---

## 🧠 Key Takeaway

Many developers assume StatefulSets exist because Deployments cannot preserve data.

In reality, **Persistent Volume Claims (PVCs)** are responsible for data persistence.

StatefulSets solve a different problem by providing:

- ✅ Stable Pod identities
- ✅ Stable network identities
- ✅ Dedicated storage for each replica
- ✅ Ordered deployment and scaling

That's why databases and distributed systems such as MySQL, PostgreSQL, Kafka, ZooKeeper, and Elasticsearch are typically deployed using StatefulSets.

---

## 🤝 Connect With Me

🌐 Website: https://praveshsudha.com

📝 Blog: https://blog.praveshsudha.com

💼 LinkedIn: https://www.linkedin.com/in/pravesh-sudha/

🐦 X (Twitter): https://x.com/praveshstwt

📺 YouTube: https://www.youtube.com/@pravesh-sudha

💻 GitHub: https://github.com/Pravesh-Sudha

---

⭐ If you found this project helpful, consider giving the repository a **Star** and following the **K8s with Pravesh** series for more Kubernetes content!
