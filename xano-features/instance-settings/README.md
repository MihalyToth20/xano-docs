---
icon: gears
---

# Instance Settings

## Custom Domain

Xano has support for users on any of our paid plans to set up a custom domain to be used for the URLs of their API endpoints.&#x20;

{% embed url="https://youtu.be/St_sqV5VWRI" %}

{% stepper %}
{% step %}
### Head to the instance selection page and click the :gear:icon next to your instance


{% endstep %}

{% step %}
### Choose 'Custom Domain' from the panel that opens


{% endstep %}

{% step %}
### Update the DNS records with your domain registrar

For more information on this process, consult your registrar's documentation. Quick links are provided below for your convenience.

* [GoDaddy](https://www.godaddy.com/help/manage-dns-records-680)
* [Namecheap](https://www.namecheap.com/support/knowledgebase/article.aspx/767/10/how-to-change-dns-for-a-domain/)
* [Cloudflare](https://developers.cloudflare.com/dns/manage-dns-records/how-to/create-dns-records/)
* [Squarespace (formerly Google Domains)](https://support.squarespace.com/hc/en-us/articles/205812348-Accessing-your-Squarespace-managed-domain-s-DNS-settings)
* [Hover](https://support.hover.com/support/solutions/articles/201000064728-managing-dns-records)
* [Network Solutions](https://www.networksolutions.com/help/article/manage-dns-adns-records)
* [1&1 IONOS](https://www.ionos.com/help/domains/dns-settings/)
* [Bluehost](https://www.bluehost.com/help/article/dns-management-add-edit-or-delete-dns-entries)
* [HostGator](https://www.hostgator.com/help/article/changing-dns-records)
* [Porkbun](https://kb.porkbun.com/article/68-how-to-edit-dns-records)
* [Dynadot](https://www.dynadot.com/community/help/question/set-up-DNS)
* [Name.com](https://www.name.com/support/articles/206127137-adding-dns-records-and-templates)
* [Gandi](https://docs.gandi.net/en/domain_names/common_operations/dns_records.html)
{% endstep %}

{% step %}
### Check for propagation and update the domain in Xano once complete

Once you add the DNS record, those changes need to propagate across the globe to various DNS servers. You can check the status of propagation at whatismydns.net.

The more green checkmarks you see here, the better. You are free to proceed at any time, but please note that in areas where propagation has not completed, your APIs may not be accessible.

<div align="left"><figure><img src="../../.gitbook/assets/CleanShot 2025-07-24 at 13.34.43.png" alt="" width="563"><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### Add your custom domain to the configuration panel

Add your domain and save your changes. They will be immediately applied, and your APIs and /Xano instance will be available at your new custom domain.
{% endstep %}
{% endstepper %}

### Connect via Xano Domain

In some cases, you may still want to connect to your Xano instance via the original Xano domain. To connect through your Xano domain, head to your instance selection screen. Click the three dots when hovering over your instance, and choose "Connect Via Xano Domain".

<figure><img src="../../.gitbook/assets/CleanShot 2023-03-15 at 09.31.14.png" alt=""><figcaption></figcaption></figure>

## Database Connector

{% hint style="info" %}
The Database Connector requires an add-on to our **Starter plan** or is included with the **Pro plan**.
{% endhint %}

You have the option to connect your Xano instance's PostgreSQL database directly with an external application or service. This can be useful if there is a platform for manipulating your database that you prefer to use over the Xano interface, creating custom backup and restore solutions, or even performing data analytics.

{% hint style="warning" %}
Use care when accessing your database directly. This type of connection removes a significant portion of normal checks and balances for data validity that using Xano directly provides.&#x20;

**Proceed with caution.**
{% endhint %}

#### How to Access the Database Connector

On your instance selection screen, click the ⚙️ icon, and in the panel that opens, choose Database Connector.

<figure><img src="../../.gitbook/assets/CleanShot 2023-08-16 at 13.18.14.png" alt=""><figcaption></figcaption></figure>

<div data-full-width="false"><figure><img src="../../.gitbook/assets/CleanShot 2023-08-16 at 13.21.19.png" alt="" width="329"><figcaption></figcaption></figure></div>

The panel that opens is split into two sections, Details and Settings.

<figure><img src="../../.gitbook/assets/CleanShot 2023-08-16 at 13.22.58.png" alt=""><figcaption></figcaption></figure>

Details allows you to retrieve the access information for a direct database connection.

Settings allows you to enable and use an allow list, to limit direct database connections to specific IP addresses.

1. Get your database's public IP
2. Get your database credentials
3. Settings Panel
4. Add an IP address to your allow list

Clicking both of the "Get" buttons will provide us with the database IP and two sets of credentials, full-access and read-only.

<figure><img src="../../.gitbook/assets/CleanShot 2023-08-21 at 07.47.08.png" alt=""><figcaption></figcaption></figure>

From this panel, you can also **revoke and re-generate** your database credentials, should the need arise.

#### Establishing a Database Connection (Example)

You can use any application you'd like that is capable of connecting to a PostgreSQL database. In this example, we'll be using Navicat.

Select 'Connection' in the top-left, and fill in your credentials and the IP recieved from Xano.

<figure><img src="../../.gitbook/assets/CleanShot 2023-08-16 at 13.39.09.png" alt=""><figcaption></figcaption></figure>

Click 'Save' to save the connection. We can now navigate the PostgreSQL database from Xano using Navicat. We can even add / update data, run queries, etc...

<figure><img src="../../.gitbook/assets/CleanShot 2023-08-16 at 13.41.35.gif" alt=""><figcaption></figcaption></figure>



## Upgrading an Instance

**Why should you upgrade?**\
Free accounts come with **one workspace that shares resources with other Xano customers**. It also is limited on capabilities such as storage, database records, and processing power.  You'll easily be able to prototype most of your application in this type of account, but upgrading to a paid plan will give you a more powerful instance that can scale with your needs. [View plan pricing and details](http://www.xano.com/pricing).

**What can I upgrade to?**\
If you are on our Launch plan, your next step would be Scale1x. Upgrades from Launch to Scale1x are able to make use of a 48 hour no questions asked refund policy -- if you find that Scale1x is not solving the requirement that prompted the upgrade, reach out to support within 48 hours and we'll roll you back to Launch and refund the difference.

If you are currently on a Scale plan and considering a higher tier, we can work with you to trial higher Scale tiers by reaching out to support.

**What does upgrading your instance actually do?**\
Upgrading your instance migrates your data and business logic to a brand new, faster instance. If you upgrade to the Scale package, you'll be put on your own dedicated instance for maximum performance and scalability.

**How long does upgrading take?**\
Upgrading an instance takes seconds to complete.

### **Does upgrading happen automatically once I pay?**

**You will need to update your API URL ORIGIN if:**

* You are adding certain features to your plan, such as Static IP
* You are upgrading from **free** to **paid**
* You are changing your server region

**You do not need to update your API URL ORIGIN if:**\
&#x20;\- You are upgrading from a PAID to PAID instance and not changing your server location.

## **How to upgrade an instance**

### **Step 1 - Go to the Billing page**

Go to the Billing section within Xano. You can get there by clicking "Billing" in the side menu on the instances page. You can also click your initials when you're in your workspace and clicking the "Billing" link.

<figure><img src="../../.gitbook/assets/CleanShot 2023-08-23 at 11.07.49.png" alt="" width="563"><figcaption></figcaption></figure>

### **Step 2 - Select a plan**

Click the **Change Plan** button on the instance you want to upgrade.&#x20;

<figure><img src="../../.gitbook/assets/CleanShot 2023-08-23 at 11.08.49.png" alt=""><figcaption></figcaption></figure>

On the next screen, you'll be able to change your current plan, modify your billing schedule, add additional upgrades, or change your region.

<figure><img src="../../.gitbook/assets/CleanShot 2023-08-23 at 11.13.14.png" alt=""><figcaption></figcaption></figure>

Once you've made your selections, click the green button at the bottom to proceed to checkout.

### **If your base API URL is changing...**

{% hint style="warning" %}
### **THIS IS THE MOST IMPORTANT STEP**

**To ensure a seamless transition for your users, please read this section carefully.**
{% endhint %}

#### **Click the "Start Upgrade" button...**

Don't worry, this doesn't start the upgrade right away. This will bring up a dialog telling you what you need to be aware of before continuing.

#### Write down your new API URL Origin

{% hint style="info" %}
**What is an API URL ORIGIN anyway?**\
It's the first part of any API endpoint you have hooked up to the front-end. See below for an example

```
YOUR API URL ORIGIN (example)
https://xd6b-cfde-62f6.dev.xano.io/

YOUR FULL API ENDPOINT URL FOR 'GET USERS' (example)
https://xd6b-cfde-62f6.dev.xano.io/api:4qSkfrOl/user
```
{% endhint %}

### Step 4 - Update your Front-end with the new API URL ORIGIN if you are upgrading from the FREE plan or changing your server region.



### Step 5 - Complete your upgrade

Once you follow the steps above, type **I UNDERSTAND** into the box and click the button "Start upgrade now".&#x20;







