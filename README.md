# Simple Kubernetes MiniKube Deployment
Build application.

```console
minikube `docker-env`
docker build -t [docker-registry-username]/first-app:v1 .
```

Test application in Docker.

```console
docker run -d -p 8000:80 [docker-registry-username]/first-app:v1
curl `minikube ip`:8000
```

Test application locally with Minikube.

```console
kubectl -n default apply -f kubernetes
curl `minikube service -n default first-app --url`