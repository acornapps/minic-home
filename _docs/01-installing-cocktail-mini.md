---
title: "Installing Cocktail Mini"
permalink: /docs/installing-cocktail-mini/
excerpt: ""
last_modified_at: 2018-06-11T15:58:49-04:00
redirect_from:
  - /theme-setup/
toc: true
toc_sticky: true
---

This guide contains how to install and run Cocktail Mini.

## System requirements

Minic is available on multiple operating systems.

* macOS : El Capitan 10.11 and newer macOS releases
* Windows : Windows 10 Pro, Enterprise and Education (1607 Anniversary Update, Build 14393 or later)
* Ubuntu : Xenial 16.04(LTS) and 18.04(LTS)
* CentOS 7

Minic requires at least 2 cores of CPU and 4 Gbytes of memory. So, your device(PC, notebook etc.) should have more resources then this requirements.

* 2 Cores of CPU or above
* 8 Gbytes of memory or above

## Install Docker

Minic requires Docker to run the Cocktail Mini container. Install Docker, depending on your host operating system. Refer to following link.

[Docker install](https://docs.docker.com/install/)

In macOS and Windows, Docker is launched on virtual machine that is hosted on your PC
or notebook. So, all containers(including Cocktail Mini container) only use resources that the virtual machine has.
Because of this reason, you should configure the Docker’s advanced options of resources for running Minic.

## Configure Docker resources setting

### Docker for Mac

Click the whale in the top status bar, and choose “Preferences” menu.

![docker menubar]({{ "/assets/images/whale-in-menu-bar.png" | relative_url }})

![docker for mac]({{ "/assets/images/Get_started_with_Docker_for_Mac___Docker_Documentation.png" | relative_url }})

On the Advanced tab, you can see the resources available to Docker. Set the CPUs value to 2 cores and the Memory value to 4.0 GiB as follows.

![docker for mac advanced]({{ "/assets/images/Advanced.png" | relative_url }})

### Docker for Windows

Open the Docker for Windows menu by right-clicking the Docker icon in the Notifications area (or System tray).

![docker for mac advanced1]({{ "/assets/images/windows-docker-documentation1.png" | relative_url }})

Select Settings... to open the Settings dialog.

![docker for mac advanced2]({{ "/assets/images/windows-docker-documentation2.png" | relative_url }})

On the Advanced tab, you can see the resources available to Docker. Set the CPUs value to 2 cores and the Memory value to 4096 MB. The Linux VM restarts after changing the settings on the Advanced tab. This takes a few seconds.

![docker for mac advanced3]({{ "/assets/images/windows-docker-documentation3.png" | relative_url }})

## Download and install Minic

Minic is distributed in zip or tar.gz file that is consists of a single executable file.

Download the Minic distribution file from following links, depending your operating system.

* Darwin/amd64(macOS)[[Link1](https://github.com/acornapps/minic-home/releases/download/v0.5/minic-darwin-amd64.zip) / [Link2](https://s3-us-west-2.amazonaws.com/cocktail-mini/minic-darwin-amd64.zip)]
* Windows/amd64[[Link1](https://github.com/acornapps/minic-home/releases/download/v0.5/minic-windows-amd64.zip) / [Link2](https://s3-us-west-2.amazonaws.com/cocktail-mini/minic-windows-amd64.zip)]
* Linux/amd64[[Link1](https://github.com/acornapps/minic-home/releases/download/v0.5/minic-linux-amd64.zip) / [Link2](https://s3-us-west-2.amazonaws.com/cocktail-mini/minic-linux-amd64.zip)]

After downloading, unzip the downloaded file to your PATH directory.

Now, you ready to run Minic.

## Running Minic

To run minic, type the “start” command on your prompt.

```bash
$ minic start
```

The `minic start` command has several steps on processing.

At first, the start command download the Cocktail Mini container image. It takes one or more minutes, depending your network speed. And then, it runs kubernetes cluster and Cocktail Mini. At this time, your prompt is changed to “status mode”.(see following image)

![minic status]({{ "/assets/images/minic-status.png" | relative_url }})

Cocktail Mini is consist of containers(pods) that are run on kubernetes. So, you should wait untill all containers are run. (As like the above image, all pod status will be changed to “Running(green)” when to be ready)

Type “o” to open Cocktail Mini and you can see the login screen of Cocktail Mini as following.

<img src="/assets/images/minic-login.png" alt="minic-login" width="300" />

Only one user is available on The Cocktail Mini.

* Role : Admin
* Id : admin@acornsoft.io
* Password : admin0000

After you logined, you can see the main dashboard of Cocktail Mini.

![minic status]({{ "/assets/images/minic-dashboard.png" | relative_url }})

Now you can experience the Cocktail Cloud !
