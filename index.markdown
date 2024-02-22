---
# This is the Front Matter section where you can set variables used by Jekyll
layout: home
title: "Red Hat AI Model Deployment Workflow from Core to Edge"
description: "The goal of this architecture is to streamline the process from model development to deployment, particularly in edge computing scenarios where models need to be run closer to data sources for faster processing."
image: /path/to/redhat-image.jpg  # Path to a redhat image (optional)
---


![20240222140117](https://i.imgur.com/41zi47h.png)

<!-- Project Overview -->
## Project Overview
Using state-of-the-art computer vision and AI technology, we've developed a system that accurately detects defects in nuts as an example us case.

## Archetecture Overview
The goal of this architecture is to streamline the process from model development to deployment, particularly in edge computing scenarios where models need to be run closer to data sources for faster processing. It emphasizes continuous integration and deployment (CI/CD) practices, automation, and the use of containerization for easy scalability and management. The model performance monitoring and training data collection at the bottom suggests that the system also includes feedback loops for continuous improvement of the AI models.
![20240222135930](https://i.imgur.com/cDFN15c.png)

<!-- Model Creation with OpenShift AI -->

<!-- Jupyter Lab Overview -->
### Configure Red Hat OpenShift Data Science
Explore how we configure Red Hat OpenShift Data Science for our AI model training. [Read More](deployments/configure_rhods)

### Jupyter Lab for Model Training
Download our Jupyter Lab notebook and explore how we train our AI models.
[Run notebook and deploy Pipeline](deployments/run_rhods_notebooks)

<!-- Workload Container & Microshift Deployment -->
### Deployment and Orchestration
Discover how we deploy our AI models using Microshift and manage workloads efficiently. [Read More](/deployment)

<!-- OpenShift Deployment Documentation -->
### Documentation for OpenShift Deployments
Check our detailed documentation for deploying on OpenShift. 
* [Developer Instructions](deployments/developer_deployment)
* [AWS Instructions](deployments/aws_deployment)
* [Rosa Deployment Instructions](deployments/rosa)

<!-- Tekton Pipeline -->
### Tekton Pipeline for CI/CD
We use Tekton Pipelines for continuous integration and continuous deployment. [Run Pipeline](/deployments/run_tekton_pipeline)

<!-- Microshift Deployment -->
### Microshift Deployment Instructions
* Configure DevSpaces for Ansible Automation Platform Configuration. [Read More](deployments/devspaces_configuration)
* Configure Ansible Automation Platform. [Read More](deployments/configure_aap)
* Deploy our application on Microshift. [Read More](deployments/aap_microshift_deployment)

<!-- Demo Section 
### See Our Technology in Action
[Watch the Demo Video](/path/to/demo-video) or view the [Image Gallery](/image-gallery)-->

<!-- Latest Blog Posts
### Latest from Our Blog
Here you can list your latest blog posts. Jekyll can automatically populate this section from your posts. -->

<!-- Footer -->
#### Stay Connected
Follow us on [GitHub](https://github.com/redhat-ai-edge-pins-demo) and stay updated with our latest developments.
