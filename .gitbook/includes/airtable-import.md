---
title: Airtable Import
---

{% stepper %}
{% step %}
## Head to the database and click ![](<../assets/CleanShot 2025-01-25 at 16.07.45.png>)
{% endstep %}

{% step %}
## In the new table menu, choose Import Data > Import From Airtable
{% endstep %}

{% step %}
## Provide your Airtable personal access token

You can generate a personal access token in Airtable by heading to your account settings, and from there visiting the **Developer Hub**.

Choose **Personal Access Tokens** from the left-side navigation, and create a token with the following scopes:

```
data:base.read
schema:base.read
```
{% endstep %}

{% step %}
## Select the tables and/or views you want to import into Xano, and confirm your selection
{% endstep %}
{% endstepper %}

***

## Rebuilding Automations

While there is no direct migration of your Airtable automations to Xano, we want to make it as easy as possible to rebuild. Please see the table and linked resources below for common Airtable -> Xano functionality translations. Click on the Xano Function name to be taken to Xano's documentation, or review the video examples provided.

| Airtable Function      | Xano Function                                                                                    | Video Example                                 |
| ---------------------- | ------------------------------------------------------------------------------------------------ | --------------------------------------------- |
| Create Record          | [Add Record](../../the-function-stack/functions/database-requests/add-record.md)                 | [Video Example](https://youtu.be/k0GpUdsRkL0) |
| Update record          | [Edit record](../../the-function-stack/functions/database-requests/edit-record.md)               | [Video Example](https://youtu.be/rTeJamc_MYE) |
| Find records           | [Query all records](../../the-function-stack/functions/database-requests/query-all-records/)     | [Video Example](https://youtu.be/-XjcXEtPNmk) |
| Conditional logic      | [Conditional statement](../../the-function-stack/functions/data-manipulation/conditional.md)     | [Video Example](https://youtu.be/QR4UJ2GpYDo) |
| Repeating group        | [For each loop](../../the-function-stack/functions/data-manipulation/loops.md)                   | [Video Example](https://youtu.be/AGe5JN0rZ2M) |
| At scheduled time      | [Background task](../../the-function-stack/building-with-visual-development/background-tasks.md) | [Video Example](https://youtu.be/SDXWVhBGKmQ) |
| Link to another record | [Table reference](../../the-database/database-basics/field-types.md#table-reference)             | [Video Example](https://youtu.be/z-TwxiQOIBs) |
| Lookup                 | [Addons](../../the-function-stack/functions/database-requests/query-all-records/#using-addons)   | [Video Example](https://youtu.be/z-TwxiQOIBs) |
