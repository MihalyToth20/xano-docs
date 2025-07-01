# Airtable to Xano

## Why migrate from Airtable to Xano?

### Scalability & Limits

At the time this document was last updated, Airtable's published pricing models offer a maximum of 500,000 records per base, and 1,000 GB of file storage.

Xano's database does not have a record limit, or a limit on file storage. We can scale infinitely to meet your data needs.

### Performance & Capability

Airtable themselves say that it is not intended to use their platform for an application backend.

> For this reason, it is important to note that Airtable is not intended to be a backend hosting service/real-time database like Heroku, Parse, Firebase, or MongoDB. Instead, Airtable is primarily designed for use cases where all users will be directly interacting within the Airtable UI. \
> \
> &#xNAN;_&#x46;rom_ [_**Troubleshooting Airtable base performance**_](https://support.airtable.com/docs/troubleshooting-airtable-performance)

Airtable says this is because as the volume of requests to your Airtable base increases, it may not be able to perform as expected under such load.

Xano is built from the ground up to be a capable, scalable, and secure backend solution.

***

## Migrating Airtable data to Xano

{% include "../../.gitbook/includes/airtable-import.md" %}
