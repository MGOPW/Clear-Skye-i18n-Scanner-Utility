# Clear Skye i18n Scanner Utility

**Enhancement requests and issues at [Github](https://github.com/MGOPW/Clear-Skye-i18n-Scanner-Utility).**   
_Please check the Github for the latest updates. We will be only updating the store app for major releases._

The **Clear Skye i18n Scanner Utility** goes out and scans a series of user-defined script fields to look for any potentially untranslated strings that exist in those scripts. The two main record types are **Scans** and **Nodes**. **Scans** house the configuration for which tables you want to scan (Scanned tables), it lists off the identified strings (Scanned Nodes) and catches any errors (Scan Logs).

For each scanned table it will run a GlideRecord query on that table, grab the designated "Script Field" and parse that script field using a library called Acorn.js. Acorn.js parses the javascript into what is called an Abstract Syntax Tree (AST) in a process similar to how the ServiceNow execution engine would process it. It can discern between strings in commented out code and strings that we want to target. The string literals obtained then become Scanned Nodes, enabling you to go through the list and change each record's respective state according to your needs.

This helps your localization process by saving you all the hassle of manually going through your app's old scripts and needing to identify what needs to be translated. It also provides you with line numbers so you can easily go back and add in any missing getMessage required.

#### Credits: Travis Toulson at [Code Creative](https://codecreative.io/), [Acorn.JS](https://github.com/acornjs/acorn)

* * *

Quick start:
============

1.  Navigate to **Clear Skye I18N Scanner Utility** on the left navigation menu.
2.  Click **Scans**.
3.  Create a new **Scan** record
4.  Create new **Scanned Table** records as you see fit.
    1.  We recommend the following **Table** and **Script Field** combinations to start:  
        `sys_script_include - script`, `sp_widget - script`,`sp_widget - client_script`,`sys_script - script`,`sysauto_script - script`,`sys_script_client - script`,`catalog_script_client - script`
5.  Click the **Run Scan** UI Action.
6.  Wait.
7.  Check the **Scanned Nodes** for any resulting string literals that need review.
8.  Do the thing.
