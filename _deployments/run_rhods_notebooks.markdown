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

## Create pipelines with Tekton integration

### Create a file called `demo.pipeline`
**Click on Pipeline Editor**
![20240220135438](https://i.imgur.com/wwPrHSw.png)
**Rename pipeline to demo pipeline**
![20240220135555](https://i.imgur.com/uAJx1As.png)

## Configure Pipeline Runtime
![20240220135727](https://i.imgur.com/5sNyQj4.png)

* Data Science Pipelines API Endpoint* 
  * `https://ds-pipeline-pipelines-definition-mltesting.apps.mltesting.example.com`
* Public Data Science Pipelines API Endpoint
  * https://rhods-dashboard-redhat-ods-applications.apps.mltesting.sandbox2831.opentlc.com/pipelineRuns/mltesting
* Data Science Pipelines API Endpoint Password Or Token
  * OpenShift API token
* Cloud Object Storage Endpoint*
  * https://minio-api-mltesting.apps.mltesting.sandbox2831.opentlc.com
* Cloud Object Storage Bucket Name*
  * `mybucket`
* Cloud Object Storage Credentials Secret
  * ` aws-connection-mybucket`
* Cloud Object Storage Username
  * minio
* Cloud Object Storage Password
  * minio123

![20240220140905](https://i.imgur.com/Wl1vo5z.png)
![20240220140937](https://i.imgur.com/IAdfshr.png)

The data volume for each job is below 
* Mount Path* `/opt/app-root/src/`
* Persistent Volume Claim Name* `pins-workspace`

Optional: Add GPU information
* GPU: `1`
* GPU Vendor: `nvidia.com/gpu`

1. [prepare_env.ipynb](https://github.com/tosin2013/redhat-pins-ai-demo/blob/main/prepare_env.ipynb)
![20240220141325](https://i.imgur.com/Rbd73yn.png)
2. [Train model.ipynb](https://github.com/tosin2013/redhat-pins-ai-demo/blob/main/Train_Model.ipynb)
![20240220142450](https://i.imgur.com/BUdu5tB.png)
3. [Test_Model.ipynb](https://github.com/tosin2013/redhat-pins-ai-demo/blob/main/Test_Model.ipynb)
![20240220142610](https://i.imgur.com/AIH2rWq.png)
4. [Store_Model.ipynb](https://github.com/tosin2013/redhat-pins-ai-demo/blob/main/Store_Model.ipynb)  
![20240220142703](https://i.imgur.com/fRy3xYe.png)

## Final View of the pipeline
![20240220142735](https://i.imgur.com/D4oECVh.png)

## Start pipeline run