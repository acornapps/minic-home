# Minic

`#minic`

## Welcome to Minic!

Minic is a tool that helps you run Cocktail Cloud locally by running a single-node Kubernetes cluster inside a Docker. Actually, Minic runs a single container(called “Cocktail mini container”) that packages Cocktail Cloud and Kubernetes cluster.

This documentation contains the sections to help you get started with Cocktail Mini.

## Installing Minic

### 1. System requirements

Minic is available on multiple operating systems.

* macOS : El Capitan 10.11 and newer macOS releases
* Windows : Windows 10 Pro, Enterprise and Education (1607 Anniversary Update, Build 14393 or later)
* CentOS 7
* Ubuntu : Xenial 16.04 (LTS), Trusty 14.04 (LTS)
* Debian : Stretch 9 (stable) / Raspbian Stretch, Jessie 8 (LTS) / Raspbian Jessie, Wheezy 7.7 (LTS)
* Fedora : Version 26, 27  

Minic requires at least 2 cores of CPU and 4 Gbytes of memory. So, your device(PC, notebook etc.) should have more resources then this requirements.

* 2 Cores of CPU or above
* 8 Gbytes of memory or above

### 2. Install Docker

Minic requires Docker to run the Cocktail mini container. Install Docker, depending on your host operating system. Refer to following link.

* [Mac](https://github.com/acornapps/minic/releases/download/v0.3/minic-darwin-amd64.zip)
* [linux](https://github.com/acornapps/minic/releases/download/v0.3/minic-windows-amd64.zip)
* [Windows](https://github.com/acornapps/minic/releases/download/v0.3/minic-windows-amd64.zip)


In macOS and Windows, Docker is launched on virtual machine that is hosted on your PC
or notebook. So, all containers(including Cocktail mini container) only use resources that the virtual machine has.
Because of this reason, you should configure the Docker’s advanced options of resources for running Minic.

### 3. Configure Docker resources setting

**Docker for Mac**

Click the whale in the top status bar, and choose “Preferences” menu.

![](./assets/images/Get_started_with_Docker_for_Mac__Docker_Documentation.png)
