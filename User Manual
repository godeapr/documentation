![afbeelding.png](/.attachments/afbeelding-9b8f9f3b-f818-467b-858d-be163129e381.png)
Welcome to the user manual of Godeapr®, the application that finds Personal Identifiable Information (PII) in files, databases, and other sources. This document will explain how the Godeapr® application should be used via a step-by-step approach with clear visuals.

[[_TOC_]]

# Installation
Godeapr® can be installed on a Windows, Linux, or Mac machine as a native desktop application or as a command line tool. This user manual focuses on the native desktop application. During the installation, a management password needs to be chosen. With only this password, you can access the application.  

<-- Add visuals about installation -->

# Starting the application
After Godeapr® is installed, you will find the application between your regularly installed apps. To start Godeapr®, double click the icon from the taskbar.

![afbeelding.png](/.attachments/afbeelding-6dfa257a-f49a-4481-87c9-26f2b58e7c81.png)

After start-up, your will be prompted with a welcoming page. To enter the application, select the deapr logo which will ask you to enter your management password chosen during installation. Without this password you will not be able to enter the application.

![afbeelding.png](/.attachments/afbeelding-36480689-9de1-483a-aee9-c2fe9e663539.png =700x)

Once a correct password is given, you will be led to the home page where there are three main actions: 
- **Scan**: start a new scan
- **Identify**: analyze a previous scan
- **Comply**: export results

![afbeelding.png](/.attachments/afbeelding-d6335f8b-c607-426f-ae7d-3b25ce25d1d7.png  =700x)

# Scan
When starting a new scan, there are three different source types to connect to:
- Files
- Databases
- APIs

## Files
When scanning files on PII, you are able to select specific files or whole folders. This folder can be a local folder on your machine, a mapped network-drive which is used throughout your organization, or locally mapped SharePoint directories for example. You can select multiple directories and files which will all be listed in the view.  

