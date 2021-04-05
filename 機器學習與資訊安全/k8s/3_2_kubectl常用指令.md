# Common kubectl Commands
```
Namespaces
Contexts
Viewing Kubernetes API Objects
Creating, Updating, and Destroying Kubernetes Objects
Labeling and Annotating Objects
Debugging Commands
Command Autocompletion
Alternative Ways of Viewing Your Cluster
```

```
Namespaces ==>  kubectl --namespace=mystuff


Contexts  ==> change the default namespace more permanently
   create a context ==> kubectl config set-context my-context --namespace=mystuff
   kubectl config use-context my-context

Viewing Kubernetes API Objects 
   ==> kubectl get pods my-pod -o jsonpath --template={.status.podIP}
       kubectl describe <resource-name> <obj-name>

Creating, Updating, and Destroying Kubernetes Objects

   Creating Kubernetes Objects ==> kubectl apply -f obj.yaml
   
   Updating Kubernetes Objects ==> kubectl apply -f obj.yaml 更新obj.yaml再執行一次

   Destroying Kubernetes Objects ==>
     kubectl delete <resource-name> <obj-name>
     kubectl delete -f obj.yaml

   kubectl edit <resource-name> <obj-name>

Labeling and Annotating Objects
   add the color=red label to a Pod named bar ==> kubectl label pods bar color=red
   remove a label ==>  kubectl label pods bar color-
   
Debugging Commands
   see the logs for a running container ==>  kubectl logs <pod-name>
   
   use the exec command to execute a command in a running container
     ==> kubectl exec -it <pod-name> -- bash
   
   attach to the running process ==> kubectl attach -it <pod-name>
   
   copy files to and from a container using the cp command
      ==> kubectl cp <pod-name>:</path/to/remote/file> </path/to/local/file>
      
   kubectl port-forward <pod-name> 8080:80
   
   see how your cluster is using resources ==> kubectl top nodes 
         kubectl top pods
         
Command Autocompletion
   # CentOS/Red Hat ==> yum install bash-completion
   # Debian/Ubuntu ==> apt-get install bash-completion


Alternative Ways of Viewing Your Cluster
```
