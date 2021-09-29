# Setup
Minikube v1.23.2
Kubernetes 1.22

###Minikube upgrade:
```
sudo minikube delete
curl -Lo minikube https://storage.googleapis.com/minikube/releases/v1.3.1/minikube-linux-amd64 && chmod +x minikube && sudo cp minikube /usr/local/bin/ && rm minikube
sudo minikube start --vm-driver=none
```


###Tekton objects
```
kubectl apply --filename https://storage.googleapis.com/tekton-releases/pipeline/latest/release.notags.yaml
```

###Tekton cli

```
curl -LO https://github.com/tektoncd/cli/releases/download/v0.20.0/tektoncd-cli-0.20.0_Linux-64bit.deb
sudo dpkg -i ./tektoncd-cli-0.20.0_Linux-64bit.deb
```

###Tekton dashboard
```
kubectl apply --filename https://github.com/tektoncd/dashboard/releases/latest/download/tekton-dashboard-release.yaml`
kubectl proxy --port=8080
localhost:8080/api/v1/namespaces/tekton-pipelines/services/tekton-dashboard:http/proxy/
kubectl --namespace tekton-pipelines port-forward svc/tekton-dashboard 9097:9097
```
