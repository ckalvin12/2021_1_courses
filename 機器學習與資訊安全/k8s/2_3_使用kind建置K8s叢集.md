# 使用kind建置K8s叢集
```
https://kind.sigs.k8s.io/docs/user/quick-start/#deleting-a-cluster
```

# 安裝kind
## windows
```
curl.exe -Lo kind-windows-amd64.exe https://kind.sigs.k8s.io/dl/v0.10.0/kind-windows-amd64

Move-Item .\kind-windows-amd64.exe c:\some-dir-in-your-PATH\kind.exe
```
## Linux
```
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.10.0/kind-linux-amd64
chmod +x ./kind
mv ./kind /some-dir-in-your-PATH/kind
```
# Creating a Cluster 
```
kind create cluster.
```
```
kind create cluster # Default cluster context name is `kind`.


kind create cluster --name kind-2
```
## Multi-node clusters
```
kind create cluster --config kind-example-config.yaml
```
```
# three node (two workers) cluster config
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
- role: worker
- role: worker
```
## Control-plane HA
```
# You can also have a cluster with multiple control-plane nodes:
# a cluster with 3 control-plane nodes and 3 workers

kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
- role: control-plane
- role: control-plane
- role: worker
- role: worker
- role: worker
```

# Interacting With Your Cluster
```

```
#
```
Deleting a Cluster ==>  kind delete cluster

Loading an Image Into Your Cluster ==> 
Docker images can be loaded into your cluster nodes with:
kind load docker-image my-custom-image-0 my-custom-image-1
```
