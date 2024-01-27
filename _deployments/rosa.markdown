---
layout: post
title: "Rosa Deployment Instructions"
description: "Revolutionizing Nut Quality Control with Edge Computer Vision using YOLO V5 and Microshift"
image: /path/to/hero-image.jpg  # Path to a hero image (optional)
---

![20240106111312](https://i.imgur.com/AGBg7uY.jpg)

## Prerequisites
* Ensure cluster is updated to 4.13
* Change worker node count to 4 on a minimal deployment. 
  
![20240106142502](https://i.imgur.com/kMdBwSo.png)

## SSH into RHEL jumpbox
{% highlight bash %}
ssh  cloud-user@<jumpbox_ip>
{% endhighlight %}

## Optional run the script below to install dependencies
{% highlight bash %}
curl -OL https://raw.githubusercontent.com/tosin2013/redhat-edge-ai-industrial-demo-infra/main/dev-box.sh
chmod +x dev-box.sh
./dev-box.sh
{% endhighlight %}

## Configure ArgoCD 
{% highlight bash %}
cd $HOME/redhat-edge-ai-industrial-demo-infra
oc create -k clusters/overlays/rosa
{% endhighlight %}

## Run Tekton Pipeline
* [Run tekton pipeline](run-tekton-pipeline.md)

![20240106111607](https://i.imgur.com/SH87x22.png)

![20240106134547](https://i.imgur.com/ssgQacx.png)

[Back to Homepage](/)