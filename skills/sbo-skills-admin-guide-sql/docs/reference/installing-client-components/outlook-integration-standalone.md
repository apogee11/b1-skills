---
title: Installing the Microsoft Outlook Integration Component (Standalone Version)
source: pdf pp. 58-60, sec 5.3
summary: Prerequisites, coexistence limits and the setup wizard procedure for installing the standalone 64-bit Microsoft Outlook integration component.
---

# Installing the Microsoft Outlook Integration Component (Standalone Version)

## Prerequisites

- You have installed the 64-bit SAP Business One DI API.
- You have installed the 64-bit Microsoft Outlook.
- You have assigned the following to the SAP Business One user account which is used for the connection:
  - The Microsoft Outlook integration add-on in the SAP Business One client
  - The SAP AddOns license
- You have started the Microsoft Outlook integration add-on in the company at least once. This ensures the necessary user-defined tables are added to the company database.

## Context

The Microsoft Outlook integration component enables you to exchange and share data between SAP Business One and Microsoft Outlook. This component is a standalone version that does not require the SAP Business One client to be installed on the same computer.

If you want to use the Outlook integration features on a computer on which you have installed the SAP Business One client, you can install either the Outlook integration add-on or the standalone version. For more information, see [Assigning SAP Business One Add-Ons](../client-configuration-and-add-ons/assigning-add-ons.md) [page 145].

> **Caution**
>
> The Microsoft Outlook integration component is a standalone version of the Outlook integration add-on, and they cannot coexist.
>
> If you install the add-on while you have the standalone version installed on the same computer, a subsequent upgrade of the standalone version will be prevented; if you install the standalone version while you have the add-on installed on the same computer, the installation fails.

> **Note**
>
> Only the 64-bit version of the Microsoft Outlook integration component is available.

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

   ![p060-01](../../assets/p060-01.png)

   If the root certificate of the romote SLD has **not** been imported to the trusted store on the machine where you are running the installation, the certificate verification cannot be enabled. For more information, see SAP Note 3520401 (https://me.sap.com/notes/3520401).

7. In the *Landscape Administrator Logon* window, enter the password for the landscape super user `B1SiteUser`.

   This landscape administrator was created during the installation of the SLD.

8. In the *Database Server Connection* window, enter the database server information as follows:
   a. Specify the database server type.
   b. In the *Server Name* field, enter the fully qualified domain hostname (FQDN) of the database server.
   c. Choose *Next*.
9. In the *Component Selections* window, select Outlook Integration Standalone and choose *Next*.
10. In the *Review Settings* window, review your settings and proceed as follows:
    - To continue, choose *Next*.
    - To change the settings, choose *Back*.
11. In the *Setup Summary* window, choose *Next*.
12. In the *Setup Status* window, wait for the system to perform the required actions.
13. In the *Complete* window, choose *Finish*.
