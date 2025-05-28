---
title: table names
---

# Custom SQL Table Names <a href="#table-names" id="table-names"></a>

From your Workspace settings, you can enable **Custom SQL Table Names**.

By default, Xano assigns each table a SQL name in the format mvpw\_ (e.g., mvpw1\_3). This identifier works for direct access, but can be difficult to read or use with direct queries and database tools.

You can replace this with a custom SQL name to make queries more intuitive and improve compatibility with external connectors.

If you change a table's SQL name, be sure to update any queries that reference the old name to avoid breaking functionality.

Once you've enabled **Custom SQL Table Names**, head to any database table's settings, and click Manage next to SQL Table Name.

<div align="left"><figure><img src="../assets/CleanShot 2025-05-22 at 10.46.21.png" alt="" width="373"><figcaption></figcaption></figure></div>

| <div><figure><img src="../assets/CleanShot 2025-05-22 at 10.48.26.png" alt=""><figcaption></figcaption></figure></div> | <p></p><ul><li>Leave the SQL Table Name field blank to use Xano’s default SQL table name, which follows the format mvpw&#x3C;workspaceID>_&#x3C;tableID> (e.g., mvpw1_3).</li></ul><ul><li>SQL table names must be globally unique across all workspaces.<br><strong>Hint</strong>: Use the Custom Prefix to ensure uniqueness across workspaces.</li></ul><ul><li>Datasources automatically add a suffix based on their environment. For example, <strong>users</strong> becomes <strong>users_test</strong> in the test datasource.</li></ul><ul><li>To reuse the same base name across workspaces, use a workspace-specific prefix (e.g., projA_users, projB_users).</li></ul> |
| ---------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
