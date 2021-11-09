# How to run reviews service

## Prerequisite

* Java 8

```bash
/opt/ibm/wlp/bin/server run defaultServer
```

## How to run with Docker

```bash
# Build Docker Image for reviews service
docker build -t reviews .

# Run details service on port 8082
docker run -d --name reviews -p 8082:9080 reviews
```

* Test with path `/reviews/1` and `/health`

## How to run with Docker Compose

```bash
docker-compose up
```
## Build amd Push Docker Image
```bash
# Build Ratings Service Docker Image
docker-compose build

export TOKEN=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
export GITHUB_USER=jowkha
echo $TOKEN | docker login ghcr.io --password-stdin --username $GITHUB_USER
docker push ghcr.io/jowkha/bookinfo-reviews:dev
```

## How to run kubectl

```bash
# Create deployment resource
kubectl apply -f k8s/

# Check status of each resource
kubectl get deploy,pod,svc,ingress
```
## How to check 

```bash
curl http://itkmitl.bookinfo.dev.opsta.net/student3/reviews/health
```
