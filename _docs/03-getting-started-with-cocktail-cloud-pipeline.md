---
title: "Getting started with Pipeline"
permalink: /docs/getting-started-with-cocktail-cloud-pipeline/
excerpt: ""
last_modified_at: 2018-06-11T15:58:49-04:00
redirect_from:
  - /theme-setup/
toc: true
toc_sticky: true
---

Before reading this document, Minic should be installed on your PC. If you didn’t install Minic, please take a look at the [Installing Cocktail Mini](http://minic.run).

Cocktail Cloud has feature of automating pipeline that is from code to deploy. Continuous Delivery is one of the key requirements in Cloud Native Computing. Because, that is related to agility of business. In the Cocktail Cloud, all the tasks of downloading code, building and deploying container are automated by pipeline. The Cocktail Cloud Pipeline ease the operator burden.

This document contains a brief demo of the Cocktail Cloud Pipeline features. The following steps describe how to that.

## Starting Minic

1. Run the `minic start` command.
```bash
$ minic start
Kubernetes cluster started.(8s)
Checking inspector...|
```

2. When all pods are running(green status), type “o” to run Cocktail Cloud on your browser.
![minic status]({{ "/assets/images/minic-pipeline-01.png" | relative_url }})

The status screen on your console(above image) shows the status of all pods that are running on local Kubernetes cluste(minic cluster). To exit the status screen, type “q” on your keyboard. You can see the screen by running `minic status` command at anytime you want.

## Log in to Cocktail Mini

1. At the Cocktail Mini’s login screen, select role and input user id, password.  
![minic status]({{ "/assets/images/minic-pipeline-02.png" | relative_url }})  
The default user informations are as follows.
* Role : Admin
* User Id : [admin@acornsoft.io](mailto:admin@acornsoft.io)
* Password : Admin0000

2. Click “Sign in” button. You can see the Dashboard screen.
![minic status]({{ "/assets/images/minic-pipeline-03.png" | relative_url }})

## Create the Build
1. Click the “Service” menu on left side.

2. Click the “Build Management” button on service bar to go to the “Build” screen
![minic status]({{ "/assets/images/minic-pipeline-04.png" | relative_url }})

3. At the build screen, click the ‘Add Build” button.
![minic status]({{ "/assets/images/minic-pipeline-05.png" | relative_url }})

4. You can see the build screen as follows. Next steps are input the build information.
![minic status]({{ "/assets/images/minic-pipeline-06.png" | relative_url }})

5. Enter title(name) of build in the first group on the build screen.
* Title : “Hello Cocktail”
![minic status]({{ "/assets/images/minic-pipeline-07.png" | relative_url }})

6. Click checkbox of the “1. Application Download” group, then you can see the input form of code repository information. Enter the information of repository. (In this example, I used the Cocktail Mini’s public repository)
* Repository Type : GIT
* Protocol Type : HTTPS
* Git Repository Type : Common (this means that the repository is public)
* Repository URL : [github.com/acornapps/hello-cocktail.git](https://github.com/acornapps/hello-cocktail) (you should omit “https://“ of the URL)
* Target Branch : master
![minic status]({{ "/assets/images/minic-pipeline-08.png" | relative_url }})

7. Next, Click checkbox of the “2. Application Build” group to enter build information. In the Cocktail Cloud, container is used to run the task of build. You can change the container to what you want., like the language image, tag etc in any time.
* Command : `go build -o main` . (This command run the golang container’s command)
* Host Path - Container Path : `/go/src/app` (This path map the “Host Path” into container)
* Host Path - Host Path : `$PWD/repo` (This path is where the code is downloaded)
* Working dir : `/go/src/app` (This is the current path where the command is executed)
* Image : golang, latest (The official image of go language container with it’s tag)
![minic status]({{ "/assets/images/minic-pipeline-09.png" | relative_url }})

8. On the group of “3. Image Build”, enter the build script of image that you will create. And enter the name of image registry, image and tag.
* Dockerfile :
```dockerfile
FROM golang:latest
WORKDIR /app
# RUN mkdir /app
COPY ./repo/main /app/
# RUN go build -o main .
CMD ["/app/main"]
```
* Registry Name : cocktail-mini
* Image Name : hello-cocktail
* Version : 1.0.0 (Image tag)
![minic status]({{ "/assets/images/minic-pipeline-10.png" | relative_url }})

9. Click the “Create” button to create build.
![minic status]({{ "/assets/images/minic-pipeline-11.png" | relative_url }})

## Run Build
1. To run the build, on the list of builds, click the action button that is in right side of build and select “Build Run”.
![minic status]({{ "/assets/images/minic-pipeline-12.png" | relative_url }})

2. During the build process is running, you can see the build logs by clicking taps on the “Build log” dialog.
![minic status]({{ "/assets/images/minic-pipeline-13.png" | relative_url }})

3. When build process was done, the status of build would be changed to “DONE”. (See below)
![minic status]({{ "/assets/images/minic-pipeline-14.png" | relative_url }})

## Create Server and Pipeline

Now, let’s create the pipeline with creating server

1. Click the “Service” menu.

2. Click the “+” button on service bar to create application map.

3. Enter the information that is needed to create application map.
* Cluster : minikube
* Map Name : Pipeline Demo
* Namespace Name : pipeline-demo

4. Click the “Create” button.
![minic status]({{ "/assets/images/minic-pipeline-15.png" | relative_url }})

5. Click the application map, “Pipeline Demo”.
![minic status]({{ "/assets/images/minic-pipeline-16.png" | relative_url }})

6. Click the “+” button to create server.
![minic status]({{ "/assets/images/minic-pipeline-17.png" | relative_url }})

7. In the server creating form, enter basic information of server.
* Name : hello-cocktail
* Group : default
* Type : Single
* Description : hello-cocktail server

8. Click the “+” button to add container.
![minic status]({{ "/assets/images/minic-pipeline-18.png" | relative_url }})

9. In the container form, select the build information what you created before as a container image.
* Container Name : hello-cocktail-container
* Build
  * Hello Cocktail : The name of build
  * cocktail-mini/hello-cocktail : The name of build’s image
  * 1.0.0.B0000001 : The tag of image. Build number is automatically assigned by Cocktail Cloud for automated pipeline process

10. Click the “Apply” button to add container.
![minic status]({{ "/assets/images/minic-pipeline-19.png" | relative_url }})

11. If you want to access the container from outside, you should to add “Service Port” to the container. Click the edit button to add service port.
![minic status]({{ "/assets/images/minic-pipeline-20.png" | relative_url }})

12. Enter the information of Service Port.
* Container : hello-cocktail-container
* Port Type : Node Port
* Name : web
* Target Port : 3000(This is the container port that is exported)
* Port : 80 (This is server port that you can access from outside)

13. Click the “Apply” button to add Service Port
![minic status]({{ "/assets/images/minic-pipeline-21.png" | relative_url }})

14. Click the “Create” button to create server.
![minic status]({{ "/assets/images/minic-pipeline-22.png" | relative_url }})

15. The server was created. You can access that by clicking the Service Port address. (See below)  
![minic status]({{ "/assets/images/minic-pipeline-23.png" | relative_url }})

## Run Pipeline

When you create server with build image, the Pipeline is automatically created. You can see the Pipeline on the “pipeline” tap of application map screen.
![minic status]({{ "/assets/images/minic-pipeline-24.png" | relative_url }})
If the code of build is updated, you can run the Pipeline to update the server.

1. Select type of run with “Build&Deployment” and check the “Execution whether” checkbox.
2. Click the “Run” button of the Pipeline.
3. You can see the status of running Pipeline
![minic status]({{ "/assets/images/minic-pipeline-25.png" | relative_url }})
The Pipeline of Cocktail Cloud automate process of build and deploy. So you can focus on your code with Cocktail Cloud Pipeline.
