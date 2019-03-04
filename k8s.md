# Kubernetes Cheatsheet

* `kubectl describe pod <pod id>` Get info on pod
* `kubectl exec -it <pod id> -- /bin/bash` SSH into pod
* `kubectl create -f https://k8s.io/examples/application/shell-demo.yaml` create pod
* `kubectl get pod shell-demo` get pod info
* `kubectl exec -it shell-demo -- /bin/bash` get shell into running container
