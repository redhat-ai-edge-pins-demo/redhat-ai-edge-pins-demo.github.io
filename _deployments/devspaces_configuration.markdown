---
# This is the Front Matter section where you can set variables used by Jekyll
layout: post
title: "Configure DevSpaces for Ansible Automation Platform Configuration" 
description: "Revolutionizing Nut Quality Control with Edge Computer Vision using YOLO V5 and Microshift"
image: /path/to/hero-image.jpg  # Path to a hero image (optional)
---

# Configure DevSpaces for Ansible Automation Platform Configuration

**Install the OpenShift DevSpaces Operator**
```
$  oc apply -k https://github.com/tosin2013/sno-quickstarts/gitops/cluster-config/devspaces/operator/overlays/stable
```

**Install the OpenShift DevSpaces Instance**
```
$ oc apply -k https://github.com/tosin2013/sno-quickstarts/gitops/cluster-config/devspaces/instance/overlay/default
```

**Wait for pods to load**
![20240221113242](https://i.imgur.com/XhKDPvh.png)

**Access OpenShift Devspaces Route**
![20240221113449](https://i.imgur.com/EV959xb.png)

![20240221113628](https://i.imgur.com/D1O1D3z.png)

**Load the ee_definition_config repo into devspaces**
* [https://github.com/tosin2013/ee_definition_config](https://github.com/tosin2013/ee_definition_config)
  ![20240221113742](https://i.imgur.com/uEWV9fE.png)

  ![20240221113930](https://i.imgur.com/Q8fgCUy.png)


## Deploy our application on Microshift.
 [Read More](deployments/aap_microshift_deployment)
