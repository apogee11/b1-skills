---
title: Upgrade Methods and Supported Releases
source: pdf pp. 69-70, sec 8*, 8.1, 8.2
summary: What an SAP Business One upgrade requires, the three upgrade methods, and where to find the supported upgrade paths and releases.
---

# Upgrade Methods and Supported Releases

To upgrade your SAP Business One application to a new minor or major release and run it successfully, you must do the following:

1. Upgrade your SAP Business One successfully.
2. Import the license file for the new release.

> **Note**
>
> If your SAP Business One is of a hotfix version, we strongly recommend that you upgrade to the next regular patch once it is available, as hotfixes are intended only as temporary solutions.
>
> To upgrade to a new minor or major release, you must upgrade to a regular patch first, and then you can proceed with the upgrade to the new release.

> **Note**
>
> If you upgrade SAP Business One from version 10.0 FP 2405 to version 10.0 SP 2511 or SP 2511 (Security) Hotfix 01, close the Windows *Services* app before you start the upgrade. For more information, see SAP Note 3694535 (https://me.sap.com/notes/3694535).

> **Note**
>
> When your SAP Business One has not been upgraded for over a year, a reminder message will pop up prompting you to upgrade to the latest release when you access the *Security* tab in the System Landscape Directory (SLD) control center.

## Upgrade Methods

You can use either of the following upgrade methods to upgrade a previous SAP Business One version:

- Using the SAP Business One setup wizard in the upgrade package
  You can use the setup wizard to guide you through the process of upgrading SAP Business One to a higher major release, a higher minor release, a support package, or a new patch level.
  If any of the upgrade steps fail, you can use the restoration mechanism to reverse all the database changes made to your SAP Business One landscape by the wizard and return to the SAP Business One version before the upgrade.

> **Caution**
>
> To detect any errors or warnings that may arise in the SAP Business One upgrade process, it is mandatory that you perform a trial run. The results of the pre-upgrade tests indicate where you may need to correct any errors before performing the actual upgrade. If no issues are found, you may continue with the upgrade procedure.

- Silent upgrade
  You can upgrade SAP Business One in a silent mode using command line arguments.
- Directly from the upgrade package folders
  You can use the upgrade files in the upgrade package to upgrade the individual SAP Business One components, although this method is not recommended and only for advanced users.

## Supported Releases

For information about the upgrade path and supported releases, see the overview note for the respective SAP Business One version. You can find the overview note in the *References* section in SAP Note 2826255 (https://me.sap.com/notes/2826255) (*Central Note for SAP Business One 10.0*).

For information about the upgrade strategy, see SAP Business One Upgrade Strategy Overview (https://help.sap.com/doc/sap-business-one-upgrade-strategy-overview/10.0/en-US/B1_Upgrade_Strategy.pdf).
