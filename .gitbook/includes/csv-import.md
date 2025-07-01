---
title: CSV Import
---

Xano's CSV file import is ultra-robust. Import your file with confidence, even if you have millions of records. The import process runs on Xano's special import service, which has dedicated resources separate from your instance, so it can handle all of your data no matter how large it is.

The CSV file import allows you to create a brand new table from scratch and will generate the schema automatically.&#x20;

Additionally, you can edit existing records if the file can be mapped to a primary key or append data to an existing table.&#x20;

Uploads of over 5,000 records will be performed in the background. You can easily monitor the import's progress in the settings of your workspace and will be notified on Xano and via email when the import is complete.&#x20;

## Add a New Table

From the database select Add Table.

![Select Add Table and Select Import Data.](<../assets/CleanShot 2021-12-07 at 15.52.56.png>)

When the right panel opens up, select **Import Data** and choose the **CSV** file option.

<figure><img src="../assets/CleanShot 2024-07-12 at 15.56.11.png" alt=""><figcaption><p>Select import data from CSV.</p></figcaption></figure>

Next, drag and drop a CSV file onto the uploader or browse the files on your computer for the file you wish to upload.

<figure><img src="../assets/CleanShot 2025-05-15 at 10.24.16.png" alt=""><figcaption></figcaption></figure>

Once you select a CSV file, the preview of your CSV will open up. The preview will display the first 100 rows of your file. You can make any final adjustments to the data types, primary key, or table name here before beginning the import.

<figure><img src="../assets/CleanShot 2025-05-15 at 10.26.30.png" alt=""><figcaption></figcaption></figure>

Xano will try to automatically detect a primary key field. Currently, only integers are supported for the primary key field. The drop-down will show any fields compatible to be a primary key. If there is no primary key, then Xano will create the primary key automatically.&#x20;

Once you are ready, click <mark style="background-color:blue;">Upload</mark> . If you are uploading over 5,000 records, then your upload will be performed in the background. You can monitor the progress of your upload from the settings page of your workspace. Once your background upload is complete a green banner will appear notifying you to refresh your browser and an email notification will be sent with confirmation of a successful import.&#x20;

{% hint style="info" %}
# Add to an Existing Table

You can import a CSV to an existing table if you'd like to add records to it. The process is the same as importing to a new table — just access the import option from inside of the database table you want to add to. \
\
![](<../assets/image (95).png>)

During the import, make sure to review the columns and make sure they are mapped to the right columns that already exist in your database table.\


![](<../assets/image (96).png>)
{% endhint %}

{% hint style="info" %}
# Edit Records in an Existing Table

Just like adding records to an existing table, you can also use a CSV upload to **edit records** in a table.

The only difference between adding a new table or adding to an existing table is that you'll need to make sure your CSV contains an `id` field. This is what Xano will use to find the records to apply changes to.
{% endhint %}

## Valid CSV Format

It's important that you use a valid CSV file format in order to successfully import your data. If there is an issue with initiating the upload then this could likely be the issue.

### What is a valid CSV file format?

A CSV stands for a comma-separate file, which is a delimited text file that uses a **comma** to separate values. The importer does not support other separators, such as semicolons. Each line of the file is a data record. Each record consists of one or more fields, separated by commas.

* The first row must contain the column names - not the file name or any other data.&#x20;
* The second row begins the values. They should be in the same order as the columns they belong to.
* Each row should have the same amount of values as there are columns.&#x20;
* **Enclosure characters** are required when working with text strings that contain quotation marks. This is because if a quotation mark is detected, this is typically something that would mark the beginning or end of a value. You can use a **double quote ("")** to dictate if a value should contain this quotation mark somewhere inside the value.
* CSV files should be UTF-8 encoded. If you're having trouble importing your CSV properly in Xano and have determined you are using both the proper separator and enclosure characters, please make sure your file us UTF-8 encoded. This ensures that there are no special characters that might not be supported in Xano.

<details>

<summary>UTF-8 Encoding in Notepad (Windows)</summary>

1. Open your file in Notepad.
2. Click File > Save As...
3. Click "Save As Type", and choose All Files.
4. Click "UTF-8" in the Encoding dropdown.
5. Save the file.

</details>

<details>

<summary><strong>UTF-8 Encoding in Google Sheets (All platforms)</strong></summary>

1. Open your file in Google Sheets
2. Click File > Download > Comma separated values (CSV)
3. The file will be downloaded in CSV format using UTF-8 encoding.

</details>

<details>

<summary>UTF-8 Encoding in Numbers (Mac)</summary>

1. Open your file in Numbers
2. Click File > Export To... > CSV
3. In the "Text Encoding" dropdown, choose UTF-8
4. Save the file.

</details>

{% file src="../assets/Xano-Sample-CSV.csv" %}
**Here is a sample CSV file demonstrating both the proper separator and enclosure characters.**
{% endfile %}

### How can I check my CSV file format?

You can review the format of your CSV file format in a number of ways. Open the file in Text Editor, Visual Studio Code, or another code editor. You can also do an online search for CSV file format validators and use an online service.&#x20;

**How can I edit my CSV file format?**

Tools like Text Editor, Visual Studio Code, and other code editors allow you to make any necessary edits to your file and save the changes. When opening the file from your computer, right click and choose open with to choose from the different options available on your computer.
