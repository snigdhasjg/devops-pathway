# Task
```
1. Create a hello world application GET API in fastapi ( python framework )
2. Create a public git repo and push your code in the github
3. Setup local docker desktop ( or any alternative local docker tool )
4. Dockerized the above application and run locally.
```

# How to run
Assuming you are inside [assignment-1](.) directory

1. Build the docker image using `docker buildx build -t hello-world:1.0 .`
2. Run the docker image in detach mode `docker run --name hello-world-container -p "8080:80" -d hello-world:1.0`

## Cleanup
1. Remove the docker container once done `docker rm -f hello-world-container`
2. Remove image with `docker image rm hello-world:1.0`

<details>
<summary>All things at once</summary>

```shell
# Run
docker buildx build -t hello-world:1.0 .
docker run --name hello-world-container -p "8080:80" -d hello-world:1.0

# cleanup
docker rm -f hello-world-container
docker image rm hello-world:1.0
```
</details>

# Useful links
- https://fastapi.tiangolo.com/#Installation