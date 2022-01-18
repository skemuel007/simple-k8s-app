# Simple Kubernetes MiniKube Deployment
Build application.

```console
minikube `docker-env`
docker build -t [docker-registry-username]/first-app:v1 .
```

Push Image to docker registry
**Note:** Must have docker registry account
```console
docker push [docker-registry-username]/first-app:v1
```

Test application in Docker.

```console
docker run -d -p 8000:80 [docker-registry-username]/first-app:v1
curl `minikube ip`:8000
```

Test application locally with Minikube.

```console
kubectl -n default apply -f k8s
curl `minikube service -n default first-app --url`
```

_where `k8s` is the folder containing deployment and service yaml files respectively_

Check pods and services
```console
kubectl -n default get pods
kubectl -n default get services
```