# Kubernetes Workshop

[Presentation](https://docs.google.com/presentation/d/1BuB8xiFdeyI5P2Ah3rxulteG23i89daxX5UTyOgWq8Y/edit?usp=sharing)

## Documentation

- [Kubernetes Official](https://kubernetes.io/docs/concepts/)
- [Container Solutions Examples](https://k8s-examples.container-solutions.com/examples/)
- [Kubectl Cheatsheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
- [Getting Started Example](https://www.freecodecamp.org/news/the-kubernetes-handbook/)

## 🛠️ Tools

- [Kubectl](#-kubectl) - **Required**
- [Minikube](#-minikube) - **Not required but suggested**
- [kubectx and kubens](#-kubectx-and-kubens)
- [gcloud] - **Alternative for those not using minikube**


### Kubectl

- Linux: https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/
- macOS: `brew cask install kubectl`
- Windows: https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/

It is recomended that you install the same version of the kubernetes that you are using.

### Minikube

https://minikube.sigs.k8s.io/docs/start/

Select the operating system, arquitecture and package manger that you want to use.

### Kubectx and kubens

https://github.com/ahmetb/kubectx

This are tools that help you on your daily basis tasks when you have multiple clusters to manage.

### GCloud

https://cloud.google.com/sdk/docs/install

If you have MacOS and homebrew installed

```bash
brew install --cask google-cloud-sdk
```

## Drivers, Start your engines

For this workshop, you will need a cluster to try what you will create.

We will give two options, being the **minikube** the one recommended.  
You will have access to this (because it's running on your computer) after this workshop finishes.

### Minikube (Recommended)

To start minikube with required addons for this workshop, use the following command

#### MacOS

```bash
minikube start --addons=ingress,ingress-dns --driver=hyperkit
```

#### Others

```bash
minikube start --addons=ingress,ingress-dns
```

### Cluster on cloud provided by us

If you don't want to use minikube, we have a cluster running on GCloud that you can use.

```bash
export GOOGLE_APPLICATION_CREDENTIALS=aettua-workshop-key.json
export KUBECONFIG=kubeconfig.yaml
gcloud container clusters get-credentials workshop-cluster --zone europe-southwest1
````


## Hands-on

First let's create a namespace for you to work, instead of use the default.

```
kubectl create namespace <some_name_without_spaces>
```

If you have installed kubens 

```bash
kubens <some_name_without_spaces>
```

otherwise don't forget to prepend or append your `kubectl` commands with `-n <some_name_without_spaces>`

Let's play

```
git clone https://github.com/ydataai/kubernetes-workshop.git
```

### Phase 1

```bash
git checkout phase-1
```

Check the readme https://github.com/ydataai/kubernetes-workshop/tree/phase-1 for the next instructions

### Phase 2

```
git checkout phase-2
```

Check the readme https://github.com/ydataai/kubernetes-workshop/tree/phase-2 for the next instructions
