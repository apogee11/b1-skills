---
title: Prerequisites
source: pdf pp. 29-31, sec 4
summary: Operating system, SQL Server, Office, ODBC driver, .NET Framework and browser requirements for SAP Business One, the 31-day license constraint, and OS user group privileges.
---

# Prerequisites

- For information on hardware requirements, see the *SAP Business One Hardware Requirements Guide* on SAP Help Portal (https://help.sap.com/viewer/p/SAP_BUSINESS_ONE_PRODUCT_LINE).
- For an overview of support platforms for SAP Business One and related products, see the *SAP Business One Platform Support Matrix* on SAP Help Portal (https://help.sap.com/viewer/p/SAP_BUSINESS_ONE_PRODUCT_LINE).
- For compatibility information regarding SAP Business One and SAP Business One Cloud, see SAP Note 1756002 (https://me.sap.com/notes/1756002).
- You have installed one of the following Microsoft operating system versions:
  - Windows 11
  - Windows Server 2016
  - Windows Server 2019
  - Windows Server 2022
  - Windows Server 2025

> **Note**
>
> SAP Business One Electronic Documents Service (EDS) and Electronic File Mapping Transformation Service (ETS) do not support Windows Server 2016. For more information about the limitation, see SAP Note 3644378 (https://me.sap.com/notes/3644378).

- You have installed Microsoft SQL Server 2016, 2017, 2019 or 2022.

> **Note**
>
> We recommend setting the language to **English** during the installation of Microsoft SQL Server.

- You have installed Microsoft Office 2016, 2019 or 2021.
- You have installed Microsoft ODBC Driver on the server as well as on the client workstations, as follows:
  - If you have installed SQL Server 2016 or 2017, make sure that the Microsoft ODBC driver version is 13.
  - If you have installed SQL Server 2019, make sure that the Microsoft ODBC driver version is 17.
  - If you have installed SQL Server 2022, make sure that the Microsoft ODBC driver version is 18.

  For more information about the driver version, see SQL Version Compatibility (https://docs.microsoft.com/en-us/sql/connect/odbc/windows/system-requirements-installation-and-driver-files?view=sql-server-ver15) and SAP Note 3532588 (https://me.sap.com/notes/3532588).

> **Note**
>
> Workstations that have Microsoft SQL Server installed have already had the SQL Server drivers installed automatically. However, you should manually install the SQL Server drivers on workstations that do not have Microsoft SQL Server installed.

- You have installed Microsoft .NET Framework 4.8 on the server as well as on the client workstations.

> **Note**
>
> As of 10.0 SP 2308, Microsoft .NET Framework 4.8 cannot be installed during the SAP Business One installation process. Please make sure that you install the framework before starting the SAP Business One installation.

- If you want to access the System Landscape Directory service, be sure to use one of the following Web browsers:
  - Microsoft Edge (the latest version)
  - Mozilla Firefox 9 or later
  - Google Chrome 12 or later
- If you want to access SAP Business One in a Web browser, be sure to use one of the following Web browsers:
  - Mozilla Firefox
  - Google Chrome
  - Microsoft Edge
  - Apple Safari (Mac and iPad)
- If you want to access SAP Business One, Web client, be sure to use one of the following Web browsers:
  - Mozilla Firefox
  - Google Chrome
  - Apple Safari (Mac and iPad)
- To display dashboards in the SAP Business One client application, ensure you have installed Adobe Flash Player for the embedded browser Google Chrome on each of your workstations. You can download Adobe Flash Player at https://www.adobe.com.

> **Note**
>
> The download link provided by Adobe is by default for Microsoft Internet Explorer. To download Adobe Flash Player for other browsers, choose to download for a different computer, and then select the correct operating system and a Flash Player version for other browsers.

- You have ensured that the names of the machines on which you want to install SAP Business One do not contain one or more non-standard characters (standard characters are letters, digits, and hyphens). Using non-standard characters in the name of a machine prevents it from being found on networks and causes the installation of SAP Business One to fail.

## Constraints

You can run the SAP Business One for 31 days without a license. To continue working with the application after 31 days, you must install a valid license key assigned by SAP.

> **Note**
>
> If you are a partner, for more information about installing the license key, see *SAP Business One License Guide* on SAP Partner Edge (https://partneredge.sap.com/en/products/business-one/about.html).

The demonstration databases provided are not for productive use. The application supports 40 localizations in the demonstration databases.

## User Privileges

The following table summarizes the requirements and recommendations for the group setup of the displayed operating system:

<!-- table: t031-01 -->
| Operation | Operating System | User Group (Recommended) | User Group (Minimum) |
|---|---|---|---|
| Client installation | Microsoft® Windows operating systems | Administrator | Administrator |
| Client upgrade | Microsoft® Windows operating systems | Administrator | Administrator |
| Runtime | Microsoft® Windows operating systems | Users | Users |

> **Note**
>
> For more information about possible installer issues related to the user account control (UAC) in Microsoft Windows operating systems, see SAP Note 1492196 (https://me.sap.com/notes/1492196).
