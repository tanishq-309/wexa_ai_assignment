This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).
## Readme.md
## Next.js Docker & minikube/kubernetes Deployment
This project demonstrate how to containerize a Next.js application, build a docker image and push it to GitHub Container Registry (GHCR) via GitHub Actions Workflows and deploy it on minikube/kubernetes.

## Requirements:
node.js and npm
docker
minikube
Optional: GHCR login for private Packages

## setup and download the application
#clone repo
git clone
cd
#install dependencies
npm install
#run locally
npm run dev

## Run app via building the image locally
docker build -t nextjs-app:latest .
docker run -p 3000:3000 nextjs-app:latest
Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Deploy to minikube/kubernetes

Start minikube
```bash
start minikube
```
Apply deployment.yaml and service.yaml
```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
```
Check status of pods
```bash
kubectl get pods
```
Check if the CLI shows status=running
## Access the application
Check the IP address on which minikube is running
```bash
minikube ip
```
Open your browser and paste the following
```bash
http://<ip-returned-by-minikubeip-command>:30080
```

## Stop cluster

```bash
kubectl delete -f k8s/deployment.yaml
kubectl delete -f k8s/service.yaml
minikube stop
```


