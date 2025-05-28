---
title: Branch Defaults
---

# Branch Defaults

> These are default settings related to what is logged in your [request-history.md](../../maintenance-monitoring-and-logging/request-history.md "mention")

In your workspace settings, you can manage the request history for your entire workspace in the Branch Defaults panel.

<figure><img src="../assets/CleanShot 2024-04-02 at 12.30.06.png" alt="" width="375"><figcaption></figcaption></figure>

From this panel, we can define the request history defaults for each object type (query, function, task, middleware, trigger) that maintains history.

<figure><img src="../assets/CleanShot 2024-04-04 at 18.59.26.png" alt=""><figcaption></figcaption></figure>

* **Enable / Disable** - Performs the selected action on the object type
* **Function Statement Limit** - The number of statements to record for each object type. You can choose between:
  * No statements
  * 100 statements
  * 1,000 statements
  * 10,000 statements
  * Store all statements

{% hint style="warning" %}
Please note that request history utilizes your Database (SSD) storage. It is important to consider this when determining how many statements can be stored, or if they need to be stored at all.
{% endhint %}

### Inheriting Settings

In each individual API, function, task, middleware, or trigger's settings, you can also control the request history for that object specifically.

By default, these will be set to **inherit**, which means it will obey the branch defaults. Otherwise, you can adjust this for specific objects as necessary.
