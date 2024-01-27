---
layout: default  # Specifies the layout template to use (e.g., 'default')
title: Deployment Types  # The title of the page
permalink: /deployments/  # Custom permalink for this page
---

# Deployment Types

Welcome to our deployment types page. Here you can find instructions for deploying our AI models on different platforms running OpenShift.

## Available Deployment Types

Below is a list of deployment Types we've put together:

{% for post in site.deployments %}
  - [{{ post.title }}]({{ post.url | prepend: site.baseurl }}) 
{% endfor %}
