---
title: Performing Silent Upgrades
source: pdf pp. 82-83, sec 8.4
summary: Upgrading SAP Business One in silent mode with Setup.exe, which components it covers, and the password parameters you can pass with a Config.XML file.
---

# Performing Silent Upgrades

You can upgrade SAP Business One using a silent mode by calling `…\Setup.exe` from the upgrade package.

You can use the silent mode to upgrade the following components:

- Repository
- All packages of Server Tools, including:
  - System Landscape Directory
  - License Manager
  - Extension Manager
  - Data Interface Server
  - Job Service
  - Microsoft 365 Integration
  - Workflow
- Databases
- Integration Solution Components
- DI API
- SAP Business One Client
- Browser Access Service
- All Add-Ons

To upgrade SAP Business One, provide the following argument:

```text
setup.exe <Config.XML> <parameter> <value>
```

To obtain the required `Config.XML` file, first run the setup wizard in the interactive mode. After generating this file, you can make a copy and use a text editor to modify the values for future use as required.

You can find the configuration file in the `…\%LOCALAPPDATA%\SAP\SAP Business One\SetupWizard\Config` folder.

You can provide several different parameters, or multiple parameters, as shown in the following table.

<!-- table: t083-01 -->
<!-- table: t083-02 -->
<!-- table: t083-03 -->
<!-- table: t083-04 -->
<!-- table: t083-05 -->
<!-- table: t083-06 -->
<!-- table: t083-07 -->
| Type | Parameter | Value |
|---|---|---|
| Database Server and License Server authentication | `-DbPassword` | Database server password |
| Database Server and License Server authentication | `-SitePassword` | Landscape administrator password |
| SLD configuration | `-SLDCertPassword` | SLD certificate password |
| SLD configuration | `-SLDDomainPassword` | SLD domain user password |
| Integration Solution Components | `-B1iDBPassword` | Integration framework database server password |
| Integration Solution Components | `-B1iAdminPassword` | Integration framework Tomcat server administrator password |
| Integration Solution Components | `-B1iDIPassword` | Company password for DI calls |

> **Example**
>
> ```text
> Setup.exe "C:\my_config\Config.XML" -DbPassword x1Y3s -SitePassword pO3kAnk3
> ```
