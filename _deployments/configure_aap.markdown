---
# This is the Front Matter section where you can set variables used by Jekyll
layout: post
title: "Configure Ansible Automation Platform"
description: "Revolutionizing Nut Quality Control with Edge Computer Vision using YOLO V5 and Microshift"
image: /path/to/hero-image.jpg  # Path to a hero image (optional)
---

# Configure Ansible Automation Platform

## Prerequisites
* AAP has been deployed on OpenShift

![20240221115730](https://i.imgur.com/bTuaOBp.png)
![20240221111734](https://i.imgur.com/2B5Wckz.png)
![20240221111755](https://i.imgur.com/cgMvq8u.jpeg)
![20240221112012](https://i.imgur.com/OUymygl.png)

![20240221112251](https://i.imgur.com/PaUXYLY.png)

### Optional Install OpenShift Devspaces
* Configure DevSpaces for Ansible Automation Platform Configuration. [Read More](../../deployments/devspaces_configuration)


## Configure AAP
If you did not install the OpenShift Devspaces Operator, you can configure the AAP manually from your laptop using the [ee_definition_config](https://github.com/tosin2013/ee_definition_config) repo.

### Requirements install collections
{% highlight bash %}
ansible-galaxy collection install  -r collections/requirements.yml 
{% endhighlight %}

### Edit the secret-vars-microshift-ansible-aws-roles.yml
{% highlight bash %}
vim secret-vars-microshift-ansible-aws-roles.yml
{% endhighlight %}

### Load Execution Environment for Ansible AWS Role
{% highlight bash %}
export USERNAME=takinosh
export TAG=latest
ansible-playbook push_to_controller.yaml -e "ee_name_var=ansible-aws-roles" -e "set_ee_registry_dest_var=quay.io/${USERNAME}/ansible-aws-roles:${TAG}"  -e "@secret-vars-microshift-ansible-aws-roles.yml"
{% endhighlight %}
![20240221125007](https://i.imgur.com/7kAxN3V.png)

## Configure Controller for Microshift Deployments on AWS
{% highlight bash %}
ansible-playbook  microshift-ansible-aws-roles.yaml  -e "@secret-vars-microshift-ansible-aws-roles.yml" -e "@projects/ansible-aws-roles/microshift-ansible-aws-vars.yaml"  -vvv
{% endhighlight %}
![20240221124855](https://i.imgur.com/3PUdxRK.png)

## Load Execution Environment for edge.microshft collection
{% highlight bash %}
export USERNAME=takinosh
export TAG=latest
ansible-playbook push_to_controller.yaml -e "ee_name_var=edge.microshift" -e "set_ee_registry_dest_var=quay.io/${USERNAME}/edge.microshift:${TAG}"  -e "@secret-vars-microshift-ansible-aws-roles.yml"
{% endhighlight %}
![20240221125202](https://i.imgur.com/E37ENMW.png)


## Configure Automation Hub

**Configure Remotes under Collections**
![20240221131804](https://i.imgur.com/G7RDXTm.png)
**Edit the community remote**
![20240221131831](https://i.imgur.com/EIdnoD7.png)
**Update the collections using the items below**
![20240221131851](https://i.imgur.com/fxecD56.png)
![20240221141659](https://i.imgur.com/cQhCA6x.png)
```
---
collections:
  - name: infra.ee_utilities
  - name: awx.awx
  - name: infra.controller_configuration
  - name: infra.ah_configuration
  - name: infra.osbuild
  - name: containers.podman
  - name: redhat_cop.controller_configuration
  - name: amazon.aws
  - name: fedora.linux_system_roles
```
**sync the Community Repository under the Repositories workload**
![20240221132034](https://i.imgur.com/bG4Krds.png)
![20240221132256](https://i.imgur.com/WlG39Xa.png)
![20240221132319](https://i.imgur.com/gX2Advc.png)
**Validate Collections have been populated**
![20240221141318](https://i.imgur.com/IJyorPv.png)

## Deploy our application on Microshift. 
[Read More](../../deployments/aap_microshift_deployment)