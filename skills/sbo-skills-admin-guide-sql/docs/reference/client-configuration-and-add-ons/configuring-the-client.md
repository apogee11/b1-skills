---
title: Configuring the SAP Business One Client
source: pdf pp. 144-145, sec 9.5
summary: Providing the System Landscape Directory address on first logon, starting the client from the Start menu or the command line, and checking the logger configuration.
---

# Configuring the SAP Business One Client

After you have installed SAP Business One and logged on to the application for the first time, you must provide the System Landscape Directory address and port number in the *System Landscape Directory Server Selection* window.

To start the SAP Business One client, choose *Start* > *All Programs* > *SAP Business One* > *SAP Business One Client*. To start the SAP Business One Client using the command line, enter the following command:

```text
"SAP Business One.exe" -DbServerType <Microsoft SQL Server version> -Server
<Microsoft SQL Server instance name> -CompanyDB <Company Database> -UserName <User
ID> -Password <Password> -SLDServiceAddress <SLD address:port>
```

For the `DbServerType` parameter, the value depends on the version of Microsoft SQL Server you are using. For Microsoft SQL Server 2017, enter `11`.

> **Note**
>
> Command line parameters are case-sensitive.

> **Caution**
>
> For security reasons, do not start the SAP Business One client using the command line in productive environments. You should use this method only for testing.

In the SAP Business One toolbar, you can check the log configurations by choosing *Help* > *Support Desk* > *Logger Setting*. You can see the relevant configuration log file under `…\SAP\SAP Business One\Conf\B1logconfig.xml`.
