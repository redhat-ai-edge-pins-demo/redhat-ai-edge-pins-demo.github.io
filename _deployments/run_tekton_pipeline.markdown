---
# This is the Front Matter section where you can set variables used by Jekyll
layout: post
title: "Run tekton pipeline"
description: "Revolutionizing Nut Quality Control with Edge Computer Vision using YOLO V5 and Microshift"
image: /path/to/hero-image.jpg  # Path to a hero image (optional)
---

# Run tekton pipeline
![20240106134547](https://i.imgur.com/ssgQacx.png)

## Prerequisites
* Configure Secret for quay regisgtry -> use this link as reference [configure-pipeline-secret.sh](https://raw.githubusercontent.com/tosin2013/redhat-edge-ai-industrial-demo-infra/main/hack/configure-pipeline-secret.sh)
* If you ran the dev-env setup, you can call the script below to configure the secret
{% highlight bash %}
 ./hack/configure-pipeline-secret.sh
{% endhighlight %}


## Run pipeline against quay.io
{% highlight bash %}
curl -OL https://raw.githubusercontent.com/tosin2013/redhat-edge-ai-industrial-demo-infra/main/hack/run_pipeline.sh
chmod +x run_pipeline.sh

USERNAME=takinosh
./run_pipeline.sh quay.io/${USERNAME}/redhat-edge-ai-industrial-demo
{% endhighlight %}

## Run pipeline against self hosted quay on openshift
{% highlight bash %}
curl -OL https://raw.githubusercontent.com/tosin2013/redhat-edge-ai-industrial-demo-infra/main/hack/run_pipeline.sh
chmod +x run_pipeline.sh

./run_pipeline.sh $(oc get route -n quay | grep registry-quay | awk '{print $2}' | head -1)/admin/redhat-edge-ai-industrial-demo
{% endhighlight %}
o


## Source code
**Tekton Pipelines**
* Tekton Pipeline for [redhat-edge-ai-industrial-demo](https://github.com/tosin2013/redhat-edge-ai-industrial-demo-infra/tree/main/components/applications/redhat-edge-ai-industrial-demo/overlays/rhde-dev-env)

**Via URL**  

*make sure openshift pipelines is installed before running*

{% highlight bash %}
oc apply -k https://github.com/tosin2013/redhat-edge-ai-industrial-demo-infra/components/applications/redhat-edge-ai-industrial-demo/overlays/rhde-dev-env
{% endhighlight %}