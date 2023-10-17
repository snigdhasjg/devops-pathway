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

# Useful links
- https://github.com/marketplace/actions/configure-aws-credentials-action-for-github-actions
- https://github.com/marketplace/actions/amazon-ecr-login-action-for-github-actions
- https://github.com/marketplace/actions/build-and-push-docker-images
- https://github.com/marketplace/actions/helm-tool-installer