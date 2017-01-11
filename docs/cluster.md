# Air Cluster Deployment

## Getting credentials

```
gcloud config set container/cluster air-x2
gcloud container clusters get-credentials air-x2
```

## Installing secrets

Run following command to make Kubernetes cluster access quay.io repositories

```
kubectl create secret docker-registry air-key \
  --docker-server=quay.io \
  --docker-username=whiskhq \
  --docker-password=<password> \
  --docker-email=tech@whisk.co.uk
```

## Deploying Mailer

[Link to repo](https://github.com/whisklabs/air-mailer)

```
kubectl create -f kubernetes
```

## Deploying skyalrk api (backend)

[Link to repo](https://github.com/whisklabs/skylark)

```
kubectl create -f kubernetes/skylark-api
kubectl expose deployment skylark-dev
kubectl expose deployment skylark
```

## Deploying frontend

[Link to repo](https://github.com/whisklabs/air)

```
kubectl create -f kubernetes
```
