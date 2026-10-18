---
title: Database Connection Security for SAP Crystal Reports
source: pdf pp. 260-261, sec 12.11
summary: Setting up an encrypted (TLS/SSL) connection between SAP Crystal Reports, version for the SAP Business One Application, and Microsoft SQL Server, including the ODBC connection string.
---

# Database Connection Security for SAP Crystal Reports

**Context**

SAP Crystal Reports, version for the SAP Business One Application supports secure communication between the Microsoft SQL Server database and SAP Crystal Reports, version for the SAP Business One Application using Transport Layer Security (TLS)/Secure Sockets Layer (SSL) protocol.

To set up the encryption connection between the SAP Crystal Report, version for SAP Business One application and the Microsoft SQL Server database, perform the procedure below.

**Procedure**

1. Export a root certificate `.pfx` (for example, `caServer.pfx`) from Microsoft SQL Server and copy it to a temporary location on your client workstation. For more information about generating a root certificate, see the Microsoft documentation at www.msdn.microsoft.com (https://www.msdn.microsoft.com).
2. Run `mmc.exe` to open Microsoft Management Console on the workstation.
3. Import the `.pfx` file in the path: `Console Root\Certificates(Local Computer)\Trusted Root Certification Authorities\Certificates`.
4. Run SAP Crystal Reports, version for the SAP Business One application.

> **Note**
>
> If you set up an ODBC connection with SSL settings from SAP Crystal Reports for SAP Business One to the Microsoft SQL server, you should set connection strings as follows:
>
> 1. Log in to SAP Crystal Reports for SAP Business One.
> 2. On the start page, create a new report by clicking (create).
> 3. In the *Standard Report Creation Wizard* window, navigate to *Create New Connection* > *ODBC(RDO)*.
> 4. In the *ODBC (RDO)* window, add `Encrypt=yes` at the end of the existing string. For example,
>
>    ```text
>    "DRIVER={ODBC Driver 18 for SQL Server};Server=<hostname>;
>    Database=;UID=sa;PWD=*****;Encrypt=yes"
>    ```
