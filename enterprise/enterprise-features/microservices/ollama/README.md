---
description: Deploy LLMs as a part of your Xano instance
---

# Ollama

{% hint style="info" %}
## Quick Summary

Through Xano's Microservice feature, you can deploy [Ollama](https://ollama.com/) as a part of your Xano instance, enabling secure communication with an off-the-shelf or customizable LLM tailored specifically to your needs.
{% endhint %}

## What is Ollama?

Ollama is a platform that enables seamless integration of large language models (LLMs) into various applications. It provides an environment where businesses can deploy pre-built or customized LLMs, facilitating secure and efficient communication tailored to specific business needs.

This makes it easier for companies to leverage advanced AI technology without extensive in-house development, and without the concerns of sending data to a third-party AI provider. In addition, deploying Ollama as a part of your Xano instance can be a significant cost-saving measure in comparison to leveraging a third party service.

## What can I do with Ollama + Xano?

Deploying Ollama as a microservice in Xano helps address a **critical data privacy challenge** when building AI-enabled applications that handle sensitive information.

By processing data within your controlled infrastructure boundary rather than sending it to external AI providers, using Xano with microservices removes one significant barrier to developing secure applications that can still leverage the benefits of AI models.

{% hint style="success" %}
<sup>_While this approach addresses an important technical aspect of data privacy, comprehensive security and compliance will require implementing additional safeguards appropriate to your specific regulatory environment._</sup>
{% endhint %}

## Getting Started

{% stepper %}
{% step %}
### If you're not on an Enterprise plan, reach out to our team to get started.

<a href="https://www.xano.com/enterprise/" class="button primary">Talk to Sales</a>
{% endstep %}

{% step %}
### Head to your instance settings, and select <mark style="background-color:blue;">Microservices</mark>&#x20;


{% endstep %}

{% step %}
### Choose a model to deploy

You'll want to know which model you're deploying so we understand the resources that need to be allocated. Check out the resource linked below if you need help choosing a model.

[choosing-a-model.md](choosing-a-model.md "mention")
{% endstep %}

{% step %}
### Add a persistent volume

A persistent volume is just a place that the microservice can store data that remains between restarts. Ollama will use this volume to store the model(s) that you're working with.

{% hint style="info" %}
## How much storage do I need?

When browsing Ollama models, use the Size column for your chosen model to determine how large of a volume you should deploy.

![](<../../../../.gitbook/assets/image (94).png>)
{% endhint %}

Name the volume `ollama`, select the size, and choose `SSD` as the storage class. When you're ready, click <mark style="background-color:blue;">Add</mark>&#x20;

<div align="left"><figure><img src="../../../../.gitbook/assets/CleanShot 2025-05-19 at 14.31.21.png" alt="" width="563"><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### Add a deployment

Click <mark style="background-color:blue;">Add</mark> under Deployments


{% endstep %}
{% endstepper %}

