---
title: Importing Multi Form Records
---
# Importing Multi Form Records
If you have multiple records that you want to import into multiple forms, Kora provides a way to import all of those records at once. Rather than performing multiple imports to submit records into a form, you may perform one multiform record import. This will require formatting your records in a particular way. This is a slightly different process than [importing records into a single form](../records/importing_a_record.md). You will have to format your records correctly into a csv, json or xml file. Examples of the correct file formats are provided in the *File Formatting* section below.

## Navigating to the Import Page
Navigating to *Import Multi Form Records* page can take place from either the [dashboard](../projects/accessing_and_managing_projects_from_the_dashboard.md) or from a project's homepage. These options are shown in the next two sections. Either of these options will bring you to the *Import Multi Form Records* page (shown below) where you can import multiple record files to multiple forms

    <img style="display:block;margin:auto;max-width:100%" src="../records-img/importing_multi_form_records_3_annotated.png" title="Import Multi Form Records Page">

### Navigating from the Dashboard
From the dashboard, you are able to navigate to the *Import Multi Form Records* page from a project block by clicking on the **Quick Action** icon.

    <img style="display:block;margin:auto;max-width:100%" src="../records-img/importing_multi_form_records_1_annotated.png" title="Use Quick Actions">

### Navigating from your Project Homepage
Alternatively, you may select **Import MF Record Setup** from the project homepage using the Kora menu.

    <img style="display:block;margin:auto;max-width:100%" src="../records-img/importing_multi_form_records_2_annotated.png" title="Using the Kora Menu">

## Preparing the Data
Before you begin importing multiple records into multiple forms, you will have to prepare your data into a format that Kora will be able to understand. Make sure that the following is taken into consideration for your data:

* Each form should have its own file

* Every single field column and datatype within an imported file should conform to the Kora datatype standard, which can be found in the below *file formats* section (This is extremely important).

* For every sheet with 1 or more associators connected to a different sheet within the dataset, the identifier column needs to be duplicated and labled as column header kidConnection. The formatting allows you to create associations between records that do not already exist.

* Multi-field field types have to be imported as XML or JSON (not CSV).

* All attached files should be compressed into a zip file. If the files are within folders, then the directory path must be included with the dataset listing in order for the connection to be made.

### File Formats
The files in this section provide the data structure that your imported records will have to conform to. Data not structured as in the files below will be unreadable to Kora. There are three formats that you are able to upload files: 1) .csv, 2) .json, and 3) .xml. Below you can view and download example files for each file type.

#### CSV Format
This file format uses *Comma Separated Values* to describe the fields you are attempting to import. CSVs are commonlly created in Microsoft Excel. You can go to the bottom of this section to download an example CSV file or use the following steps to start a new CSV file:

1. In Excel go to the File menu and click Save As

2. Identify a filename and location

3. Select File Format: CSV UTF-8.

4. Click Save

5. You will see the following prompt. Click OK

    <img style="display:block;margin:auto;max-width:100%" src="../records-img/importing_multi_form_records_2_annotated.png" title="Using the Kora Menu">

6. Then you'll see the following prompt. Click Yes.

    <img style="display:block;margin:auto;max-width:100%" src="../records-img/importing_multi_form_records_2_annotated.png" title="Using the Kora Menu">

7. Close the spread sheet.This file can now be used to create additional csv files and to add your records in.

Do not edit csv files in Microsoft Excel and do a regular save. This could potentially add Microsoft garbage into your file. Instead it is recommended to edit csv files only in a text editor such as Atom or Notepad++.

It is also reccomended that you open every single csv file in a text editor and do a general check. Especially check for: blank rows at the end of each document and the continued presence of special characters/diacritics (not UTF-8 encoded)

An example of the CSV format is embedded below. Follow the **import_example_csv.csv** link to github.com in order to download this file.

<script src="https://gist.github.com/0Redfeather/0258f81c076428893e7c848153255839.js"></script>

#### JSON Format
The JSON file format uses *JavaScript Object Notation* to describe the fields for the records you are attempting to import. You will need a text editor to create and edit JSON files. An example of the JSON format is embedded below. Follow the **import_example_json.json** link to github.com in order to download this file.

