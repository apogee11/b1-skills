---
title: Upgrade Process Overview
source: pdf pp. 70-72, sec 8.3*
summary: Prerequisites and the five high-level steps for upgrading SAP Business One (server components, databases and workstation clients).
---

# Upgrade Process Overview

**Prerequisites**

- You have downloaded the upgrade package from the SAP Support Portal.
- You have ensured that company databases are not connected to any SAP Business One clients, SQL Server clients, or other applications.
- You have the SAP Business One 10.0 license file available. You need this license file for connecting your company after the upgrade process is finished. If you do not import a valid license file after the upgrade process, you cannot work with your company.
- You have administrator rights on the computer that runs the SAP Business One setup wizard.
- If the machines on which the SAP Business One client and DI API run use an HTTP proxy for network access, you have added the System Landscape Directory server to the list of proxy exceptions.
- The `SBO-COMMON` database that you have installed on your computer is not a later release than the upgrade package.
- If any components of SAP Business One integration for SAP NetWeaver (B1iSN) were previously installed on your server, you have uninstalled them manually before installing any integration solutions delivered with SAP Business One. This step is required due to compatibility reasons. For more information about uninstalling components of B1iSN, see the *SAP Business One integration for SAP NetWeaver Installation and Upgrade Guide*.
- If you have installed the integration framework, you stopped the following services (in the order given below):
  1. SAP Business One integration Event Sender
  2. SAP Business One integration DI Proxy Monitor
  3. SAP Business One integration DI Proxy
  4. Integration Server Service

> **Note**
>
> After you have completed the upgrade process, check whether you must restart the services in reverse order.
>
> To upgrade only the integration framework, run the `setup.exe` file under `\Packages.x64\B1 Integration Component\Technology\` in the product package.

During the upgrade of SAP Business One, you have the option of installing remote support platform for SAP Business One. For more information about installing remote support platform for SAP Business One, see *Administrator's Guide to Remote Support Platform for SAP Business One*. You can find the guide (`RSP_AdministratorGuide.pdf`) under `…\Documentation\Remote Support Platform\System Setup\` on the SAP Business One product DVD, or on SAP Help Portal (https://help.sap.com/viewer/p/SAP_BUSINESS_ONE_PRODUCT_LINE).

**Procedure**

To upgrade SAP Business One, do the following:

1. To determine the upgrade path, read the Overview Note for the required version. For example, check which versions are supported for upgrade to the required higher version. If direct upgrade is not supported, you first need to upgrade your system to a supported version and perform the server upgrade operation for more than one time.
2. On your server, upgrade your operating system to the required version. For more information, see [Prerequisites](../introduction-and-prerequisites/prerequisites.md) [page 29].
3. On your server, upgrade Microsoft SQL Server to the required version. For more information, see [Prerequisites](../introduction-and-prerequisites/prerequisites.md) [page 29].

> **Recommendation**
>
> After upgrading the MSSQL Server, we recommend that you align the compatibility level of your company database with the default compatibility level designation of the SQL Server. For more information, see Database Compatibility Level (https://docs.microsoft.com/en-us/sql/t-sql/statements/alter-database-transact-sql-compatibility-level?view=sql-server-ver15).

4. On your server, run the setup wizard for the required version to upgrade the common database, company databases, and all server components.

> **Recommendation**
>
> Upgrade all the server components at one time, and not separately. Otherwise, you may have problems fixing certain errors in the pre-upgrade test.

> **Note**
>
> On your server machine, if you need to upgrade SAP Business One SLD Agent, you must upgrade it separately using the **Components Setup Wizard**. For more information, see [Manually Installing SLD Agent Service](../centralized-deployment/sld-agent-wizard-installation.md#manually-installing-sld-agent-service) [page 165].

5. On each workstation, do the following:
   - If you have installed such client components as the DTW, run the setup wizard to upgrade these client components. For more information, see [Upgrading SAP Business One Databases and Components](upgrading-databases-and-components.md) [page 72].
   - Upgrade the SAP Business One client application. For more information, see [Upgrading the SAP Business One Client](upgrading-client.md) [page 79].
   - Upgrade SAP Business One SLD Agent using the **Components Setup Wizard**. For more information, see [Manually Installing SLD Agent Service](../centralized-deployment/sld-agent-wizard-installation.md#manually-installing-sld-agent-service) [page 165].
