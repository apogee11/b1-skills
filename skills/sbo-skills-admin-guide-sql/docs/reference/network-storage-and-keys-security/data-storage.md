---
title: Data Storage Security
source: pdf pp. 225-226, sec 12.5*, 12.5.1
summary: Responsibility for data storage security and which databases and folders hold SLD, company, system, shared and integration framework data.
---

# Data Storage Security

The security of the data saved in SAP Business One is generally the responsibility of the database provider and your database administrator. As with your application infrastructure, most of the measures that you should take depend on your strategy and priorities.

There are a few general measures, as well as database-specific measures, that you can take to increase the protection of your data. Details are provided in the following sections:

- Exporting the Configuration File
- Importing the Configuration File
- Configuration Logs and User Settings

## Data Storage

In SAP Business One, according to the different types and purposes, the data is stored in different databases, as follows:

- SLD Database
  The SLD database stores the SLD data and contains the persistent landscape information and security settings. The SLD database must be protected with the highest priority.
- Company Database
  Company database stores business or transactional data.
- System Database (`SBOCOMMON`)
  System database holds system data, version information, upgrade information, and shared data of each company.
- Shared Folder (`B1_SHR`)
  Shared folder contains central configuration data as well as installation files for various client components. It also stores the files used in business, for example, attachments, templates.
- Database for SAP Business One integration framework
  The default database name is `IFSERV`. You can define a new name when installing the integration framework.
