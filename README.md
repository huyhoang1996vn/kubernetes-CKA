
describe pod
kubectl get pods
kubectl describe pods nginx
kubectl run nginx --image=nginx --dry-run=client -o yaml > nginx-pod.yaml


describe deploy
kubectl get deploy
kubectl delete deploy <deployment name>
kubectl create deployment nginx-depl --image=nginx:1.19 --dry-run=client -o yaml > nginx-deploy-rollout.yaml
kubectl describe deploy nginx

rollout: recreate, rolling update, rollback
kubectl rollout status deployment/myapp-deployment
kubectl rollout undo deployment/myapp-deployment


replica-set
kubectl get rs

service
kubectl create service loadbalancer my-lbs --tcp=5678:8080  --dry-run=client -o yaml > nginx-svc-loadbalancer.yaml
kubectl get svc
kubectl describe svc nginx


get ip node 
kubectl get nodes --output wide
kubectl get service -o wide

gcloud compute firewall-rules create test-node-port --allow tcp:30081


kubectl apply -f services/svc-nginx-np.yaml
kubectl apply -f services/svc-nginxloadbalance.yaml


current server
kubectl apply -f services/svc-nginxloadbalance.yaml
kubectl apply -f deployments/dash-deployment.yaml
kubectl apply -f services/svc-dash-loadbalance.yaml
kubectl apply -f ingress/dash-nginx.yaml



#Update Kubernetes version

apt-cache madison kubeadm

apt-get upgrade -y kubeadm=1.26.0-00

kubeadm upgrade apply v1.26.0 --ignore-preflight-errors all

apt install kubelet=1.26.0-00

node
https://kubernetes.io/docs/tasks/administer-cluster/kubeadm/kubeadm-upgrade/
apt-mark unhold kubelet kubectl && \
apt-get update && apt-get install -y kubelet=1.26.0-00 kubectl=1.26.0-00 && \
apt-mark hold kubelet kubectl
