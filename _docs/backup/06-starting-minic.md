---
title: "Starting Minic"
permalink: /docs/starting-minic/
excerpt: ""
last_modified_at: 2018-06-11T15:59:31-04:00
---

# Getting started for Minic
Before reading this document, Minic should be installed on your PC. If you didn’t install Minic, please take a look at the Installing Minic .
Minic is a tool that runs the Cocktail Cloud(mini version) on your PC. You can experience various features of the Cocktail Cloud with Minic.
This document contains a brief demo of deploying container to Cocktail Cloud. The flollowing steps describe how to get started.

## Starting Minic

1. Run the minic start command.
```bash
$ minic start
Kubernetes cluster started.(8s)
Checking inspector...|
```
2. When all pods are running(green status), type “o” to run Cocktail Cloud on your browser.
![minic status]({{ "/assets/images/minic.png" | relative_url }})
The status screen on your console(above image) shows the status of all pods that are running on local Kubernetes cluste(minic cluster). To exit the status screen, type “q” on your keyboard. You can see the screen by running minic status command at anytime you want.
