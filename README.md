# Minic

`minic` is a tool of running and managing local minikube cluster on container(Docker in Docker).

You need not local virtual machine tools like a virtualbox to run minikube anymore. Minic use a dind(Docker in docker) container to run minikube cluster, so you only need to install Docker in your PC or laptop on any OS(Windows, MacOS, Linux etc.)

## Use case

- Testing your container at various version of k8s cluster in local environment
- Delivering your containerized software package(with k8s cluster) for user experience on their PC

## How to use
 
### Download
* [Mac](https://github.com/acornapps/minic/releases/download/v0.3/minic-darwin-amd64.zip)
* [linux](https://github.com/acornapps/minic/releases/download/v0.3/minic-windows-amd64.zip)
* [Windows](https://github.com/acornapps/minic/releases/download/v0.3/minic-windows-amd64.zip)

### You can run the Cocktail Mini

```console
$ minic start
```
