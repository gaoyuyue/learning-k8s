# Pod

# 1. 什么是node？

一台装有操作系统的物理机或虚拟机

```shell
kubectl explain nodes
```

## 2. 什么是pod?

运行在同一个节点，同一个Linux命名空间中的一组紧密相关的容器

```shell
kubectl explain pods
```



## 3. pod和node是什么关系？

一对多，一个node上可以运行多个pod，一个pod只能运行在一个node上

## 4. pod和docker container是什么关系？

一个pod包含一个或多个docker container

# Question

## 1. 当前集群有几个node?

```shell
kubectl get nodes
```

## 2. 当前集群有几个pod？

```shell
kubectl get pods --all-namespaces
```

## 3.  怎么查询asp.net core app所在的pod运行在哪个node上？

```shell
kubectl describe pod <pod-name>

kubectl get pods -o wide
```