<script src="https://gist.github.com/0Redfeather/17692e3550e94330d1fc7b85c3fd66a4.js"></script>

#### XML Format

The XML file format stands for *Extensible Markup Language*. It is a markup language designed to encode data that is both machine and human readable. You will need a text editor to create and edit XML files. An example of the XML format is embedded below. Follow the **import_example_xml.xml** link to github.com in order to download this file.

<script src="https://gist.github.com/0Redfeather/64252b8a700acf030cad141e2aefe1f4.js"></script>

## Importing
Once you have your records formatted correctly, you can begin importing your records into Kora. This will require 3 steps: uploading, matching fields and importing.

### Uploading records

1. Upload the correctly formatted record files by clicking the **Add New File** button. After clicking the button, you'll be able to select the files you want to upload from your computer.

    <img style="display:block;margin:auto;max-width:100%" src="../records-img/importing_multi_form_records_3_annotated.png" title="Add New File">

2. Once you've selected the files you want to upload, select the forms that you want the records to be uploaded to by clicking **Select Some Options**. A dropdown menu will appear, this is where you can select forms that you have already created.

    <img style="display:block;margin:auto;max-width:100%" src="../records-img/importing_multi_form_records_4_annotated.png" title="Select Forms">

3. If you have zipped files that correlate to the records you are already importing, you may add them below. These records should have the same format as the records that you are already importing.

    <img style="display:block;margin:auto;max-width:100%" src="../records-img/importing_multi_form_records_5_annotated.png" title="Use Zipped Files">

4. Once you have all of your files uploaded, press the **Upload Record Import Files**

    <img style="display:block;margin:auto;max-width:100%" src="../records-img/importing_multi_form_records_6_annotated.png" title="Upload Record Imports">

### Field Matching

5. This will bring you to the *Field Matching* tab on the *Import Records* page. This page allows you to associate the field names between the records you are uploading to the form you are importing the records to. Select fields if applicable on the right column of the page. You will want to associate or match fields based on type. If you need information about field types, visit the [Understanding Field Types](/forms/understanding_field_types.md) guide.

		* **Note**: If a field is *required* in the form you are importing records into, you must associate an incoming field to one that is being imported.

		<img style="display:block;margin:auto;max-width:100%" src="../records-img/importing_a_record_7_annotated.png" title="Field Matching">

6. Click the **Upload Records** button at the bottom of the screen.

		<img style="display:block;margin:auto;max-width:100%" src="../records-img/importing_a_record_8_annotated.png" title="Upload Records">

### Import your records

5. A loading page will open informing you that your import has begun. Depending on the number of records you are importing, it may take several minutes to complete. Do not close the page or browser until completion. When the import is complete, you will be automatically brought to the *Import Records Complete* page.

		<img style="display:block;margin:auto;max-width:100%" src="../records-img/importing_a_record_9_annotated.png" title="Loading Page">

6. On this page you can view how many records were successfully imported and have the option to view the imported records by clicking on the *View Imported Records* button.

		<img style="display:block;margin:auto;max-width:80%" src="../records-img/importing_a_record_10_annotated.png" title="Field Matching">

#### Failed Record Import

There are several reasons a record import will fail. If a required field was not assoicated with an uploaded field (matched), you will be informed how many records out of the total were successfuly imported on the *Import Records Complete* page (example: 0 of 1 Records Successfully Imported).

Your record(s) will not import if you associate different field types.

#### Import Completition and Error Reporting

		<img style="display:block;margin:auto;max-width:100%" src="../records-img/importing_a_record_11_annotated.png" title="Failed Records Report">

You can download the failed records and their report to identify the problem with the import. The **Failed Records Report** will state which fields are required. If you did not match your field types correctly, the *Failed Records Report* may give you an error: {"18":"Unable to determine error. This is usually caused by a structure issue in your CSV\/XML\/JSON, or an unexpected bug in kora."}. If this occurs, we recommend trying to import your record(s) again after checking how the fields should be matched.

You can then try importing the record(s) again or view the successfully imported records using the buttons on the page.
