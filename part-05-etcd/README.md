# Create the deployment
kubectl create deployment nginx-demo --image=nginx --replicas=3

# Query Etcd for specific Namespace
kubectl exec -n kube-system etcd-minikube -- sh -c "ETCDCTL_API=3 etcdctl \
  --endpoints=https://127.0.0.1:2379 \
  --cacert=/var/lib/minikube/certs/etcd/ca.crt \
  --cert=/var/lib/minikube/certs/etcd/server.crt \
  --key=/var/lib/minikube/certs/etcd/server.key \
  get /registry/deployments/default/nginx-demo --write-out=fields" | grep -E "Key|Value" | strings


## Inspecting raw object and it's revision
kubectl exec -n kube-system etcd-minikube -- sh -c "ETCDCTL_API=3 etcdctl \
  --endpoints=https://127.0.0.1:2379 \
  --cacert=/var/lib/minikube/certs/etcd/ca.crt \
  --cert=/var/lib/minikube/certs/etcd/server.crt \
  --key=/var/lib/minikube/certs/etcd/server.key \
  get /registry/deployments/default/nginx-demo --write-out=json" | jq


## Changin the Revision
kubectl set image deployment/web-app nginx=nginx:1.25 --namespace=nginx-demo

