# Namespace

## 1. 什么是namespace？

namespace 是Kubernetes提供的组织机制，用于给集群中的任何对象组进行分类、筛选和管理

## 2. namespace有什么用？

> <http://dockone.io/article/8590>

## 3. 请分别通过yaml文件和command，创建一个名为world的namespace

**cmd:**

```shell
kubectl create namespace world
```

**yaml:**

```yaml
apiVersion: v1
kind: Namespace
metaData:
	name: world
```

```shell
kubectl create -f world.yml
```

## 4. 请分别通过yaml文件和command，创建一个pod使其隶属于上述创建的namespace

```shell
kubectl create -f kubia-demo.yml -n world
```

```yaml
apiVersion: v1
kind: Pod
metaData: 
	name: kubia-demo
	namespace: world
spec:
	containers:
	  - image: luksa/kubia
		name: kubia
        prots:
         - containerPort: 8080
           protocol: TCP
```



## 5. 请分别通过yaml文件和command，将上述namespace的名字修改为universe ???

```shell

```

```yaml

```



## 6. 请使用command，查询所有namespace

```shell
kubectl get ns
```



## 7. 请使用command，查询universe中的所有pod

```shell
kubectl get po -n universe
```



## 8. 请使用command，删除universe中的所有pod，但保留该namespace

```shell
# kubectl delete po --all -n universe
kubectl delete all --all -n universe
```

