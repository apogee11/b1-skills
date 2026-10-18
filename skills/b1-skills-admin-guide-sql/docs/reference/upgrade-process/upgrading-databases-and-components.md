---
title: Upgrading SAP Business One Databases and Components
source: pdf pp. 72-79, sec 8.3.1
summary: Step-by-step setup wizard procedure for upgrading the common database, company databases, server and client components, plus restoring after a failed upgrade and troubleshooting.
---

# Upgrading SAP Business One Databases and Components

- [Prerequisites and context](#prerequisites-and-context)
- [Procedure](#procedure)
- [Next Steps](#next-steps)
- [Restoring Components and Databases](#restoring-components-and-databases)
- [Troubleshooting Upgrades](#troubleshooting-upgrades)

## Prerequisites and context

**Prerequisites**

- You have ensured that all SAP Business One clients are closed.

> **Recommendation**
>
> - Complete or terminate all workflow instances before closing SAP Business One client.
> - Lock the company whose database you will upgrade from the SLD control center. For more information, see [Upgrading Databases](../centralized-deployment/deploying-and-upgrading-databases.md#upgrading-databases) [page 176].

**Context**

A setup wizard is used for installation as well as for upgrade. The following procedure describes how to upgrade the common database, the company databases, server components, and client components. If any of the upgrade steps fail, you can use the restoration mechanism to reverse all changes made by the wizard.

> **Note**
>
> For security reasons, we recommend that you run the SAP Business One setup wizard to upgrade your company databases (schemas) on a backend server which is well protected.

Note that **the setup wizard does not support remote upgrade and can upgrade only local components**. To upgrade components on other machines, you must run the setup wizard repetitively.

In addition, for upgrade of the SAP Business One client within a release family, you can perform silent upgrade instead of using the setup wizard. For more information, see [Upgrading the SAP Business One Client](upgrading-client.md) [page 79].

If you intend to install the browser access service during the upgrade process, first read the instructions in [Installing the Browser Access Service](../installing-server-components/browser-access-service.md) [page 40].

> **Recommendation**
>
> Before initiating company database upgrades, we recommend that you use the change logs cleanup utility to delete the change log entries and master data that are no longer needed. This may help free up the space within your company database and reduce the upgrading time. For more information about change logs cleanup, see the online help of SAP Business One.

## Procedure

**Procedure**

1. Navigate to the root folder of the upgrade package and run the `setup.exe` file.
2. In the welcome window, select your setup language, and choose *Next*.
3. In the *Setup Type* window, select the *Perform Setup* checkbox, and choose *Next*.

   The option *Test the existing SAP Business One installation environment* verifies if the existing SAP Business One installation environment and the company databases are ready for an upgrade. The existing installation and data are not changed. For each company database that passes the test, you can generate a passcode, which allows you to bypass the pre-upgrade test when upgrading the database later. The passcode is in the form of an XML file that contains details on the tested company databases. It is valid for three days, and any changes to the company configuration render the passcode invalid.

   The *Perform Setup* option both performs the pre-upgrade tests and upgrades selected components and databases. If you carried out a pre-upgrade test for a company database earlier, you can enter the passcode to bypass the pre-upgrade tests for this company database.

4. In the *Setup Configuration* window, select one of the following options and choose *Next*:
   - *New Configuration* – Select this radio button to manually enter all the required settings. Go directly to step 6.
   - *Use Settings from the Last Wizard Run* – Select this radio button to use the settings from the last wizard run, which are stored in the configuration file generated during that run.
   - *Load Settings from File* – Select this radio button to use the settings stored in a configuration file generated during a previous wizard run, and then specify the location of the file you want to use. To obtain the required `Config.XML` file, first run the setup wizard and select the *New Configuration* option. After generating this file, you can make a copy and use a text editor to modify the values for future use as required.
5. If you selected to use the settings from the previous wizard run or a file, the *Review Settings* window appears.

   This window provides an overview of the settings that you have configured for the upgrade process. To modify any of the settings, edit the values in the table. Otherwise, choose *Next* to proceed with the upgrade.

> **Note**
>
> If you are sure that all the settings are correct, you can select the checkbox *Skip Remaining Steps and Automatically Start Pre-Upgrade Test and Upgrade* to bypass the remaining wizard steps and begin the process immediately.

6. In the *System Landscape Directory* window, do either of the following:
   - If you are upgrading the System Landscape Directory and other components that are installed on the same machine, select *Connect to Local System Landscape Directory* and choose *Next*. Note that the local System Landscape Directory will be upgraded forcibly if it is not already upgraded to the required version.
   - If you are upgrading components that are installed on a different machine from that of the System Landscape Directory, select *Connect to Remote System Landscape Directory*, specify the server, and then choose *Next*. Note that the remote System Landscape Directory must have already been upgraded to the required version.
7. In the *Landscape Administrator Logon* window, enter the password for the landscape super user `B1SiteUser`.

> **Note**
>
> If you chose to perform only the pre-upgrade test, you also have the option to connect to a database server. In this case, you need to specify the information for a database user instead of the landscape administrator.

8. In the *Database Server Connection* window, specify the Microsoft SQL Server version and select the database server instance. Then choose *Next* to proceed.

   If you do not find the database server you want to upgrade in the server list, you can register it in the System Landscape Directory. To do so, choose *Register New Database Server*, specify the relevant information, and then choose *Back* to continue with the upgrade.

> **Note**
>
> If you intend to upgrade the components from a lower version to SAP Business One 10.0 and upgrade the database server from a lower version to Microsoft SQL Server 2017 simultaneously, we recommend that you perform the following steps:
>
> 1. Upgrade the Microsoft SQL Server from the lower version to Microsoft SQL Server 2017.
> 2. Upgrade the SAP Business One Server Tools by running the `setup.exe` file in the path `…\Packages.x64\ComponentsWizard\seup.exe` from the upgrade package.
> 3. Upgrade SAP Business One Components from the lower version to SAP Business One 10.0 by the setup Wizard.

9. In the *Unsupported 32-bit Components* window, you can see the 32-bit components installed previously. We recommend that you manually uninstall these components. For more information about uninstalling SAP Business One, see [Uninstalling SAP Business One](../crystal-reports-and-uninstalling/uninstalling-sap-business-one.md) [page 66].

> **Note**
>
> Add-ons cannot be uninstalled from the SAP Business One Server by the setup wizard.

10. In the *Component Selections* window, select the corresponding checkboxes of the components that you want to upgrade.

    If a component has already been upgraded to the current version, its checkbox is enabled but not selected. If you select an already upgraded component, the wizard overwrites all instances of installed components.

    The wizard also lists all third-party add-ons present in the `\Packages.x64\Add-Ons Autoreg` folders, which you can select to upgrade.

> **Note**
>
> Upgrading the repository is a prerequisite for upgrading other components or company databases. If there are no installed versions of the `SBO-COMMON`, *Upgrade Database is not allowed*.
>
> If a component is indicated as *Not Found*, you can select the corresponding checkbox to install the component.

11. In the *Behavior Change for the Shared Folder* window, choose *OK*.

    When you upgrade SAP Business One from 10.0 FP 2208 or a lower version to FP 2305 or higher, the shared folder (`B1_SHR`) access permissions are further restricted as part of a security best practice. This may have an impact on your operations (for example, exporting data to Microsoft Excel) depending on your SAP Business One configuration.

    Please read SAP Note 3347947 (https://me.sap.com/notes/3347947), which describes permission and security changes for share folder, and evaluate any required follow-up actions based on your use of share folder.

12. In the *Port for Server Tools* window, specify a port number that is used by the server tools and choose *Next*. The default port number is `40000`.
13. In the *Port for License Service* window, specify a port number that is used by the license service and choose *Next*. The default port number is `40002`.
14. If you choose to upgrade Job Service, the *Port for Job Service* window appears. In this window, specify a port number that is used by the job service and choose *Next*. The default port number is `40004`.
15. If you choose to upgrade Service Layer or Mobile Service, the *Port for Service Layer Controller and Mobile Service* window appears. In this window, specify a port number that is used by the service layer controller and mobile service and choose *Next*. The default port number is `40005`.
16. If you choose to upgrade Microsoft 365 Integration, the *Port for Microsoft 365 Integration* window appears. In this window, specify a port number that is used by the Microsoft 365 integration and choose *Next*. The default port number is `40006`.

> **Note**
>
> If you are upgrading Microsoft 365 Integration from an earlier version to 10.0 FP 2602 or higher, please update the redirect URI in the Azure portal. For more information, see SAP Note 3649038 (https://me.sap.com/notes/3649038).
>
> If you are installing Microsoft 365 Integration for the very first time, after completing the installation, please refer to How to Work with SAP Business One Microsoft 365 Integration. (https://help.sap.com/docs/SAP_BUSINESS_ONE/ac897fe631794b7db54650bb36926b76/1539b340ad5b42008782e353db7ec07d.html)

17. In the *Database Selection* window, select the checkboxes of the databases that you want to upgrade.
18. To view additional options and information, select the row of a company database, select the *Advanced Settings* checkbox, and then specify the following:

    - *Backup* – From the drop-down lists in the *Backup* column, select whether to back up each database before the upgrade.

      > **Caution**
      >
      > If you select not to back up a database before upgrade, you cannot restore the database should the upgrade fail. SAP does not provide support for such databases in the case of an upgrade failure; a backup of the pre-upgrade database is required to qualify for SAP support.

    - *Upgrade By* – From the drop-down list, select the SAP Business One superuser that you want to use to perform the upgrade. By default, the wizard uses the `manager` account.
    - *Stop on Test Error* – Select this checkbox to force the wizard to stop the entire upgrade process if it encounters an error during a pre-upgrade test.
    - *Stop on Upgrade Error* – Select this checkbox to force the wizard to stop the entire upgrade process if it encounters an error while upgrading the database.

19. If errors occur which are preventing you from upgrading the company databases, do the following:

    1. In the *Status* column, click the *Not Ready* link. Details about the errors are displayed.
    2. Do either of the following:
       - Fix the errors and choose *Refresh*. Such errors are as follows:
         - The wizard finds more than one connection to the company database.
         - The database user registered with the server is either locked or is not a database admin user.
       - If the errors cannot be fixed and you must contact SAP Support, deselect the checkbox. Such errors are as follows:
         - The wizard does not support the company database version.
         - The wizard cannot find the localization for the company database from the locale list in the common database.

20. When all the selected databases have the status *Ready*, choose *Next*.

> **Note**
>
> - If any of the selected databases has the status *Not Ready*, the wizard disables the *Next* button. You cannot proceed to the next step until you have fixed the problem.
> - The database statistics on Microsoft SQL Server will not be updated after the company database upgrade.

21. In the *Upgrade - Backup Settings* window, specify the location where you want to store the backup files created before upgrading the selected components.

    - To use the default backup path configured in SQL Server, choose *Use the Default SQL Server Backup Location*.
    - To use another location on the database server, choose *Browse directories on database server* and click *Browse* to choose a directory.
    - To use a network drive, choose *Enter a network path* and specify the path.

    After you specify a location for the backup, the wizard displays the amount of space required for database backups and the available space on the corresponding drives.

> **Note**
>
> The backup procedure automatically includes the `B1AS` and `SLDDATA` databases as part of the upgrade process.

22. If you previously selected the integration framework for upgrade, do the following:

    1. In the *Integration Solution - B1i Database Connection Settings* window, enter the database password.
    2. In the subsequent *Integration Solution - Scenario Packages* windows, if you want to activate any new scenarios, select the corresponding checkboxes, and specify the necessary information.

23. In the *Review Settings* window, review your configuration setting. To modify any of the settings, choose *Back* to return to the relevant window; otherwise, choose *Next*.
24. In the *Pre-Upgrade Test* window, do the following:

    - To bypass the tests for a database, choose *Enter Passcodes* and upload one or more of the passcode files you saved earlier. After uploading the files, choose *Next* and proceed to step 23.

      > **Note**
      >
      > A passcode file is only valid for three days. Any changes to the company configuration render the passcode file invalid.

    - To perform pre-upgrade tests on each database to ensure its readiness for the upgrade and to reduce the possibility of upgrade failure, choose *Start*.

      > **Note**
      >
      > For the latest information about pre-upgrade tests, see SAP Note 1357462 (https://me.sap.com/notes/1357462).

25. In the *Pre-Upgrade Testing In Progress* window, the wizard first checks the common database and then checks the company databases one by one.

> **Note**
>
> If the common database does not pass the checks, the wizard does not continue with the rest of the checks.

26. The *Pre-Upgrade Test* window provides a detailed overview of the results of the pre-upgrade tests. You can view information about individual checks, possible solutions to errors, and recommendations for dealing with warnings by clicking the links to the corresponding notes in the *SAP Note* column.

    Depending on the results of the pre-upgrade tests, one of the following windows appears:

    - *Pre-Upgrade Test: Passed* – All components and databases successfully passed the pre-upgrade tests. Proceed to the next step.
    - *Pre-Upgrade Test: Errors Detected* – One or more components or databases contain errors. You cannot continue upgrading. You must fix the reported errors or contact SAP for support, and then start the setup wizard again.
    - *Pre-Upgrade Test: Warnings Detected* – One or more components or databases contain warnings. It is strongly recommended that you first fix the issues, and then continue the upgrade:
      1. For each component or database that contains warnings, click the corresponding link in the *Details* column.
      2. The *Pre-Upgrade Test Result* window appears.
      3. In the *Pre-Upgrade Test Result* window, click the corresponding hyperlink in the *SAP Note* column and follow the recommendations. After fixing the issue, select the checkbox in the *Confirmation* column.
      4. After confirming all the warnings, choose *Back* to return to the *Pre-Upgrade Test* window.
      5. After you have confirmed all warnings for all components and databases, choose *Next* to open the *Pre-Upgrade Test: Warnings Confirmed* window, and then proceed to the next step.
27. The *Setup Summary* window displays an overview of the components and databases that you have selected to upgrade (or install if some selected components are not installed). Do either of the following:
    - To begin the upgrade process, choose *Upgrade*.
    - To change the settings, choose *Back* to return to the previous steps.

    The *Upgrade in Process* window displays the upgrade progress of each component and database.
28. According to the upgrade results, one of the following windows appears:

    - *Upgrade Result: Upgraded* window: This window appears if the upgrade of all components and databases was successful. To continue, choose *Next*. To view the details of the components that are upgraded, select *Details* in its row. In the *Setup Results - Details* window, you can view the status of database backup for `SLDModel.SLDDATA` and `B1AS`.
    - *Upgrade Result: Errors* window: This window appears if the upgrade of any component or database fails. To continue restoring the failed components and databases, choose *Next* and then proceed to the [Restoring Components and Databases](upgrading-databases-and-components.md#restoring-components-and-databases) [page 78] section.
29. To enable you to upgrade all software components to the same version on all servers, in the *Upgrade Notification* window, the setup wizard displays a list of components that need to be upgraded.
30. In the *Congratulations* window, choose *Finish* to close the wizard.

    To view a summary report of the various upgrade steps, choose the *Setup Summary*, *Setup Log*, or *Setup Folder with Log Files* links.

## Next Steps

**Next Steps**

1. Import the license file for the new release.
2. On each client workstation, upgrade the SAP Business One client.

## Restoring Components and Databases

**Context**

If the upgrade process fails, the SAP Business One setup wizard restores the databases and certain components. The other components must be restored manually.

> **Note**
>
> The procedure below continues from the penultimate step of upgrading databases and components. It is relevant for situations only where the upgrade has failed.

To restore components and databases, do the following:

**Procedure**

1. In the *Restoration* window, select the checkboxes of the components and databases that you want to restore, and choose *Restore*.
2. Depending on the results of the restoration process, one of the following windows appears:
   - If the restoration is successful, the *Restoration Result: Restored* window appears. To complete the restoration, do the following:
     1. In the *Restoration Result: Restored* window, choose *Next*.
     2. In the *Congratulations* window, choose *Finish* to complete the restoration process.
   - If the restoration fails, the *Restoration Result: Failed* window appears. To complete the restoration, do the following:
     1. In the *Restoration Result: Failed* window, choose *Next*.
     2. In the displayed window, choose *Finish* to exit.

> **Note**
>
> If the restoration fails, to roll back SAP Business One to the version before the upgrade, you must do a manual restoration.

## Troubleshooting Upgrades

- The root user that runs the setup wizard has read, write, and execute permissions to the shared folder `B1_SHR` on the SAP Business One server computer.
- If you cannot connect to the System Landscape Directory using the server name, use the IP address of the server computer.
- To have SBO Mailer’s signature copied after upgrade, do the following:
  1. To open the SAP Business One *Service Manager* window, in Windows, choose *Start* > *All Programs* > *SAP Business One* > *Server Tools* > *Service Manager*.
  2. In the *SAP Business One Manager* window, from the *Service* dropdown list, select *SBO Mailer*, and then choose *Connection*.
  3. In the *Connection Settings* window, specify values in the *DB Type* and *DB Server* fields, and then choose *OK*.
  4. Log off SAP Business One and log on to SAP Business One again. You will find that the signature was copied.
