---
# This is the Front Matter section where you can set variables used by Jekyll
layout: post
title: "Deploy Application on Microshift"
description: "Revolutionizing Nut Quality Control with Edge Computer Vision using YOLO V5 and Microshift"
image: /path/to/hero-image.jpg  # Path to a hero image (optional)
---

# Deploy Application on Microshift

## Prerequisites
* AAP has been deployed on OpenShift

![20240221111710](https://i.imgur.com/Qr1GB97.png)
![20240221111734](https://i.imgur.com/2B5Wckz.png)
![20240221111755](https://i.imgur.com/cgMvq8u.jpeg)
![20240221112012](https://i.imgur.com/OUymygl.png)

![20240221112251](https://i.imgur.com/PaUXYLY.png)

### Optional Install OpenShift Devspaces
* Configure DevSpaces for Ansible Automation Platform Configuration. [Read More](../../deployments/devspaces_configuration)


## Configure AAP
If you did not install the OpenShift Devspaces Operator, you can configure the AAP manually from your laptop using the [ee_definition_config](https://github.com/tosin2013/ee_definition_config) repo.

## Requirements install collections
{% highlight bash %}
ansible-galaxy collection install  -r collections/requirements.yml 
{% endhighlight %}