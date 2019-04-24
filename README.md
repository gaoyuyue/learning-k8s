# learning-k8s

## cmd

```shell
# 启动minikube
minikube start
# 查看cluster信息
kubectl cluster-info
# 查看当前cluster有几个node
kubectl get nodes
# 查看当前cluster有几个pod
kubectl get pods
# 获取node的详细信息
kubectl describe node <node-name>
# 获取pod的详细信息
kubectl describe pod <pod-name>
 
kubectl run <name> --image <image-name> --port <port> --generator=run/v1

kubectl expose rc <name> --type=LoadBalancer --name <service-name>


```

