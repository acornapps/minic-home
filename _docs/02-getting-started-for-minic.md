---
title: "Hello Cocktail"
permalink: /docs/getting-started-for-minic/
excerpt: ""
last_modified_at: 2018-06-11T15:58:49-04:00
redirect_from:
  - /theme-setup/
toc: true
toc_sticky: true
---

Before reading this document, Minic should be installed on your PC. If you didn’t install Minic, please take a look at the [Installing Cocktail Mini](http://minic.run).

Minic is a tool that runs the Cocktail Cloud(mini version) on your PC. You can experience various features of the Cocktail Cloud with Minic.

This document contains a brief demo of deploying container to Cocktail Cloud. The flollowing steps describe how to get started.

## Starting Minic

1. Run the `minic start` command.
```bash
$ minic start
Kubernetes cluster started.(8s)
Checking inspector...|
```
2. When all pods are running(green status), type “o” to run Cocktail Cloud on your browser.
![minic status]({{ "/assets/images/minic.png" | relative_url }})
The status screen on your console(above image) shows the status of all pods that are running on local Kubernetes cluste(minic cluster). To exit the status screen, type “q” on your keyboard. You can see the screen by running `minic status` command at anytime you want.

## Log in to Cocktail Mini

1. At the Cocktail Mini’s login screen, select role and input user id, password.  
<img src="/assets/images/minic-login.png" width="300" />  
The default user informations are as follows.
* Role : Admin
* User Id : [admin@acornsoft.io](mailto:admin@acornsoft.io)
* Password : Admin0000

2. Click “Sign in” button. You can see the Dashboard screen.
![minic dashboard]({{ "/assets/images/Cocktail-2.png" | relative_url }})

## Create Namespace

1. Click the Service menu on left side. To create the namespace, click the “+” button.
![minic status]({{ "/assets/images/Cocktail-3.png" | relative_url }})

2. On the dialog box, input the namespace information that you want create. And then click the Create button.
![minic status]({{ "/assets/images/Cocktail-4.png" | relative_url }})
For example.
* Cluster : Select “minikube”
* Map Name : “Web Service”
* Namespace Name : web-svc

3. You can see the “Web Service” namespace on the screen.
![minic status]({{ "/assets/images/Cocktail-5.png" | relative_url }})

## Create Server

In the Cocktail Cloud, Server is a package that is consist of Kubernetes objects. Cocktail Cloud manges life cycle and monitoring of the server.

1. Click the name of namespace. And Click the Default group’s “+” button on the namespace(Application Map) screen.
![minic dashboard]({{ "/assets/images/Cocktail-6.png" | relative_url }})
![minic dashboard]({{ "/assets/images/Cocktail-7.png" | relative_url }})

2. Input server basic information.
![minic dashboard]({{ "/assets/images/Cocktail-8.png" | relative_url }})
For example.
* Name : nginx
* Group : Default
* Type : Single
* Description : nginx server

3. Click the “+” button to add container(see the above image). Add container information to run.(see below image). And then click the Apply button to save.
![minic dashboard]({{ "/assets/images/Cocktail-Bear.png" | relative_url }})

4. The nginx container was added. To add Service port, click the edit button.
![minic dashboard]({{ "/assets/images/Cocktail-9.png" | relative_url }})

5. In the Service port’s input dialog, add port as following image.
![minic dashboard]({{ "/assets/images/Cocktail-11.png" | relative_url }})
For example.
* Container : Select “nginx”
* Port Type : Select “Node Port”.
* (Click the “Add Port button”)
* Name : “web”
* Target Port (Container port) : 80
* Port (Service Port) : 80

## Deploy Server

1. Everything is ready to deploy the “nginx” server. To create server, click the “Create” button.
![minic dashboard]({{ "/assets/images/Cocktail-Bear-2.png" | relative_url }})

2. After a while, you can see the nginx server running. Click the server address link to open the home page of nginx.
![minic dashboard]({{ "/assets/images/Cocktail-10.png" | relative_url }})

(On your browser...)
![minic dashboard]({{ "/assets/images/Welcome_to_nginx_.png" | relative_url }})
