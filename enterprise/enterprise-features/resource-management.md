---
description: >-
  BYOC (Bring your own Cloud) users can manage their available instance
  resources from their instance settings
---

# Resource Management

{% hint style="danger" %}
## Warning

Make sure you are aware of your maximum available resources within the cluster before making any adjustments to these settings.

These settings can consist of maximum CPU/RAM per node (or server), as well as the maximum number of nodes that can exist within the environment.

Maximum restrictions are in place to prevent infrastructure costs from increasing unexpectedly. It is very easy to request excessive amounts of resources, so these safeguards help keep things aligned to the current expectations you have for your backend performance and cost.

The maximum restrictions can be adjusted at the infrastructure level if you have outgrown your current allotment.

If you aren't sure how to proceed, contact our support team for details.
{% endhint %}

## What is Resource Management?

The Resource Management panel allows Custom and Enterprise BYOC (Bring Your Own Cloud) customers to configure CPU, RAM, and storage allocation for different components of your Xano instance.&#x20;

## Accessing Resource Management

{% stepper %}
{% step %}
### From the instance selection screen, click the :gear: icon

<div align="left"><figure><img src="../../.gitbook/assets/CleanShot 2025-07-10 at 17.26.52.png" alt="" width="451"><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### In the panel that opens, choose Resource Management

<div align="left"><figure><img src="../../.gitbook/assets/CleanShot 2025-07-10 at 17.27.29.png" alt="" width="474"><figcaption></figcaption></figure></div>
{% endstep %}
{% endstepper %}

## Types of Resources

{% hint style="info" %}
### Resource Unit Measurements

Understanding the units used in Xano's resource allocation is essential for proper configuration.

#### CPU Measurements

* **m (millicores):** 1000m = 1 CPU core
* **Examples:** 5m (very light), 100m (moderate), 1000m (1 full core)

#### RAM Measurements

* **Mi (Mebibytes):** 1024Mi = 1 GB
* **Examples:** 512Mi (0.5 GB), 1536Mi (1.5 GB), 2048Mi (2 GB)

#### Storage Measurements

* **Gi (Gibibytes):** 1Gi = 1.07 GB
* **Examples:** 10Gi (≈11 GB), 100Gi (≈107 GB)
{% endhint %}

### Backend Resources

The **Backend** handles your API endpoints, most of your business logic execution, and core Xano functionality. This is typically your primary compute workload.

**Configuration Options:**

* **Requested CPU:** Minimum CPU allocation
* **Limit CPU:** Maximum CPU the backend can consume
* **Requested RAM:** Minimum memory allocation
* **Limit RAM:** Maximum memory the backend can use

### Backend Autoscaler

The **Autoscaler** automatically adjusts the number of backend pods based on CPU utilization to handle varying traffic loads.

**Configuration Options:**

* **CPU Threshold:** Percentage of CPU usage that triggers scaling
* **Min Replicas:** Minimum number of backend pods to maintain
* **Max Replicas:** Maximum number of instances the autoscaler can create

{% hint style="warning" %}
## Important Considerations

* Setting min replicas too low may cause cold start delays during traffic spikes
* Setting max replicas too high could lead to unnecessary costs
* Monitor your typical traffic patterns to optimize these settings
{% endhint %}

### Deno Resources

The **Deno** pod handles execution of your [lambda-functions.md](../../the-function-stack/functions/apis-and-lambdas/lambda-functions.md "mention")

**Configuration Options:**

* **Requested CPU:** Minimum CPU allocation
* **Limit CPU:** Maximum CPU the backend can consume
* **Requested RAM:** Minimum memory allocation
* **Limit RAM:** Maximum memory the backend can use

### Node Resources

**Node** powers our realtime functionality as well as certain core functionality of your Xano instance such as team collaboration and state mangement

**Configuration Options:**

* **Requested CPU:** Base CPU allocation (e.g., 5m)
* **Limit CPU:** Maximum CPU available (e.g., 500m = 0.5 CPU cores)
* **Requested/Limit RAM:** Memory allocation (e.g., 2048Mi = 2 GB)

### Database Resources

{% hint style="info" %}
This section may not be present if your database is offloaded to a managed service, such as CloudSQL.


{% endhint %}

**Database pod** manages your PostgreSQL database pod and handles all database operations.

{% hint style="info" %}
While you do have a separate backend pod for business logic, it's important to note when workloads will lean on the database resources. If an API executes a Query All Records function, the backend is only responsible for passing that instruction to the database, and receiving the result when it's ready. The database resources are used to actually perform the operation.
{% endhint %}

**Configuration Options:**

* **Requested CPU:** Guaranteed database CPU (e.g., 5m)
* **Limit CPU:** Maximum database CPU (e.g., 2000m = 2 CPU cores)
* **Requested/Limit RAM:** Database memory allocation
* **Storage:** Persistent storage for your database (measured in Gi = Gibibytes, e.g., 10Gi ≈ 10.7 GB)

{% hint style="success" %}
## Optimization Tips

* Database performance heavily depends on RAM for caching
* Consider your data size and query complexity when setting limits
* Storage should account for data growth over time, and should never reach over 50% - 60% capacity for best performance.
{% endhint %}

### Task Resources

**Task resources** execute [background-tasks.md](../../the-function-stack/building-with-visual-development/background-tasks.md "mention"). Please note that these resources are for all of your tasks collectively, and not individual tasks.

**Configuration Options:**

* **Requested CPU:** Minimum CPU allocation
* **Limit CPU:** Maximum CPU your tasks can consume
* **Requested RAM:** Minimum memory allocation
* **Limit RAM:** Maximum memory your tasks can use

**When to Scale Up:**

* High volume of background jobs
* Complex data processing tasks
* Frequent scheduled operations

### Frontend Resources

**Frontend service** serves your Xano interface

**Configuration Options:**

* **Requested CPU:** Often minimal (0m for light loads)
* **Limit CPU:** Usually 50m-100m is sufficient
* **RAM:** Typically 16Mi-32Mi for basic serving

{% hint style="info" %}
It's not likely that this will ever require adjustment.
{% endhint %}

### Global Redis Resources

{% hint style="info" %}
This section may not be present if Redis is offloaded to a managed service such as Memorystore within GCP.
{% endhint %}

**Redis cache** powers all of the high-performance caching functions and response caching

**Configuration Options:**

* **CPU:** Usually 5m-1000m depending on cache usage
* **RAM:** Critical for Redis performance (384Mi-512Mi typical)
* **Storage:** Persistent storage for Redis data&#x20;

{% hint style="danger" %}
## Redis-Specific Warnings

* Redis is memory-intensive; insufficient RAM will impact performance significantly
* Storage ensures data persistence across pod restarts
{% endhint %}

## Additional Information

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}

{% content-ref url="deployment.md" %}
[deployment.md](deployment.md)
{% endcontent-ref %}

