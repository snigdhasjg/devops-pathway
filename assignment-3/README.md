# Task
```
1. Create a local kubernetes cluster using minikube or kind.
2. Use Kubectl for the following operation
	2.1 Check the current context and set the context to local cluster if not set.
	2.2 Check the number of namespace in the cluster
	2.3 Check the pods in namespace kube-system
	2.4 Check the deployments in namespace in kube-system
	2.5 Check the services in the namespace in kube-system
	2.6 Check the dameon-set in the namespace in kube-system
	
3. Learn what is helm chart ?
4. Browse artifacthub.io and see the public which helm chart publish on the portal.
5. Deploy nginx community helm chart by following instruction from artifacthub.io
6. Create custom helm chart in your service repository.
7. Deploy your custom helm chart in local cluster.
```

# How to run

## To create/update
```shell
helm upgrade --create-namespace -n world-apps -i hello-world-api ./helm
```

## To delete
```shell
helm uninstall -n world-apps hello-world
```
