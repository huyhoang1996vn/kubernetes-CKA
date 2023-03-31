
create pod

kubectl run nginx --image=nginx --dry-run=client -o yaml > nginx-pod.yaml

describe pod

kubectl describe pods nginx