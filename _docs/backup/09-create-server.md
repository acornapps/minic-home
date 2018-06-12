---
title: "Create Server"
permalink: /docs/create-server/
excerpt: ""
last_modified_at: 2018-06-11T10:55:15-04:00
---

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
