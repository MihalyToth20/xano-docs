---
description: Build business logic once and reuse it in multiple places
---

# Custom Functions

{% hint style="info" %}
**Quick Summary**

Custom functions are very similar to your APIs — they have inputs, a function stack, and a response. However, they can not be called externally. Instead, custom functions allow you to build something and use it in other places, while maintaining it in a centralized location.
{% endhint %}

## What is a custom function?

Custom functions can be thought of as a building block for the rest of your backend. You can build a custom function just like an API endpoint, and insert that custom function into other function stacks, giving you easily reusable logic while only having to maintain it in one place. When you make a change inside of a custom function, that change is automatically in effect everywhere you have chosen to use the custom function.

***

## Building and Using Custom Functions

{% stepper %}
{% step %}
### Access your custom functions from the left-hand menu.

<div align="left"><figure><img src="../../../.gitbook/assets/CleanShot 2024-12-27 at 14.31.52 (1).png" alt=""><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### Click <mark style="background-color:blue;">+ Add Function</mark> to create a new custom function.

Give your custom function a **name**, **description**, **tags**, and choose your [request-history.md](../../../maintenance-monitoring-and-logging/request-history.md "mention") settings.

You can also choose to store your custom functions inside of a folder. If the folder already exists, just start typing the name and select it from the auto-complete. If the folder doesn't exist, you can create a new one from here.

![](<../../../.gitbook/assets/CleanShot 2025-05-19 at 10.34.21.png>)\
\
When you're done, click <mark style="background-color:blue;">Save</mark> .
{% endstep %}

{% step %}
### Build your custom function

A custom function has three sections — the same as an API endpoint.

{% include "../../../.gitbook/includes/inputs.md" %}

{% include "../../../.gitbook/includes/function-stack.md" %}

{% include "../../../.gitbook/includes/response.md" %}
{% endstep %}

{% step %}
### Insert your new custom function into other function stacks.

When you're ready to use your new custom function in other function stacks, click ![](<../../../.gitbook/assets/CleanShot 2024-12-27 at 14.40.23.png>), choose **Custom Functions** from the panel that opens, and select your custom function.

You'll be able to supply data for any inputs the custom function is expecting here.

<div align="left"><figure><img src="../../../.gitbook/assets/CleanShot 2024-12-27 at 14.41.28.png" alt=""><figcaption></figcaption></figure></div>
{% endstep %}
{% endstepper %}

***

### Creating Custom Functions from Existing Function Stacks

If you have a function stack that you'd like to convert into a custom function, you can do so in one of the following ways.

{% stepper %}
{% step %}
### Convert the entire stack

Click the three dots in the upper-right corner and choose Convert To Function

<div align="left"><figure><img src="../../../.gitbook/assets/CleanShot 2025-02-12 at 12.13.55.png" alt=""><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### Select individual steps to convert to a function

You can select a group of steps and click ![](<../../../.gitbook/assets/CleanShot 2025-02-12 at 12.16.11.png>)to convert those steps into a custom function.

<figure><img src="../../../.gitbook/assets/CleanShot 2025-02-12 at 12.14.46.gif" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

***

## Custom Function Settings

### From the Settings panel

<div align="left"><figure><img src="../../../.gitbook/assets/CleanShot 2024-12-23 at 09.56.20 (1).png" alt="" width="266"><figcaption></figcaption></figure></div>

<table><thead><tr><th width="257">Name</th><th>Purpose</th></tr></thead><tbody><tr><td>Name</td><td>The name of the custom function.</td></tr><tr><td>Description</td><td>An internal description, just for you.</td></tr><tr><td>Tags</td><td>Use tags to organize objects throughout your Xano workspace and find them later</td></tr><tr><td>Request History</td><td><ul><li><p>Inherit Settings</p><ul><li>Use whatever is set in your workspace branch defaults</li></ul></li><li><p>Other</p><ul><li>Set specific request history settings for this function</li></ul></li></ul><p><span data-gb-custom-inline data-tag="emoji" data-code="1f4d6">📖</span> <a href="../../../maintenance-monitoring-and-logging/request-history.md"><strong>Learn more about request history</strong></a></p></td></tr><tr><td>Response caching</td><td>Cache the response and redeliver it during future runs<br><br><span data-gb-custom-inline data-tag="emoji" data-code="1f4d6">📖</span><a href="../../additional-features/response-caching.md"> <strong>Learn more about response caching</strong></a></td></tr></tbody></table>

***

## Custom Function Folders <a href="#folders" id="folders"></a>

You can organize your custom functions into folders for better organization.

* Folders are not required if you prefer not to use them. You can store all of your functions in folders, or use a combination of folders and no folders.
* A folder requires having at least one function inside of it — empty folders are not supported.

{% stepper %}
{% step %}
### Creating New Functions

When creating a new function, you'll be given the option to store it in a folder.

Just start typing the name of the folder. If it exists, select it from the auto-complete dropdown. If it doesn't exist, it will be created for you.

<div align="left"><figure><img src="../../../.gitbook/assets/CleanShot 2025-05-19 at 10.40.00.png" alt=""><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### Creating New Folders with Existing Functions

Click the <mark style="background-color:blue;">Add Folder</mark> button to create a new folder for your existing functions.

<div align="left"><figure><img src="../../../.gitbook/assets/CleanShot 2025-05-19 at 10.41.03.png" alt="" width="305"><figcaption></figcaption></figure></div>

Give your new folder a name, and use the autocomplete to select at least one function to add to it.

<div align="left"><figure><img src="../../../.gitbook/assets/CleanShot 2025-05-19 at 10.42.01.png" alt="" width="240"><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### Moving Existing Functions into Folders

Select the functions to move by using the checkboxes on the left-hand side, and click <mark style="background-color:blue;">Move</mark>&#x20;

<figure><img src="../../../.gitbook/assets/CleanShot 2025-05-19 at 10.44.42.png" alt=""><figcaption></figcaption></figure>

Type a new folder name, or add them to an existing folder. When you're ready, click <mark style="background-color:blue;">Save</mark>&#x20;

<div align="left"><figure><img src="../../../.gitbook/assets/CleanShot 2025-05-19 at 10.45.29.png" alt="" width="242"><figcaption></figcaption></figure></div>
{% endstep %}
{% endstepper %}
