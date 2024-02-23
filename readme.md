## Start application with Docker, Minikube and Helm
```
docker compose --profile postgres build
minikube start
helm install spring-petclinic-app  ./spring-petclinic
minikube tunnel
```