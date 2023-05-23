# Kubernetes Workshop

[Presentation](https://docs.google.com/presentation/d/1BuB8xiFdeyI5P2Ah3rxulteG23i89daxX5UTyOgWq8Y/edit?usp=sharing)

## 🚧 

Docker images to use
- Webapp
    - ydata/docker-workshop:1.0
    - ghcr.io/ydataai/docker-workshop:1.0
- Redis
    - bitnami/redis:7.0.11
    - or another from dockerhub

### The deployment.yml file

#### Complete the file

Add a container with `webapp` using one of the docker images mentioned above

You have to set the image, the tag and expose the port 8000

Add another container with the `redis` image using the image above or other from the dockerhub (make sure you read how to use it)

Note the labels in the `template` and `selector` sections

#### Apply it to the cluster

```bash
kubectl apply -f deployment.yml -n <some_name_without_spaces>
```

Check the deployment in the cluster

```bash
kubectl get deployment
```

Check the pods (remember, which deployment has one or more pods, depending on the replicas property)

```bash
kubectl get pods 
```

NOTE: You don't need the `-n <some_name_without_spaces>` if you have used kubens to set the default namespace

### The service.yml file

#### Complete the file

Add the necessary ports to expose the services in the deployment.

Note the selector, this needs to match the same labels in the deployment

#### Apply it to the cluster

```bash
kubectl apply -f service.yml -n <some_name_without_spaces>
```

You don't need the `-n <some_name_without_spaces>` if you have used kubens to set the default namespace