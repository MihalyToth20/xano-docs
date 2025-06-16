---
description: >-
  Database Relationships are used to define related data between one or more
  tables.
---

# Relationships

{% hint style="info" %}
**Quick Definition**

Database relationships show how different tables of data connect to each other - like how a customer's ID links their personal information to their complete order history. These relationships can be one-to-one (one person, one social security number), one-to-many (one customer, many orders), or many-to-many (many students can take many classes).
{% endhint %}

## What are database relationships?

Database relationships are crucial connections that link pieces of data across different tables in a database. Imagine it like a web of information where each piece is connected in a logical way.

For example, consider a library: each book has one unique ISBN, which is similar to a one-to-one relationship. Many books can belong to one category, which reflects a one-to-many relationship. Finally, readers may borrow many books, and many copies of a book can be borrowed by different readers, representing a many-to-many relationship. These connections help in organizing data efficiently, allowing more straightforward retrieval and management of the information stored.

Typically, when discussing database relationships, you'll see two terms that are important to remember:

* **Primary Key -** The primary key inside of a database table is the key that's used to maintain uniqueness between records — a value that's always different for each record. Usually, this is an `id` field.
* **Foreign Key** - The foreign key inside of a database table refers to a field that references a primary key inside of another table. For example, a table of `books` might have a field that contains foreign keys from an `authors` table.

### Types of Relationships

In Xano, there are three primary ways tables can be related:

#### 1. One-to-One

This is like a person and their unique passport. Each data entry in one table relates to exactly one entry in another table.

#### 2. One-to-Many

Think of a parent and their children. A single entry in one table can relate to multiple entries in another. For example, one teacher can teach many students.

#### 3. Many-to-Many

Similar to students enrolling in various courses, any entry in one table can relate to multiple entries in another.



***

## Why Use Relationships?

* **Data Consistency**: Ensures all references are valid.
* **Reduced Redundancy**: Minimizes repeated data.
* **Efficient Data Retrieval**: Makes it easier to access related data.

Understanding these basic concepts can simplify how you view databases and highlight why tools like Xano are powerful for managing data.

***

## Using the Table Reference Field Type

When you add a table reference field to a database table, that field simply stores the IDs of the record(s) being referenced; the data is not actually duplicated. To access the actual data is typically done via an add-on as part of a function stack.

### Auto-Complete

Auto-Complete allows you to configure how the referenced records look inside of other tables.

For this example, we have two tables: `user` and `userRole`

<figure><img src="../../.gitbook/assets/CleanShot 2024-12-15 at 17.50.17.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/CleanShot 2024-12-15 at 17.50.57.png" alt=""><figcaption></figcaption></figure>

{% @arcade/embed flowId="RWmuIhxQkGk0OoOiBCdD" url="https://app.arcade.software/share/RWmuIhxQkGk0OoOiBCdD" %}

{% stepper %}
{% step %}
### Navigate to the table you are referencing data from to adjust the Auto-Complete settings.
{% endstep %}

{% step %}
### Click the three dots in the top right and choose Auto-Complete
{% endstep %}

{% step %}
### Click 'Customize' if this is your first time enabling Auto-Complete customization on this table.
{% endstep %}

{% step %}
### Click 'Add Column' to add a new field that will appear on tables that reference this one.
{% endstep %}
{% endstepper %}

***

## Relationship View

You can quickly observe all of your table relationships (that utilize the table reference field to contain the foreign keys of other records) by selecting the "Show table relationships" option when viewing your database tables.

<figure><img src="../../.gitbook/assets/CleanShot 2025-06-16 at 09.10.54.png" alt=""><figcaption></figcaption></figure>

From this view, you can visualize all of your table relationships, and click/drag the tables to organize the view based on your preferences.

<figure><img src="../../.gitbook/assets/CleanShot 2025-06-16 at 09.13.38.gif" alt=""><figcaption></figcaption></figure>

<sup>_Please note that customization in this view are not saved._</sup>