There is also an option to only scan for **structured** files. Meaning, files containing data in a column-row format, like .csv, .xls(x) or structured .txt files. When scanning structured files, you will get additional information on where PII is found on **deviating** locations in those structured files. More information on deviating findings can be found [in this chapter](https://dev.azure.com/Datamo/Horizon/_wiki/wikis/Horizon.wiki/39/01.-Godeapr-user-manual?anchor=regular-vs-deviating). When scanning for structured files only, the view will directly indicate which files will probably be scanned and which not by graying-out non-structured files.

![afbeelding.png](/.attachments/afbeelding-103292d8-c222-4a7b-96e6-91f259ef87c6.png =700x)

You can remove specific files from the list if you do not want to include them in the scan by selecting the trashcan icon. The (**!**) icon indicates that a (sub)directory in the view contains files that will not be scanned. The (**X**) icon indicates that the file will not be scanned.

### Meta scan
When satisfied with the file selection, click next to trigger the meta scan. The meta scan scans files on metadata that can be used to filter out files you are not interested in with respect to PII. Reasoning is that some network-drives or SharePoint folders can contain hundreds of thousands of files and by using the meta filters, you will only scan relevant files. 

Filters:
- **Creation date**
- **Last access date**
  - Note that when opening a specific folder containing the folder in a file explorer or even programmatically might already alter the access date.
- **Last modified data**
- **Last Godeapr® scan**
  - Filter based on when the file was last scanned by Godeapr®.
- **Owner**
  - Often the creator of the file.
- **Extension**
- **Size**

Depending on the filter selection, files will be grayed-out, meaning they will not be considered in the scan.

There is also a tab 'not scannable', meaning this file cannot and will not be scanned by our scanning algorithm. A file will be marked as not scannable, when we do not have a suitable way to extract the content of the file to search for potential PII. Examples are executables, temporary files, hidden files, binary files etc. The list of files that will be scanned is as follows:

```
.bmp | .csv | .doc | .docm | .docx | .dot | .eml | .msg | .gif | .htm | .html | .jpe | .jpg | .jpeg | .json | .md | .mht | .log | .odt | .pdf | .plain | .png | .ppxt | .psv | .rtf | .tif  | .tiff | .tsv | .txt | .xlm  | .xls | .xlsx
```
Godeapr® does not just scan plain text in for example ``` .docx ``` files (word documents), but it also processes images in the document in case there are any. Besides, also attachments found in ```.eml``` files (emails) will be scanned for PII. If there is PII found on e.g. the attachments of the ```.eml``` Godeapr® will indicate that the source is the ```.eml``` for those findings.

![afbeelding.png](/.attachments/afbeelding-3e1941f5-c220-47c6-bdd8-4583a6f1db6d.png =700x)

Proceed to [preferences](https://dev.azure.com/Datamo/Horizon/_wiki/wikis/Horizon.wiki/39/01.-Godeapr-user-manual?anchor=preferences) if you want to follow the next step when scanning a filesystem.

## Databases
When scanning databases on PII, you are able to setup several database connections in Godeapr®. When selecting 'new connection', you will be prompted with a form requesting relevant information for the database you would like to connect to. A 'standard' database connection requires a 
- server
  - the location of the database
- port
  - the entry point on that server
- username
  - the user that has access to the databases and tables you want to scan
  - if want to prevent Godeapr® to scan specific databases or tables, you should restrict this user from doing so
- password
  - the password for the specific user

![afbeelding.png](/.attachments/afbeelding-6c1fd666-b3c3-4824-b220-74113eec4284.png =700x)

Optionally you can save the password. If you prefer not to, you will be prompted with a request to enter the password manually each time you want to run a scan with that specific database connection. Before saving the connection details, it is wise to test the connection first. Godeapr® will check whether it can reach the database or not. Please note that no firewalls or other network rules should be blocking the request from the location where Godeapr® is installed. 

If the database type you would like to scan, is not listed in this overview, please contact info@deapr.com to check whether we can add the database type to the possible connections.

### Column-mapping
If the database connection is successful, when clicking 'next', Godeapr® extracts the column names from the tables and databases it has access to. Thereafter, you can optionally start a column-mapping activity where column names are mapped to a specific PII which you expect to be in that column. This activity is very useful in determining 'regular' PII versus 'deviating' PII. More information on the difference is explained [here: Regular vs. Deviating](https://dev.azure.com/Datamo/Horizon/_wiki/wikis/Horizon.wiki/39/01.-Godeapr-user-manual?anchor=regular-vs.-deviating).

Each time you change a column-mapping, the change will immediately be saved to the database. Also when you start a new scan with the same database connection, it remembers the mapping you did for a previous scan, so it should be an one-time activity only. If you do not know what kind of PII might be existing in a specific column, you can leave it 'unknown' and Godeapr® will predict the PII type for the column itself. 

![afbeelding.png](/.attachments/afbeelding-5d58a36c-c52e-4b61-9bc3-0edb848fbd67.png =700x)

The rationale is that often database columns have a very specific purpose within a system. One specific column might be used for saving names of customers while other columns just contain a regular timestamp of the creation date of that record. Giving Godeapr® more information on where it should and where it should not find specific PII types, gives you more accurate insights in where PII should not be existing in your database. 

### Regular vs. Deviating
Godeapr® tries to find PII at 'deviating' locations. It determines whether a found PII type is deviating based on three methods, evaluated in the following order:

1. Based on the column-mapping (more info [here](https://dev.azure.com/Datamo/Horizon/_wiki/wikis/Horizon.wiki/39/01.-Godeapr-user-manual?anchor=column-mapping)). Example: when during the column-mapping stage a particular column is mapped to PII type IBAN, all found IBAN's will be identified as **regular** since we mapped the column to IBAN's. Therefore we also expect to find IBAN's in that particular column. On the other hand, all other PII types found in that column, will be marked as **deviating**. Meaning, we did not expect to find any other PII type in that column besides IBAN's.

2. If there is no PII mapped to a particular column, Godeapr® will estimate a column's PII type based on the name of the column. Often database columns already hint on what the content of the specific column is. For example _ADDR_ hints to _ADDRESS_ and _CC_ hints to _CreditCard_. If Godeapr® was able to estimate a PII type based on the column names, hits for that specific PII type are marked **regular** where all other found PII types will be marked **deviating**.

3. If Godeapr® was not able to determine a PII type based on the column name, it will determine a PII type based on the column data. Where it is determined that if one column is filled with more than 70% of one specific PII type and less than 10% of any other PII type, the column will be mapped to that specific PII type. All findings based on that specific PII type are **regular** and all others are **deviating**. 

If Godeapr® was not able to determine a PII type based on the column data, all found PII types will be marked as **deviating** since there was no reason to believe that those PII types are at a **regular** location, specifically designed to hold that PII.

Note: since the above logic can only be applied on column-based datasets, there is no way to determine **deviating** findings for a scan on unstructured filesystems. 


## Preferences
_This view is similar for scanning files or databases_.

When the setup is satisfactory, clicking next brings you to an overview of all PII types Godeapr® scans for. Which is, in line with the GDPR, categorized in three parts: 
- Personal data
- Special personal data
- Criminal convictions and offenses

For more information on each individual PII, please consult [this chapter](https://dev.azure.com/Datamo/Horizon/_wiki/wikis/Horizon.wiki/39/01.-Godeapr-user-manual?anchor=personal-identifiable-information).

Note: We **advise** not to scan for thousands of files at once while also scanning for all PII types. This might give overwhelming results and will not help in structurally and accurately identifying PII on unexpected locations. 

![afbeelding.png](/.attachments/afbeelding-180b042f-9158-4918-8467-5482b03899c1.png =700x)

Besides selecting for specific PII, in this view you can also choose to **anonymize** the results. In the reporting overview, the actual results will be partially masked. This is useful in case PII should be hidden from the user using Godeapr®.

![afbeelding.png](/.attachments/afbeelding-a6142db4-7e6f-4356-8fe3-e30c618886b5.png =700x)

Once you select **start scan**, you are prompted to give the scan a suitable name (which you can alter later in the  section [**Identify**](https://dev.azure.com/Datamo/Horizon/_wiki/wikis/Horizon.wiki/39/01.-Godeapr-user-manual?anchor=loading-a-previous-scans) section). If no name was given, Godeapr® will give the scan a default name.

## Reports
_This view is similar for scanning files or databases_.

When a scan is started, findings are generated interactively during the process and visualized in a first overview of total findings and deviating findings (see [Regular vs. Deviating](https://dev.azure.com/Datamo/Horizon/_wiki/wikis/Horizon.wiki/39/01.-Godeapr-user-manual?anchor=regular-vs.-deviating)). The progress-bar is based on the number of files or tables yet need to be scanned by Godeapr®. 

![afbeelding.png](/.attachments/afbeelding-fa6e851a-77c6-465f-b165-e4d9641c8bef.png =700x)

### General overview
Once the scanning process is finished, you are automatically redirected to the reporting overview which looks more or less as follows:

![Screenshot 2022-08-04 at 14.43.02.png](/.attachments/Screenshot%202022-08-04%20at%2014.43.02-80da40cd-5c58-4aac-b772-3ca9bb55d0c9.png =700x)

On the left side, there are 3 filtering possibilities:

1.  An checkbox to only visualize the 'deviating' results (see [Regular vs. Deviating](https://dev.azure.com/Datamo/Horizon/_wiki/wikis/Horizon.wiki/39/01.-Godeapr-user-manual?anchor=regular-vs.-deviating)).
2. A selection tree based on PII types. In the example screenshot, you see three PII types selected in the tree: Creditcard, Labor union, and Medical information. Based on this selection, the key-figures table (**5**) and overview graph (**6**) are updated respectively. 
3. A selection tree based on the scanned source. In the screenshot, you see that three tables of the scanned database are selected. So based on total filter selection 

Hint: use Ctrl (cmd on MacOs) + mouse click to (de)select multiple tree nodes. The dot (**•**) on a tree node indicate that not all children nodes are selected.

On the right of the filters, there is:

4. A tab selection to jump between three different views. A general overview with aggregated results, a tabular overview per data source, or a list overview with detailed information on the specific findings. All views will show the data corresponding to the filter selection.
5. A key-figure table indicating the following data based on the filter selection: 
    - Total scanned sources
    - Total scanned data cells
    - Total scanned columns
    - Total scanned rows
    - Total findings
    - Total deviating findings
6. A graph overview of the total amount of findings and deviating findings per PII type for the filter selection. When a PII type is not selected, the bar will be grayed-out. Hint: If you hover over the bar, a tool-tip will indicate the exact amount of findings and deviating findings for that specific PII type. 
7. An export functionality to export a list of findings according to your filter selection. More information can be found here: [Export](https://dev.azure.com/Datamo/Horizon/_wiki/wikis/Horizon.wiki/39/01.-Godeapr-user-manual?anchor=export).

### Tabular overview
_This view is only visible when scanning for structured data files or databases._

When selecting the table overview (**4**), you will see an overview of findings per scanned source in tabular format. In this view you will see the column names of the scanned sources in the first column and their mapped PII type based on the [Regular vs. Deviating](https://dev.azure.com/Datamo/Horizon/_wiki/wikis/Horizon.wiki/39/01.-Godeapr-user-manual?anchor=regular-vs.-deviating) methods applied in the second column. The superscript per predicted PII type indicates whether the prediction was based on column-mapping, column names, or column data. The remaining three columns indicate the amount of findings per selected PII type in the PII filter on the left side. In this way, the view tells you how much PII is found per column in tabular data and based on which method Godeapr® predicted the PII type.

![afbeelding.png](/.attachments/afbeelding-845e3e8b-e3ab-49f4-b5cf-b1a05254ac79.png =700x)

### Listed overview

For more details on the found PII, there is the listed overview. Here, all findings based on the PII type and sources selected in the filters on the left, are visualized in a list. This list provides information about the location of the found PII, the type of the PII and the actual found content. In the below screenshot, there are several PII types found in the same piece of data; BSN, IBAN, Political Party, Religion. In the 'found data' column is highlighted in purple what the specific PII type was that Godeapr® found. If there is nothing highlighted, it means that the text as a whole was the PII on which Godeapr® was triggered, like you see with the email 'van-den-veldeeline@hotmail.com'.

The red (**!**) indicated that the PII was found on a **deviating** location (_structured data only_). More information here: [Regular vs. Deviating](https://dev.azure.com/Datamo/Horizon/_wiki/wikis/Horizon.wiki/39/01.-Godeapr-user-manual?anchor=regular-vs.-deviating). For scans on unstructured data and files, this explanation mark will not be visible. 

![afbeelding.png](/.attachments/afbeelding-c84734c6-70ac-4af8-ad5e-8a3e71ebbc48.png =700x)

When you click one of the rows in the list, you see the source of the specific PII and the row where exactly the data is found. For unstructured scans, the row is an estimation as many unstructured documents like PDF files or images do not have a defined length nor rows. 

When indicated to make the results **anonymized** in the [preferences](https://dev.azure.com/Datamo/Horizon/_wiki/wikis/Horizon.wiki/39/01.-Godeapr-user-manual?anchor=preferences) section. All found data will be partially masked to hide the PII from the user as you can see below. 

![afbeelding.png](/.attachments/afbeelding-49742061-a4a3-4f37-a8de-8f79826798b1.png =700x)

## APIs
When you want to scan data coming from an API, the client needs to be installed in the back-end to be able to call the endpoint and extract data. Currently, there are no standard APIs included in the application. To add your own API, please contact info@deapr.com.

# Identify
Once scans are completed and you would like to analyze the results once more, you can do so in the **Identify** section. Here all previous scans are listed, including their given name, the mode and the run date of the scan, how many source objects Godeapr® scanned and how much PII was found in those objects. 

## Loading a previous scan
You can choose to delete a previous scan be selection the trash icon, or to analyze the results once more be either selecting the magnifying glass or simply selecting the row and then the **Analyze** button in the upper right corner. Analyzing an previous scan will load the scan and bring you to the [reporting overview](https://dev.azure.com/Datamo/Horizon/_wiki/wikis/Horizon.wiki/39/01.-Godeapr-user-manual?anchor=reports).

![afbeelding.png](/.attachments/afbeelding-c7fe7207-c899-4f0a-911b-b511b52f97fd.png =700x)

You can also change the name of the scan by simply selecting the name of the scan you would like to change.

## Comparing multiple scans
Besides loading a single scan, you can also compare multiple scans to see if any progress was made during an optional clean-up process within your organization. To compare multiple scans, simply select multiple scans in the list and the analyze button in the top right corner changes to **Compare**. Needless to say, it is wise to compare scans that make sense to compare. For example when the scan was executed to the same source objects with the same PII types included. 

Note: It is possible to include as many scans as necessary in the comparison, but all scans need to have at least one finding and should be of the same mode. Meaning you should compare database scans with database scans and unstructured file system scans with unstructured file system scans. 

![afbeelding.png](/.attachments/afbeelding-2740792d-224f-4cae-a7a5-cd3cc4a8b23f.png =700x)

When starting a comparison, all scans will be loaded and you will automatically be led to a comparison report like the one below. The scans are automatically ordered by their execution date throughout the report. The first table shows the amount of deviating results in case you are comparing either database scans or structured filesystem scans. The number of deviating findings is displayed in this table as well as the relative deviating findings based on the total number of findings for all scans for each group of PII types. The filters on the left are again available for quick and easy navigation through the scanned objects and PII types. 

![afbeelding.png](/.attachments/afbeelding-9c1f27a5-7a6a-4819-a84c-ffe8f79c35a9.png =700x)
![afbeelding.png](/.attachments/afbeelding-c25eb77a-2875-485d-a025-17edd8b7c2ba.png =700x)

The graph is only showing the relative deviating findings per group of PII types per scan. In this way you quickly see the progress when reducing and cleaning the number of unwanted deviating findings.

When comparing unstructured scans, only the last table and a corresponding graph as visualized. This last table shows the total number of findings and the relative number of findings based on the total. Godeapr® does not show deviating findings for unstructured scans, more information can be found here: [Regular vs. Deviating](https://dev.azure.com/Datamo/Horizon/_wiki/wikis/Horizon.wiki/39/01.-Godeapr-user-manual?anchor=regular-vs.-deviating).

# Comply

To quickly comply and start addressing potential issues, in the **Comply** section, you find a similar list of processes as in the **Identify** section. Instead of loading the process in the reporting overview or comparing the reports, here it is possible to export particular findings to support or facilitate addressing issues conveniently. 

## Export
When selecting the 'download' icon, you will be prompted with a couple of choice regarding the export:
- Whether or not to export only deviating results
- To anonymize the results in the export, which is on by default
- To export findings from specific PII types
- To export findings from specific sources

![afbeelding.png](/.attachments/afbeelding-76182b8e-858b-4b77-949d-3afac5286031.png)

The next step will be to select an export location on the machine where Godeapr® is installed. Hereafter, a ```.csv``` file will be generated including the:
- Name of the source
- Column index (_structured data only_)
- Row index (_estimation for unstructured data_)
- Location of the source (_file path or database / table name_)
- Whether the PII was found at a deviating location (_structured data only_)
- the PII type
- the original data (_non anonymized exports only_)
- the matched data (_non anonymized exports only_)


# Appendix
## Personal Identifiable Information 
### First name
### Last name
### Street name
### House number
### Postal Code
### City
### Country 
### Nationality
### BSN
### Credit-card
### IBAN
### Passport
### Drivers license
### Email
### License plate
### Phone number
### Gender
### Date of birth
### Civil status
### Education level
### Financial information
### Political party
### Political preference
### Religion
### Labor union
### Ethnicity
### Sexual preference 
### Medical information
### Medicines 
### Criminal convictions and offenses
