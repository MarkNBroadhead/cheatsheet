# Kubernetes Cheatsheet

# Authentication & Switching Clusters
* `kubectl config use-context` switch context
* `kubectl config current-context` get name of current context
* `kubectl config get-clusters` list all k8s clusters currently in config file
* `kubectl config get-contexts` list all contexts, showing active context too
* `kubectl config rename-context <ugly_long_name> <shortName>` Rename context name for easier switching

# Pods
* `kubectl describe pod <pod id>` Get info on pod
* `kubectl exec -it <pod id> -- /bin/bash` SSH into pod
* `kubectl create -f https://k8s.io/examples/application/shell-demo.yaml` create pod
* `kubectl get pod shell-demo` get pod info
* `kubectl exec -it shell-demo -- /bin/bash` get shell into running container
