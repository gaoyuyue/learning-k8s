# Labels

## 1. 什么是labels？

 标签是可以附加到资源的任意键值对

## 2. labels有什么用?

用以选择具有该确切标签的资源

## 3. 请分别通过yaml文件和command，给任意pod加上以下标签：hello-label=world

**cmd: **

```shell
kubectl label po kubia-demo hello-label=world
```

**yaml:**

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: kubia-demo
  labels:
    hello-label: world
spec:
  containers:
    - image: luksa/kubia
      name: kubia
      ports:
        - containerPort: 8080
          protocol: TCP
```



## 4. 请分别通过yaml文件和command，将上述标签修改为：hi-label=universe

**cmd:**

```shell
kubectl label po kubia-demo hi-label=universe --overwrite
```

**yaml:**

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: kubia-demo
  labels:
    hi-label: universe
spec:
  containers:
    - image: luksa/kubia
      name: kubia
      ports:
        - containerPort: 8080
          protocol: TCP
```



## 5. 请使用command，查询：

- 含有标签"hi-label"的所有pod

  ```shell
  kubectl get po -l hi-label
  ```

  

- 不含有标签"hi-label"的所有pod

  ```shell
  kubectl get po -l '!hi-label'
  ```

  

- 含有标签"hi-lable"且值为"universe"的所有pod

  ```shell
  kubectl get po -l hi-label=universe
  ```

  

- 含有标签"hi-lable"且值不为"universe"的所有pod

  ```shell
  kubectl get po -l hi-label!=universe
  ```

  

##  6. 请使用command删除含有标签"hi-label"的所有pod

```shell
kubectl delete pods -l hi-label 
```



