---
title: Installing Client Components
source: pdf pp. 55-58, sec 5.2
summary: Prerequisites and the setup wizard procedure for installing all SAP Business One client components, silent-mode parameters, and next steps for Excel Report and Interactive Analysis.
---

# Installing Client Components

## Prerequisites

- The installation computer complies with all hardware and software requirements. For information on hardware and software requirements, search for relevant information on SAP Help Portal (https://help.sap.com/viewer/p/SAP_BUSINESS_ONE_PRODUCT_LINE).
- You have installed Microsoft .NET Framework 4.8.

  > **Note**
  >
  > If you do not have Microsoft .NET Framework 4.8 installed, it is installed during the SAP Business One installation process. However, you must restart your machine. To avoid a restart, you may choose to install the framework before starting the SAP Business One installation.

- You have installed Microsoft Visual C++ 2005 SP1 Redistributable Package. If it is not installed yet, you can install it during client installation.
- You have installed Microsoft Excel.
- If the machines on which the SAP Business One client and DI API run use an HTTP proxy for network access, you have added the System Landscape Directory server to the list of proxy exceptions.

## Context

You can install the following client components on every workstation:

- SAP Business One client application (together with SAP Business One client agent and DI API)
- Software development kit (SDK)
- Data transfer workbench
- Solution Packager
- SAP Business One studio

If you want to use the Microsoft Outlook integration features on a workstation without the SAP Business One client application, install the Microsoft Outlook integration component (standalone version). For more information, see [Installing the Microsoft Outlook Integration Component (Standalone Version)](outlook-integration-standalone.md) [page 58].

> **Note**
>
> SAP Business One client components can be installed also from the System Landscape Directory (SLD) control center. For more information, see [Performing Centralized Deployment](../centralized-deployment/registering-installation-cd.md) [page 163].

> **Note**
>
> If you want to install the SAP Business One client manually in silent mode, you can use the following command line parameters:
>
> ```text
> Setup.exe /S /Z"<Full Installation Path>*<System Landscape Directory
> Address>:<Port>
> ```
>
> For example: `setup.exe /S /z"c:\Program Files\SAP\SAP Business One Client\*127.0.0.1:30000"`

A setup wizard is used for installation as well as for upgrade. The following procedure describes how to install **all** client components in a clean environment where no SAP Business One components exist.

## Procedure

1. Navigate to the root folder of the product package and run the `setup.exe` file.
2. In the welcome window, select your setup language and choose *Next*.
3. In the *Setup Type* window, select *Perform Setup* and choose *Next*.
4. In the *Setup Configuration* window, select *New Configuration* and choose *Next*.
5. In the *System Landscape Directory* window, do the following:
   a. Select *Connect to Remote System Landscape Directory*.
   b. Specify the hostname or the IP address of the server where the SLD is installed.
   c. Choose *Next*.
6. In the *Certificate Verification Settings* window, enable or disable certificate verification.

   Figure: The Certificate Verification Settings window of the setup wizard.

   ![p057-01](../../assets/p057-01.png)

   If the root certificate of the romote SLD has **not** been imported to the trusted store on the machine where you are running the installation, the certificate verification cannot be enabled. For more information, see SAP Note 3520401 (https://me.sap.com/notes/3520401).

7. In the *Landscape Administrator Logon* window, enter the password for the site super user `B1SiteUser`.

   This landscape administrator was created during the installation of the SLD.

8. In the *Database Server Connection* window, enter the database server information as follows:
   a. Specify the database server type.
   b. In the *Server Name* field, enter the fully qualified domain hostname (FQDN) of the database server.
   c. Choose *Next*.
9. In the *Component Selections* window, select the required client components and choose *Next*.
10. In the *Review Settings* window, review the settings you have made and choose *Next*.
11. In the *Setup Summary* window, review the component list and then choose *Setup* to start the setup process.
12. In the *Setup in Process* window, wait for the setup to finish.

    In the course of the setup, some additional wizards are displayed to guide you through the setup of corresponding components.

13. Depending on the results of the setup, one of the following windows is displayed:
    - *Setup Result: Successful* window: The wizard opens this window if the setup of all components was successful. To continue, choose *Next*.
    - *Setup Result: Errors* window: The wizard opens this window if the setup of one or more components failed. To continue, choose *Next*, and then in the *Restoration* window, do either of the following:
      - Select the failed component and proceed to start the restoration process.
      - Choose *Next* to skip the restoration.
14. In the *Congratulations* window, choose *Finish* to close the wizard.

## Next Steps

### Next Steps for Excel Report and Interactive Analysis

To use Excel Report and Interactive Analysis, you must do the following after the installation:

- In Microsoft Excel, enable all macros and select to trust access to the VBA project object model. For instructions, see the Microsoft online help.
- If the user who installs Excel Report and Interactive Analysis (user A) is different from the user who uses Excel Report and Interactive Analysis (user B), user B must start Excel Report and Interactive Analysis from the Windows menu for the first time. After having done so, user B can start Excel Report and Interactive Analysis directly from within the SAP Business One client or from the Windows menu.

If you have installed Excel Report and Interactive Analysis to a folder that is not in the `%ProgramFiles%` directory (default installation folder), you must perform some additional steps before using the function.
