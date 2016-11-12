Some simple sample config to run test sshd containers.

Log into them as root:root

Quick launch:

```shell
kubecfg -p 31001:22 run rastasheep/ubuntu-sshd 1 sshd-test-controller
kubectl get pods | grep sshd-test-controller
ssh root@${ip_of_host} -p 31001
```

Cluster launch:

```shell
kubectl create -f sshd-controller.yaml
kubectl expose deployment --type=NodePort sshd 
kubectl get services | grep ssh
ssh root@${service_ip} -p{service_port
```

Use kubectl from within minikube cluster:

```shell
mkdir ~/.kube
cat config >~/.kube
kubectl config set-credentials minikube --token=$(cat /var/run/secrets/kubernetes.io/serviceaccount/token)
kubectl cluster-info
```
