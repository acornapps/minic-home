---
title: "Running Minic"
permalink: /docs/running-minic/
excerpt: ""
last_modified_at: 2018-06-11T15:59:26-04:00
# toc: true
---

## Running Minic

To run minic, type the “start” command on your prompt.

```bash
$ minic start
```

The `minic start` command has several steps on processing.

At first, the start command download the Cocktail mini container image. It takes one or more minutes, depending your network speed. And then, it runs kubernetes cluster and Cocktail mini. At this time, your prompt is changed to “status mode”.(see following image)

![minic status]({{ "/assets/images/minic-status.png" | relative_url }})

Cocktail mini is consist of containers(pods) that are run on kubernetes. So, you should wait untill all containers are run. (As like the above image, all pod status will be changed to “Running(green)” when to be ready)

Type “o” to open Cocktail mini and you can see the login screen of Cocktail mini as following.

<img src="/assets/images/minic-login.png" alt="minic-login" width="300" />

Only one user is available on The Cocktail mini.

* Role : Admin
* Id : admin@acornsoft.io
* Password : admin0000

After you logined, you can see the main dashboard of Cocktail mini.

![minic status]({{ "/assets/images/minic-dashboard.png" | relative_url }})

Now you can experience the Cocktail Cloud !
