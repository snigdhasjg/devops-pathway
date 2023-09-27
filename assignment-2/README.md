# Task
```
1. Install tfenv for terraform manager on your local machine ( I prefer this but if you have any other version manager feel free to use that )
2. Install helm client on your local machine
3. Install minikube or kind for local k8s cluster
4. Create local kubernetes cluster version 1.26 or 1.27
5. Learn what is helm package manager and basic of kubernetes like k8s architecture etc
6. Install kubectl cli
7. Install awscli
8. Create python virtualenv inside your code repository
	( 
	    pip install vitualenv
	    virtualenv venv
	    source venv/bin/activate
	)
9. Run command "pip list" to see the code dependencies and google command to create requirement.txt file from pip
10. Last but not least, setup pycharm, sublime text, vim, visual code if you don’t have these, each tool have its own need during development.
```
# Prerequisite
## Install `tfenv` & `terraform`
1. Install tfenv via brew `brew install tfenv`
2. Install latest tfenv via `tfenv install`
3. List the downloaded version `tfenv list`
4. Use & make it default version `tfenv use 1.5.7` _Note: Latest version will differ in future_

## Install kubernetes
Prerequisites: [Colima](https://github.com/abiosoft/colima)
1. Configure kubenetes version 1.27 using `colima template`.
2. Update the version `kubernetes.version` number from [K3s releases](https://github.com/k3s-io/k3s/releases), example `v1.27.6+k3s1`
3. Start kubernetes with `colima kubernetes start`

This will take sometime. Post this you should see `~/.kube/config` file configured with colima context

## Install other CLIs
1. awscli: `brew install awscli`
2. kubernetes-cli: `brew install kubernetes-cli`
3. helm: `brew install helm`

# Playground commands
## Viewing context 
with `kubectl config get-contexts`
```shell
CURRENT   NAME     CLUSTER   AUTHINFO   NAMESPACE
*         colima   colima    colima
```

## Listing initial pods 
with `kubectl get pods -A`
```shell
NAMESPACE     NAME                                     READY   STATUS    RESTARTS   AGE
kube-system   local-path-provisioner-957fdf8bc-tn6wr   1/1     Running   1          30h
kube-system   coredns-77ccd57875-wpdpr                 0/1     Running   1          30h
kube-system   metrics-server-54dc485875-fsz9p          0/1     Running   1          30h
```

## Get deployments
with `kubectl get deployments -A`
```shell
NAMESPACE     NAME                     READY   UP-TO-DATE   AVAILABLE   AGE
kube-system   local-path-provisioner   1/1     1            1           30h
kube-system   coredns                  1/1     1            1           30h
kube-system   metrics-server           1/1     1            1           30h
```

# Understanding Pip
## Create virtual environment
1. Run `pip install --upgrade virtualenv` to install.
    > Had to use `--upgrade` flag due to some error in finding virtualenv distribution
    > https://stackoverflow.com/a/55620248
2. Create a virtual env with `virtualenv venv`. This will create a `venv` directory in the current working directory.
3. To activate the newly created virtual env `source venv/bin/activate`

> ### To Clean
> There is no command for deleting your virtual environment.
> Simply deactivate it and rid your application of its artifacts by recursively removing it.
> ```shell
> deactivate
> rm -rf venv
> ```

## Pip freeze
- Install any module/library
e.g. `pip install fastapi uvicorn`
- Do `pip list` to see all the downloaded libraries along with its' dependent libraries
- Create [requirements.txt](./requirements.txt) using pip `pip freeze > requirements.txt` 

