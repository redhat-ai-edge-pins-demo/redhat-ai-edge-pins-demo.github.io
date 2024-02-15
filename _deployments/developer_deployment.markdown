---
# This is the Front Matter section where you can set variables used by Jekyll
layout: post
title: "Developer Deployment Instructions"
description: "Revolutionizing Nut Quality Control with Edge Computer Vision using YOLO V5 and Microshift"
image: /path/to/hero-image.jpg  # Path to a hero image (optional)
---

## Prerequisites
* RHEL 8.x jumpbox that is registred with Red Hat
* Review and run the [openshift-ai-workload.sh](https://gist.github.com/tosin2013/76e47de3f32de4486ab4699c21b2188e)
* If using demo.redhat.com use `RHEL 8 Base` instance to configure a jumpbox and run the fork and run [rhel8-bootstrap](https://github.com/tosin2013/rhel8-bootstrap) `https://github.com/tosin2013/rhel8-bootstrap/actions/workflows/configure-rhel8-bastion.yml` to run GitHub Actions to configure the jumpbox. Igf you do not want to run this on your laptop.

  
## SSH into RHEL jumpbox
[Deploying GPUs for AI Workloads on OpenShift on AWS](https://medium.com/@tcij1013/deploying-gpus-for-ai-workloads-on-openshift-on-aws-9f43b9ce2875)

{% highlight bash %}
Export the following AWS variables before running this script:
export aws_access_key_id="YOUR_ACCESS_KEY_ID"
export aws_secret_access_key="YOUR_SECRET_ACCESS_KEY"
export aws_region="YOUR_AWS_REGION"

curl -OL https://gist.githubusercontent.com/tosin2013/76e47de3f32de4486ab4699c21b2188e/raw/959ae5dd2117edf124e4531cfae5216c722a3358/openshift-ai-workload.sh
chmod +x openshift-ai-workload.sh
./openshift-ai-workload.sh m6i.4xlarge # without GPU

./openshift-ai-workload.sh g4dn.2xlarge # with GPU
{% endhighlight %}

## Configure SSL for OpenShift Console
* [Configuring SSL for OpenShift Console](https://docs.openshift.com/container-platform/4.14/security/certificates/replacing-default-ingress-certificate.html)
* [configure-keys-on-openshift.sh](https://gist.githubusercontent.com/tosin2013/866522a1420ac22f477d2253121b4416/raw/35d6fa88675d63b6ecf58a827df32356ccf3ddde/configure-keys-on-openshift.sh)
{% highlight bash %}
$ sudo su - 
$ curl -OL https://gist.githubusercontent.com/tosin2013/866522a1420ac22f477d2253121b4416/raw/35d6fa88675d63b6ecf58a827df32356ccf3ddde/configure-keys-on-openshift.sh
$ chmod +x configure-keys-on-openshift.sh
$ ./configure-keys-on-openshift.sh AWS_ACCESS_KEY AWS_SECRET_ACCESS_KEY podman
{% endhighlight %}

## Configure jumpbox for deployment
{% highlight bash %}
curl -OL https://raw.githubusercontent.com/tosin2013/redhat-edge-ai-industrial-demo-infra/main/dev-box.sh
chmod +x dev-box.sh
./dev-box.sh
{% endhighlight %}

## Deploy Gitea
{% highlight bash %}
curl -OL https://raw.githubusercontent.com/tosin2013/openshift-demos/master/quick-scripts/deploy-gitea.sh
chmod +x deploy-gitea.sh
./deploy-gitea.sh
{% endhighlight %}

### Configure Gitea
**Click on route in OpenShift Console**
![20240215124034](https://i.imgur.com/Zc2JdCs.png)
**(1) Click on Register**
**(2) Register a new account**
![20240215124218](https://i.imgur.com/8cy4AtL.png)
**(3) Click on New Migration**
click on Git
![20240215124321](https://i.imgur.com/Mnlm1NL.png)
**(4) Click on Migrate From Git**
* https://github.com/tosin2013/redhat-edge-ai-industrial-demo-infra.git
![20240215124519](https://i.imgur.com/ZW62bxD.png)
**(5) Edit the following folders in the repo**
* Replace with your gita URL  
File path: `clusters/overlays/aws/patch-applicationset-repo-revision.yaml`
![20240215130537](https://i.imgur.com/wL6dyLS.png)
File path 2: `clusters/overlays/aws/patch-application-repo-revision.yaml`
![20240215130742](https://i.imgur.com/lrv5Wj9.png)
## Apply configure changes to argocd
{% highlight bash %}
$ git clone https://$(oc get route -n gitea | grep gitea-with-admin | awk '{print $2}' | head -1)/user1/redhat-edge-ai-industrial-demo-infra.git
$ cd redhat-edge-ai-industrial-demo-infra
$ oc create -k clusters/overlays/aws
{% endhighlight %}

## Ensure the ArgoCD application is in sync
![20240213165739](https://i.imgur.com/0vdu0mx.jpg)

## Configure Enviornment
1. [Run tekton pipeline](../../deployments/run_tekton_pipeline) - The Tekton pipeline is used to build the container image for the application.
2. [Configure rhods](../../deployments/configure_rhods) - The Red Hat OpenShift Data Science environment is used to train the AI model.

[Back to Homepage](/)