# Minic

`minic` is a tool of running and managing local minikube cluster on container(Docker in Docker).

You need not local virtual machine tools like a virtualbox to run minikube anymore. Minic use a dind(Docker in docker) container to run minikube cluster, so you only need to install Docker in your PC or laptop on any OS(Windows, MacOS, Linux etc.)

## Use case

- Testing your container at various version of k8s cluster in local environment
- Delivering your containerized software package(with k8s cluster) for user experience on their PC

## How to use
 

## Building

### Building with go

- you need go v1.9 or later.
- if your working copy is not in your `GOPATH`, you need to set it accordingly.

```console
$ go build -o minic main.go
```

You can also use the Makefile directly:

```console
$ make
or
$ make install
```


### You can run the Cocktail Mini

```console
$ minic start
```
