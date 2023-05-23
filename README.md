# Kubernetes Workshop

[Presentation](https://docs.google.com/presentation/d/1BuB8xiFdeyI5P2Ah3rxulteG23i89daxX5UTyOgWq8Y/edit?usp=sharing)

## 🛠️ Tools

- [Kubectl](#-kubectl) -**Required**
- [Minikube](#-minikube)
- [kubectx and kubens](#-kubectx-and-kubens)


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