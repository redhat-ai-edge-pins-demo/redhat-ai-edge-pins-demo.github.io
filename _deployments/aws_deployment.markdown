---
# This is the Front Matter section where you can set variables used by Jekyll
layout: post
title: "AWS Blank Environment Instructions"
description: "Revolutionizing Nut Quality Control with Edge Computer Vision using YOLO V5 and Microshift"
image: /path/to/hero-image.jpg  # Path to a hero image (optional)
---

## Prerequisites
* RHEL 8.x jumpbox that is registred with Red Hat
* Review and run the [openshift-ai-workload.sh](https://gist.github.com/tosin2013/76e47de3f32de4486ab4699c21b2188e)
  
## SSH into RHEL jumpbox
{% highlight bash %}
Export the following AWS variables before running this script:
export aws_access_key_id="YOUR_ACCESS_KEY_ID"
export aws_secret_access_key="YOUR_SECRET_ACCESS_KEY"
export aws_region="YOUR_AWS_REGION"

https://gist.githubusercontent.com/tosin2013/76e47de3f32de4486ab4699c21b2188e/raw/1c16543b4edae4804f73966ca4e40822e0bbfa95/openshift-ai-workload.sh
chmod +x openshift-ai-workload.sh
./openshift-ai-workload.sh
{% endhighlight %}

## Configure jumpbox for deployment
{% highlight bash %}
curl -OL https://raw.githubusercontent.com/tosin2013/redhat-edge-ai-industrial-demo-infra/main/dev-box.sh
chmod +x dev-box.sh
./dev-box.sh
{% endhighlight %}


## For deployments without GPU
{% highlight bash %}
cd $HOME/redhat-edge-ai-industrial-demo-infra
oc create -k clusters/overlays/aws
{% endhighlight %}

## For deployments with GPU
{% highlight bash %}
cd $HOME/redhat-edge-ai-industrial-demo-infra
oc create -k clusters/overlays/aws-gpu
{% endhighlight %}


[Back to Homepage](/)