---
title: Assigning SAP Business One Add-Ons
source: pdf pp. 145-146, sec 9.6
summary: What SAP Business One add-ons are, the 64-bit add-ons provided, their general prerequisites, and per-add-on prerequisites.
---

# Assigning SAP Business One Add-Ons

Add-ons are additional components or extensions for SAP Business One. Installing the server and client applications automatically registers the SAP add-ons and makes them available for installation from the SAP Business One application. For more information about assigning SAP add-ons to your companies, see the *Assigning Add-Ons* section in the online help document.

The add-ons run under the SAP Add-Ons license, which is included in the Professional User license.

SAP Business One provides the 64-bit add-ons as follows:

- Electronic File Manager
- Microsoft Outlook Integration
- Payment Engine

> **Note**
>
> The ELSTER Electronic Tax Return add-on is available for download in the SAP Business One Software Download Center and is no longer included in the SAP Business One download package. For more information, see SAP Note 2064562 (https://me.sap.com/notes/2064562).

**Prerequisites**

- You have a Professional license from SAP.
- You have installed Microsoft XML 3.0 Service Pack 4 on your workstation. To ensure that this software is installed on the hard drive of the workstation, check that the `msxml3.dll` file is saved in the system32 directory in the main Windows directory.
- If you chose Custom for the installation of server components, ensure that SAP Add-ons is selected in the *Select Features* window.
- You must have Power User or Administrator rights, especially in the terminal server environment.

The following table displays the SAP Business One add-ons and their prerequisites.

<!-- table: t145-01 -->
<!-- table: t146-01 -->
<!-- table: t146-02 -->
<!-- table: t146-03 -->
- Payment Engine
  - **Prerequisites**: Inbound Functionality is activated only when the *Bank Statement Processing* checkbox is deselected.
- Microsoft Outlook Integration
  - **Prerequisites**:
    - You have installed the 64-bit Microsoft Outlook on your workstation. Supported versions: 2000 SR1 (and higher), 2002, 2003, 2007, 2010, 2013, and 2016.
    - After installing Microsoft Outlook, you created an email account for sending and receiving emails.
    - Microsoft Outlook is set as your default mail client.

    After installing the Microsoft Outlook integration add-on, the *SAP Business One* entry appears in the *Add-Ins* menu of the following Microsoft Office applications:

    - Microsoft Outlook
    - Microsoft Word
    - Microsoft Excel

    For more information about how to use the feature, see the Microsoft Outlook integration online help. The help is available in the *Add-Ins* menu of the above Microsoft Office applications and from within the relevant windows in the SAP Business One client application (by pressing `F1` in the windows).
- Datev FI Interface
  - **Prerequisites**: You have created a new company to work with the DATEV add-on and deselected the checkboxes: *Copy User-Defined Fields and Tables* and *Copy User-Defined Objects*.

    The DATEV add-on may not work with demo databases.
