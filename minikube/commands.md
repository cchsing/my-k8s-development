# Minikube Commands
```bash
kubectl get nodes
kubectl get pods
kubectl get pods -A
kubectl get services
kubectl create deployment <deployment-name> --image=<image-name>
kubectl create deployment nginx-1 --image=nginx
kubectl delete deployment nginx-1
kubectl get replicasets
kubectl edit deployment <deployment-name>
kubectl edit deployment nginx-1
kubectl logs <pod-name>
kubectl describe <resource-type> <resource-name>
kubectl describe pods <pod-name>
kubectl describe deployments nginx-1
kubectl exec -it <pod-name> -- bin/bash
kubectl exec -it mongo-1-75d69d7f45-cv9jz -- bin/bash
kubectl get deployments
kubectl apply -f <configuration-file>
kubectl apply -f nginx-1.deploy.yaml
kubectl delete -f nginx-1.deploy.yaml
kubectl get pod -o wide
kubectl get deployment nginx-deployment -o yaml
echo -n 'username' | base64
kubectl get secrets
minikube service mongo-express-service
kubectl create namespace my-namespace
kubectl api-resources --namespaced=false
kubectl api-resources --namespaced=true
apt install kubectx
kubens my-namespace
```