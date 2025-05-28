---
title: table format
---

# Table Format

{% hint style="info" %}
# Table Formats - Only relevant for direct database connections

As of our **1.68 release (5/27/25)**, all new workspaces will default to the standard SQL column format for tables. For all workspaces created prior to that, read below.
{% endhint %}

Your tables can be created using one of two formats:

* **JSONB format**
  * This creates your tables with two columns:
    * `id` - the ID of the record
    * `jsonb` - contains a JSON representation of the entire record
* **Standard SQL format**
  * This creates a more standard table layout. Instead of a jsonb column, each column is written separately.

If you are using the [direct-database-connector.md](../../xano-features/instance-settings/direct-database-connector.md "mention"), Standard SQL format is usually recommended.

## Converting Tables from JSONB to standard SQL

{% hint style="warning" %}
This change is **permanent**. Most users will not need to adjust these settings, and they only impact your experience if you are connecting to your database directly via third-party tools.
{% endhint %}

{% stepper %}
{% step %}
## From your workspace dashboard, click the settings icon in the upper-right corner, and click Settings.


{% endstep %}

{% step %}
## Scroll down to the Database Preferences section, and check the option to 'Use standard SQL columns for new tables'

<div align="left"><figure><img src="../assets/CleanShot 2025-05-22 at 10.38.36.png" alt="" width="345"><figcaption><p>This setting must be enabled before you can convert existing tables to the new format.</p></figcaption></figure></div>
{% endstep %}

{% step %}
## Convert your table(s) from your workspace settings, or the settings of any table.

From the migration panel, select any of the tables you'd like to convert, and confirm your choices. The migration will begin immediately.

<div align="left"><figure><img src="../assets/CleanShot 2025-05-22 at 10.41.30.png" alt="" width="375"><figcaption></figcaption></figure></div>
{% endstep %}
{% endstepper %}
