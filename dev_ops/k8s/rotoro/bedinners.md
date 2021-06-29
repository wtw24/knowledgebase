# k8s - Course kubernetes for beginners

## Links:

- https://www.youtube.com/playlist?list=PLxeQ-jZjcEf0KXOA7jDJBNoWCCaB-glRo
- play-with-k8s.com
- katacoda.com
- rotoro.cloud


## 04. Kubernetes for absolute beginners with practice tests - Architecture

~~~
kubectl run hello-minikube
kubectl cluster-info
kubectl get nodes -owide
~~~

## Лабораторная №1

- https://rotoro-cloud.github.io/Coruse-Rotoro/
- https://katacoda.com/embed/rotoro-cloud/kubernetes-for-beginners-ru/?v=2&embed=true&ui=inline&host=rotoro-cloud.github.io&url=https%3A%2F%2Frotoro-cloud.github.io%2FCoruse-Rotoro%2F&target=katacoda-scenario-1&nonce=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWJlZCI6dHJ1ZSwiZG9tYWluIjoiaHR0cHM6Ly9yb3Rvcm8tY2xvdWQuZ2l0aHViLmlvLyIsImlwIjoiMmEwMjo5MDg6MzcxMTo5YjIwOjlmZmE6Njk2ZTpjYTU0OjUyYjEiLCJpYXQiOjE2MjQ5NTE2MTEsImV4cCI6MTYyNDk1MTY0MX0.twUDjbCzGtWpzB0vRmZAca7ScDy0FLsc6maeiYQytho&color=004d7f&hideintro=false&externalcss=https%3A%2F%2Fraw.githubusercontent.com%2Frotoro-cloud%2Frotoro-cloud.github.io%2Fmaster%2FlabEnv.css

## Minikube Install

- Ubuntu 64-bit
- 4GB RAM
- 30 GB VDI

### Install kubectl on Linux

- https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/
~~~
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

# Validate
curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
echo "$(<kubectl.sha256) kubectl" | sha256sum --check

sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

kubectl version --client
~~~

### Install minikube

- https://minikube.sigs.k8s.io/docs/start/
- https://minikube.sigs.k8s.io/docs/handbook/

~~~
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

minikube start --driver=docker

docker ps
minikube status
kubectl get po -A

kubectl create deployment hello-minikube --image=k8s.gcr.io/echoserver:1.4
kubectl expose deployment hello-minikube --type=NodePort --port=8080
kubectl get svc 
minikube service hello-minikube

# clear
kubectl delete pods --all
kubectl delete services --all
kubectl get all

minikube stop
~~~