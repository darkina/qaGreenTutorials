---
# Daria many validations v2
<!-- description --> Tutorial description. Lorem ipsum
tags: [tutorial>advanced, topic>abap-extensibility]
primary_tag: products>sap-btp--cloud-foundry-environment
time: 10 min
parser: v2
---
## You will learn
  - How to do something
  - Why this technology is helpful
 
## Prerequisites  

 - **Proficiency:** Beginner 
 - **Web IDE** If you don't have the Web IDE open, follow these steps: [Enable and open the HANA Cloud Platform Web IDE](https://go.sap.com/developer/tutorials/sapui5-webide-open-webide.html)
 - **Tutorials:** This tutorial is part of a series.  The previous tutorial is [Set up the Northwind Destination](https://go.sap.com/developer/tutorials/hcp-create-destination.html)

## Next Steps
- This is a nex steps section
- **Tutorials** [Creating Database Backups](https://www.sap.com/)
  
## Intro
This is an Intro part

---

### Exact match rule

Video in iframe:

<iframe width="560" height="315" src="https://www.youtube.com/embed/IRnt2_dDxzI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Regex

***Tables:***

First Header | Second Header
------------ | -------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column


and

| Left-Aligned  | Center Aligned  | Right Aligned |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |
| zebra stripes | are neat        |    $1 |


### http-status-check

***Headers***

**Example:** 

## This is an h2 header
### This is an h3 header
###### This is an h6 header


### Regex begins with

***Lists***

**Example:** 
  
Sometimes you want numbered lists:

1. One
2. Two 
3. Three

Sometimes you want bullet points:

* Start a line with a star
* Profit!

You can create nested lists: 

* item1
    * one_one
    * two

### Regex with id Exact Match

***Blockquotes***

**Example:** 

In the words of Abraham Lincoln:
> Pardon my French

### Regex-substring

***There are three different types of messages: Note, Caution and Warning.***

>### Warning
>jhkjhkjhkjhkj
>>### Warning
>>>### Warning
>>>>### Warning
>>>>This is a Warning. 

&nbsp;

>### Caution
>iikjhiojhioji
>>### Caution
>>This is a Caution. 

&nbsp;

>### Note

>This is a note. 


### Single choice

**Task Lists*** (Please note, this requires empty line before task list):

**Example:**

- [x] @mentions, #refs, [links](), **formatting**, and ~~tags~~ supported
- [x] list syntax required (any unordered or ordered list supported)
- [x] this is a complete item
- [ ] this is an incomplete item

### Multiple choice

***Code blocks:***
```markup
 quit;
 !@#$%^&*&*(*(()_++|"}?><>??*&^%#!~~~~@33123-090=|"]?>{}|\\
  require 'redcarpet'
  markdown = Redcarpet.new("Hello World!")
  puts markdown.to_html
  exit;
```

```js
 quit;
 !@#$%^&*&*(*(()_++|"}?><>??*&^%#!~~~~@33123-090=|"]?>{}|\\
  require 'redcarpet'
  markdown = Redcarpet.new("Hello World!")
  puts markdown.to_html
  exit;
```

### Regex rule

> **For this step, select your preferred connection method by clicking on the options under the step title.**
>
> !![Options Screenshot](TabOptions-Screenshot.png)

[OPTION BEGIN [Tab One]]
After confirming the status, click on the three dots again and select the option to **Open SQL Console** in the SAP HANA Database Explorer.
>You can also navigate to the same destination by selecting the option to open SAP HANA Database Explorer.

1.	Look for the name of your standalone data lake from the database menu located on the left side in the database explorer.

2.	Click on the ![SQL](DBX_SQL icon.png) **icon** in the top-left corner to open a new SQL Console.

3.	You can confirm the connection to your standalone data lake from the connection status provided on the menu in the SQL Console.

[OPTION END]
[OPTION BEGIN [Option Two]]
>Connecting to a data lake instance with Interactive SQL is another option besides using the SAP HANA Database Explorer. If you want to connect using Interactive SQL (dbisql), you need to have it installed on your local system. You can download the Interactive SQL using the link provided in the [technical documentation](https://help.sap.com/viewer/a895964984f210158925ce02750eb580/LATEST/en-US/2fdb23a4fb364e06ace0eea0c9a4afec.html).

There are two ways to connecting to an instance through an Interactive SQL- from the graphical user interface or from the command line.

These are the steps towards connecting to your instance through the graphical user interface of Interactive SQL:

1.	Launch the SAP Interactive SQL in your system. The Connect dialog box should appear as shown below.

     !![Open dbisql](ss-01-open-dbisql.png)

2.	Select **Change database type** and choose **SAP HANA Cloud Data Lake**.

     !![Change Database type](ss-02-change-database-type.png)

3.	After selecting the database type, ensure that the encryption parameters placed under the security tab have been pre-filled, as shown below.

    !![Check security](ss-03-check-security.png)

[OPTION END]
[OPTION BEGIN [Option Three]]

If you would like to connect to your data lake instance through an Interactive SQL from the command line, please follow the instructions given below.

1.	Connecting to a data lake instance through an Interactive SQL from the command line requires a Connection String. To extract the connection string, ensure all fields on the Identification tab are filled in. Select **Tools**, then choose **Copy Connection String to Clipboard**.

    !![Copy Connection string](ss-08-copy-connection-string.png)

2.	After pasting the connection string in a notepad file, you can the distinguish the parts as seen below.
>**The password field must be filled using the password for your data lake instance before using this string to connect from the command line.** The connecting string consists of the port number at the end of Landscape information and is followed by the encryption parameters.

    !![Connection string](ss-09-connection-string.png)


3.	Now, open a Command Prompt window in your system. To begin an Interactive SQL session, execute the following command given below.
```
dbisql -c <CONNECTION_STRING>
```

    **For example**, paste the connection string as shown below.
```
dbisql -c "UID=HDLADMIN;PWD=SamplePassword;host=a111111a-1a11-11aa-a11a-1a1a11a1a111.iq.hdl.test.hanacloud.ondemand.com:443;ENC=TLS(tls_type=rsa;direct=yes)"
```

    !![Command Prompt](ss-10-command-prompt.png)

[OPTION END]
[OPTION BEGIN [Opyion Four]]

>**Attention**: The following instructions apply to you if you're using isql from the on-premise SAP IQ 16.1 version. Using any other open-source isql versions may lead to errors. Therefore, it's highly recommended to use the same version to avoid any errors.


Set up an open client connection to your database. Open a `linux` instance  and use the superuser account. For this example, your `$SYBASE` environment variable points to `/opt/sap` as your root folder.

To use isql, you need to have an **interfaces file**, which you can create in the vim editor. Follow these steps to create the interfaces file:

1.	Navigate to the root folder using command:  `/opt/sap/OCS-16_0/bin`

    !![Root folder](ss-13-root-folder.png)

2.	Enter the vim editor as the superuser account

    a.	`sudo vim interfaces`

    b.	`enter password`

    !![Connected to Root folder](ss-14-connected-root-folder.png)

12. If you encounter the following error while trying to start an isql session:

    !![Troubleshoot](ss-19-troubleshoot.png)

    Run the following command before trying again:

    ```
    unset LANG
    ```

    >**Attention**: This error was observed while using Ubuntu on a virtual Linux machine. This error will not occur when supported programs are used.


[OPTION END]

>In this tutorial, you have learned how to access your standalone data lake in SAP HANA Cloud. In the next tutorial, you will see how to load data into your standalone data lake.

