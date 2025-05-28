---
description: >-
  Webhooks are specialized API endpoints designed to be triggered based on other
  events
icon: fishing-rod
---

# Webhooks

{% hint style="info" %}
## Quick Summary

Webhooks are API endpoints specifically designed for one system to **automatically push** information to another when a specific **event** happens. For example, Slack provides you with a webhook URL. This URL is ready and listening, much like your own API endpoint.

But here’s the key difference:

1. Something like a **form submission endpoint** receives data because the _user initiated_ the request (e.g., they clicked 'Submit').
2. The **Slack webhook** receives data because _your server_, after processing the form (the **event**), _initiated_ a new request, automatically pushing the form details _to_ Slack's URL. Slack didn't ask for it; your system sent it because something happened.

You'd build webhooks in Xano typically to ingest information _**pushed**_ from other places — like if a user pays for something via Stripe, or they perform an action in your app that you want to log.&#x20;
{% endhint %}

{% embed url="https://youtu.be/y5mmGCy7q1A" %}

## Building Webhooks

{% stepper %}
{% step %}
### Create a new API endpoint with a POST method

1. Click <mark style="background-color:blue;">+ Add API Endpoint</mark> from inside one of your API groups.
2. Choose **Custom API Endpoint** and fill in the details. Make sure to select **POST** as the verb.\
   ![](<../.gitbook/assets/CleanShot 2025-04-30 at 11.18.57.png>)
{% endstep %}

{% step %}
### Add a Get All Raw Input function

Typically, webhooks need to be able to dynamically process data that might look a little different between requests. So, we use [#get-all-raw-input](../the-function-stack/functions/utility-functions.md#get-all-raw-input "mention") to make sure that we aren't confined to just the inputs that are defined in the inputs section.

You'll need to choose the encoding, or the format, of the data being sent to this endpoint. This will more often than not be JSON.

While Get All Raw Input offers flexibility, always check the documentation of the service _sending_ the webhook. They will specify the structure (schema) of the data payload you should expect.
{% endstep %}

{% step %}
### Process the output of Get All Raw Input as needed

From here, the process is completely unique to whatever data is being sent to the webhook, and what you need to do with it.

**Examples:**

* Store the data in a database table using [add-record.md](../the-function-stack/functions/database-requests/add-record.md "mention")
* If the webhook is receiving a list of items, loop against them using [#for-each-loop](../the-function-stack/functions/data-manipulation/loops.md#for-each-loop "mention")
* Transform or manipulate the data using [filters](../the-function-stack/filters/ "mention") or an [expression.md](../the-function-stack/data-types/expression.md "mention")
* Send the data to another service, such as an analytics platform, using an [external-api-request.md](../the-function-stack/functions/apis-and-lambdas/external-api-request.md "mention")
* Begin a more in-depth process using a combination of the above to perform multiple actions, such as transforming data, storing it, and sending [emails.md](emails.md "mention")
{% endstep %}
{% endstepper %}

## Securing your Webhooks

Just like any other API endpoint you're building, it's important to ensure that they are built securely. Webhooks have some more specific-to-them ways that they are usually kept locked up.

{% stepper %}
{% step %}
### Signature Verification (recommended)

The service you're accepting requests from may offer signature verification. At a high level, this means that you would cross-check the signature they sent with your own calculated signature, using a private key that only you and the service are aware of, and ensure that they match.

{% hint style="success" %}
**If they match**: The request is verified and you can proceed.
{% endhint %}

{% hint style="danger" %}
**If they don't match**: you should deny the request
{% endhint %}

In general, this process follows a typical flow:

* Extract the signature provided in the request headers
* Ensure you have a raw, unaltered copy of the request body (which you do using Get All Raw Input)
* Use the proper [security.md](../the-function-stack/filters/security.md "mention") filter (such as [#hmac\_sha256-hmac384-hmac512](../the-function-stack/filters/security.md#hmac_sha256-hmac384-hmac512 "mention")) to encode your own signature, and ensure that it matches with the one you extracted from the request.
{% endstep %}

{% step %}
### Check a static token provided in the headers

Similar to how standard [user-authentication-and-user-data](user-authentication-and-user-data/ "mention") works, some services may just send an API key or bearer token as part of the request header. You'll want to compare this against your own stored key and ensure that they match.

It's also good practice to rotate this token on a regular basis to ensure that it is not compromised.
{% endstep %}
{% endstepper %}

{% hint style="success" %}
## Tip

Use [middleware.md](../the-function-stack/building-with-visual-development/middleware.md "mention") or [custom-functions](../the-function-stack/building-with-visual-development/custom-functions/ "mention") to build your webhook verification and quickly deploy it across multiple function stacks.
{% endhint %}

