# Kubernetes Workshop

[Presentation](https://docs.google.com/presentation/d/1BuB8xiFdeyI5P2Ah3rxulteG23i89daxX5UTyOgWq8Y/edit?usp=sharing)

## 🚧 

Use the deployment and service YAML files as starting point

```bash
kubectl apply -f deployment.yml service.yml -n <your_namespace_previously_created>
```

If you running on minikube, you need to follow this to enable ingress https://minikube.sigs.k8s.io/docs/handbook/addons/ingress-dns/

### The ingress.yml file

- Documentation: https://kubernetes.io/docs/concepts/services-networking/ingress/
- Examples: https://k8s-examples.container-solutions.com/examples/Ingress/Ingress.html

#### Complete the file

Basically you have to fill the ingress host for the http, path and backend service (check documentation and examples, there are a lot of documentation)

#### Into the cluster

```bash
kubectl apply -f ingress.yml
```

Check the deployment in the cluster

```bash
kubectl get ingress -n <your_namespace_previously_created>
```

NOTE: You don't need the `-n <some_name_without_spaces>` if you have used kubens to set the default namespace

#### Let's test it

Go to your browser and give it a try http://webapp.aettua

Now edit the redis deployment and change the replicas to 0.

```bash
kubectl edit deployment redis
```

Check if the pod had already gone. If you hit http://webapp.aettua you should have an error

```bash
kubectl get pod
```

Now edit again the deployment and set again the replicas to 1.

When you refresh the page http://webapp.aettua you should see the same number of hits that you had before.

### The persistentvolume.yml file

If you are using minikube, check this https://minikube.sigs.k8s.io/docs/handbook/persistent_volumes/  
This can also be useful for the future https://minikube.sigs.k8s.io/docs/tutorials/volume_snapshots_and_csi/

- Documentation: https://kubernetes.io/docs/concepts/storage/persistent-volumes/
- Examples: https://kubernetes.io/docs/tasks/configure-pod-container/configure-persistent-volume-storage/

#### Complete the file

Configure the persistent volume claim to use the persistent volume

Configure the `deployment.yml` file to attach to the persisten volume claim

#### Into the cluster

Apply the file to create the resources in the cluster

```bash
kubectl apply -f persistentvolume.yml deployment.yml
```

#### Let's test it

Go to your browser and give it a try http://webapp.aettua

Now edit the redis deployment and change the replicas to 0.

```bash
kubectl edit deployment redis
```

Check if the pod had already gone. If you hit http://webapp.aettua you should have an error

```bash
kubectl get pod
```

Now edit again the deployment and set again the replicas to 1.

When you refresh the page http://webapp.aettua you should see the same number of hits that you had before.

NOTE: You don't need the `-n <some_name_without_spaces>` if you have used kubens to set the default namespace