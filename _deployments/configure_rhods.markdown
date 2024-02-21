---
# This is the Front Matter section where you can set variables used by Jekyll
layout: post
title: "Configure Red Hat OpenShift Data Science"
description: "Revolutionizing Nut Quality Control with Edge Computer Vision using YOLO V5 and Microshift"
image: /path/to/hero-image.jpg  # Path to a hero image (optional)
---

# Configure Red Hat OpenShift Data Science - WIP

## Prerequisites
* OpenShift Data Science Operator installed
* Minio has been installed 

**Access the minio dashboard from OpenShift**
![20240220130000](https://i.imgur.com/lsHlOBV.png)

**Login to minio**
![20240215152544](https://i.imgur.com/Ja5dMfY.jpg)
**Use username `minio` and password `minio123`**
![20240215152632](https://i.imgur.com/tAJwQ8d.png)
**Create `mybucket` to be used for pipelines**
![20240215152705](https://i.imgur.com/3ErXqeg.png)
![20240215152852](https://i.imgur.com/iVT3SlN.png)
**Create Access Keys to be used for `mybucket`**
![20240215152929](https://i.imgur.com/5MFQTN0.png)

**Login to openshift data science dashboard**
![20240220125558](https://i.imgur.com/ljRC5DU.png)
![20240220125619](https://i.imgur.com/Wd4lay2.png)

**Switch to the mltesting project**
![20240220125651](https://i.imgur.com/JkElNIM.png)
![20240220125717](https://i.imgur.com/FBqE9Qg.png)

**Create `rh1` workbench**
![20240215152310](https://i.imgur.com/oEGKujL.png)
![20240215152343](https://i.imgur.com/emojiDj.png)
![20240215152428](https://i.imgur.com/p4OLvNe.png)


![20240215153610](https://i.imgur.com/wGcCXrj.png)

**Configure Pipeline Server**
![20240220135935](https://i.imgur.com/UePuw81.png)
![20240220140113](https://i.imgur.com/Jr2CQOg.png)

**Create Notebooks in workbench**  
*Git URL:* https://github.com/tosin2013/redhat-pins-ai-demo.git
![20240215160517](https://i.imgur.com/C1eUdh0.png)
**Clone the repo**
![20240215160449](https://i.imgur.com/Sk9TrO1.png)
**Access the folder**
![20240215160735](https://i.imgur.com/2STy56n.png)

![20240215160945](https://i.imgur.com/3YtLydm.png)

### Run the notebooks
1. [Run rhods Notebooks](../../deployments/run_rhods_notebooks) - Run notebooks to train the AI model. 