### Why do we need it?

- To manage and customize configuration files, enabling more flexible and maintainable deployments.


### What is it?

- Kustomize is configuration management solution for customizing your applications in Kubernetes, where you can keep the original settings as a base and then apply changes using special configuration files, called patches, without actually altering the original files. This allows you to tweak your applications without messing up their core configuration.

### Prerequisites:

0.  Kubernetes Cluster 

    - ```minikube start --nodes=2 --kubernetes-version v1.25.14``` can be used to create a simple cluster in your local machine

1. ```kubectl version```


If you have 1.21 or above of kubectl you will have access to kubectl kustomize which is the recommended method. If you aren't on version 1.21 or above, upgrade kubectl. (4*)

2. Create namespaces

```kubectl create namespace dev```

```kubectl create namespace prod```


### Test

```kustomize build overlays/dev```

```kustomize build overlays/prod```


```kubectl apply -k overlays/dev```

```kubectl apply -k overlays/prod```

### Resources

1. https://kubectl.docs.kubernetes.io/guides/introduction/kustomize/

2. https://devopscube.com/kustomize-tutorial/

3. [Kustomize: The Best Way to Manage Your Kubernetes Configs](https://www.youtube.com/watch?v=spCdNeNCuFU)

4. https://github.com/devopsjourney1/mykustomapp/blob/master/README.md