---
# This is the Front Matter section where you can set variables used by Jekyll
layout: post
title: "Run Jupyter Notebooks on Red Hat OpenShift Data Science"
description: "Revolutionizing Nut Quality Control with Edge Computer Vision using YOLO V5 and Microshift"
image: /path/to/hero-image.jpg  # Path to a hero image (optional)
---

# Run Jupyter Notebooks on Red Hat OpenShift Data Science - WIP

## Prerequisites
* Configure RHODS workspace has been completed.

## Run Jupyter notebooks 
1. [prepare_env.ipynb](https://github.com/tosin2013/redhat-pins-ai-demo/blob/main/prepare_env.ipynb)
![20240220131717](https://i.imgur.com/NOrV7m2.png)
2. [Train model.ipynb](https://github.com/tosin2013/redhat-pins-ai-demo/blob/main/Train_Model.ipynb)
![20240220133400](https://i.imgur.com/HqpcRMR.png)
3. [Test_Model.ipynb](https://github.com/tosin2013/redhat-pins-ai-demo/blob/main/Test_Model.ipynb)
![20240220132122](https://i.imgur.com/1SIFfBg.png)
4. [Store_Model.ipynb](https://github.com/tosin2013/redhat-pins-ai-demo/blob/main/Store_Model.ipynb)  
`Change the minio vaules and run the notebook`
![20240220134738](https://i.imgur.com/sBiIxs2.png)

## Create pipelines with Tekton