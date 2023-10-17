# Task
```
1. Manually create docker and Helm repository for your service in AWS ECR ( ee-test-account )
2. Create Github Action pipeline to do following task
	2.1  Checkout your git repo
	2.2  Run unit tests
	2.3  Build docker image
	2.4  Publish docker image to ecr
	2.5  Build Helm Chart
	2.5  Push Helm chart to ecr
3. On local machine, login to ecr using aws cli and docker login
   and pull docker image from remote repository.
4. Deploy helm chart from ecr to your local minikube/kind cluster ( not the local helm chart)
```

# ECR setup on local
## Docker login
```shell
aws ecr get-login-password \
	--region ap-south-1 | docker login \
	--username AWS \
	--password-stdin 889772146711.dkr.ecr.ap-south-1.amazonaws.com
```

## Helm login
```shell
aws ecr get-login-password \
     --region ap-south-1 | helm registry login \
     --username AWS \
     --password-stdin 889772146711.dkr.ecr.ap-south-1.amazonaws.com
```

# Helm deploy
```shell
helm upgrade -i snigdhajyoti-hello-world \
	oci://889772146711.dkr.ecr.ap-south-1.amazonaws.com/snigdhajyoti-joe-microservices-helm \
	--version "0.1.0" \
	--create-namespace \
	--namespace world-apps \
	--set image.repository=889772146711.dkr.ecr.ap-south-1.amazonaws.com/snigdhajyoti-hello-world \
    --set image.tag=1.0-arm \
	--set image.pullPolicy=IfNotPresent
```

# Useful links
- https://github.com/marketplace/actions/configure-aws-credentials-action-for-github-actions
- https://github.com/marketplace/actions/amazon-ecr-login-action-for-github-actions
- https://github.com/marketplace/actions/build-and-push-docker-images
- https://github.com/marketplace/actions/helm-tool-installer
- https://docs.aws.amazon.com/AmazonECR/latest/userguide/push-oci-artifact.html

