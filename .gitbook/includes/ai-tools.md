---
title: AI Tools
---

{% embed url="https://youtu.be/D1HtzC6yiO4" %}

## Using Existing Function Stacks as Tools

{% stepper %}
{% step %}
### In the existing function stack, click the ⋮ settings icon in the upper-right corner of another function stack, and click <mark style="background-color:blue;">Use As AI Tool</mark>&#x20;
{% endstep %}

{% step %}
### Choose the Agent or MCP Server you'd like to add the tool to, and give it a name. This name is what the command will be, so make sure it's understandable
{% endstep %}

{% step %}
### A new tool will be created in your chosen destination with a function to call the function stack

Xano will not make a copy of your existing function stack; instead, it will use a Run Endpoint function and call that function stack internally. This is ideal, so you only have to maintain one function stack.

<div align="left"><figure><img src="../assets/CleanShot 2025-04-18 at 11.07.39 (1).png" alt="" width="563"><figcaption><p>A tool created from an existing API endpoint</p></figcaption></figure></div>
{% endstep %}

{% step %}
### Head to your tool's settings and add instructions

Instructions are important to have so the AI models and clients interacting with this tool understand how to use it.
{% endstep %}
{% endstepper %}

## Creating Tools from Scratch

{% stepper %}
{% step %}
### From the left-hand navigation menu, click Tools, then <mark style="background-color:blue;">+ Add Tool</mark>&#x20;
{% endstep %}

{% step %}
### Fill out the required information

* **Name**
  * Give your tool a recognizable name. This is also the command that will be used to execute your tool.
* **Description**
  * This is an internal-only field just for you to describe the purpose of the tool.
* **Allow Connections**
  * Enable or diffsable connection to this specific tool
* **Add Tag**
  * Tag your tools for easier search across your Xano workspace
* **Authentication**
  * Determine if this tool requires an authentication token
* **Tool Instructions**
  * These instructions are what your clients will use to understand how to send requests to the tool, and what the expected result will be. Markdown format is recommended.
{% endstep %}

{% step %}
### Build your tool's function stack

If you haven't already, make sure you're familiar with [building-with-visual-development](../../the-function-stack/building-with-visual-development/ "mention")
{% endstep %}

{% step %}
### Add the tool to an Agent or MCP Server

From the Agent or MCP Server, choose  + Add Tool  and select the tool you just created.
{% endstep %}
{% endstepper %}
