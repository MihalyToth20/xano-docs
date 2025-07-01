---
icon: person-running-fast
---

# Getting Started Shortcuts

## Getting Started Shortcuts

When entering the database in Xano, you're presented with some quick shortcuts to get started faster. This section of our documentation is designed to accompany those shortcuts.

<table data-view="cards"><thead><tr><th></th></tr></thead><tbody><tr><td><span data-gb-custom-inline data-tag="emoji" data-code="2728">✨</span> <strong>Modify your table schema with AI</strong></td></tr><tr><td><span data-gb-custom-inline data-tag="emoji" data-code="1f4d4">📔</span> <strong>Import data from a CSV</strong></td></tr><tr><td><img src="../.gitbook/assets/image (98).png" alt="" data-size="line"> <strong>Import data from Airtable</strong></td></tr><tr><td><span data-gb-custom-inline data-tag="emoji" data-code="1fa84">🪄</span> <strong>Generate test records for table</strong></td></tr><tr><td><span data-gb-custom-inline data-tag="emoji" data-code="1f4a1">💡</span> <strong>Create flows from database triggers</strong></td></tr></tbody></table>

## Modify your table schema with AI

{% stepper %}
{% step %}
### Choosing this option opens our AI Database Assistant.

The database assistant can be used to modify your database schema. You can prompt it to add or edit existing tables, delete tables, and help you design your database while following best practices.
{% endstep %}

{% step %}
### Prompting the AI Database Assistant

Your prompts to the assistant can be as simple or as complex as necessary. Here's a quick example:

<div align="left"><figure><img src="../.gitbook/assets/CleanShot 2025-06-19 at 08.44.27.png" alt="" width="563"><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### Approving Changes

Each change that the assistant suggests will need to be approved individually. This ensures that no changes are made that you do not explicitly review first. In addition, some changes rely on the previous change being completed — the assistant will notify you of this as you continue.

For each table being created, you can choose to just create the table, or create the table and [default CRUD API endpoints](../the-function-stack/building-with-visual-development/apis/#auto-generated-apis) at the same time.

<div align="left"><figure><img src="../.gitbook/assets/CleanShot 2025-06-19 at 08.46.56.png" alt="" width="320"><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### Review and Iterate

You can leave and return to the Database Assistant at any time. Here's the final schema we ended up with using the above example of an Airbnb-style application.

<figure><img src="../.gitbook/assets/CleanShot 2025-06-19 at 08.48.11.png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

***

## Import data from a CSV

{% include "../.gitbook/includes/csv-import.md" %}

***

## Import data from Airtable

{% include "../.gitbook/includes/airtable-import.md" %}

***

## Generate test records for table

{% include "../.gitbook/includes/generating-test-data.md" %}

***

## Create flows from database triggers

{% include "../.gitbook/includes/database-triggers.md" %}
