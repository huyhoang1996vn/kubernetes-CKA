
create pod

kubectl run nginx --image=nginx --dry-run=client -o yaml > nginx-pod.yaml

describe pod

kubectl describe pods nginx

describe deploy
kubectl get deploy

replica-set
kubectl get rs

kubectl get svc


get ip node 
kubectl get nodes --output wide
kubectl get service -o wide

gcloud compute firewall-rules create test-node-port --allow tcp:30081


kubectl apply -f services/svc-nginx-np.yaml
kubectl apply -f services/svc-nginxloadbalance.yaml

kubectl apply -f services/svc-nginxloadbalance.yaml

kubectl apply -f deployments/dash-deployment.yaml
kubectl apply -f services/svc-dash-loadbalance.yaml


