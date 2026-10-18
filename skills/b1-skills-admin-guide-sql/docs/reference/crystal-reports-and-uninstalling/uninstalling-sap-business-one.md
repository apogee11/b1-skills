---
title: Uninstalling SAP Business One
source: pdf pp. 66-67, sec 7*, 7.1
summary: Removing SAP Business One add-ons, server and client components and the DI API, and uninstalling the client agent.
---

# Uninstalling SAP Business One

When you uninstall SAP Business One, you remove the application and its components.

**Procedure**

1. Remove the add-ons:
    1. From the SAP Business One *Main Menu*, choose *Administration* > *Add-Ons* > *Add-On Administration*. The *Add-On Administration* window appears.
    2. On the *Company Preferences* tab, under *Company Assigned Add-Ons*, select the add-ons.
    3. Choose the left arrow between the two panels.
    4. In the *Available Add-Ons* list, select the add-ons you want to remove.
    5. Choose *Remove Add-On*, and then choose the *Update*. SAP Business One automatically removes the add-ons that you have uninstalled the next time you start the SAP Business One application from any workstation that is connected to the server.

        > **Note**
        >
        > You can move XL Reporter to the *Available Add-Ons* panel, but you cannot remove XL Reporter in the *Add-On Administration* window. The *Remove Add-On* button is disabled for XL Reporter.

    6. Log on again to SAP Business One. SAP Business One automatically uninstalls the SAP Business One add-ons that you have removed. This is applicable to all companies on the same server.

    Note that for third-party add-ons, you may need to uninstall them from the Windows Control Panel.

2. Uninstall the server and client components:
    1. On your server or client workstation, choose *Start* > *Control Panel* > *Programs and Features*.
    2. In the *Programs and Features* window, select the following items one at a time and choose *Uninstall/ Change* after each selection:
        - SAP Business One Client
        - SAP Business One Server
        - Data Transfer Workbench
        - SAP Business One Studio
        - SAP Business One SDK
        - SAP Business One Components Wizard

    > **Note**
    >
    > On Windows machines, you can also uninstall SLD Agent by running the `setup.exe` file in the path `C:\Program Files\SAP\SAP Business One SetupFiles\setup.exe`.

3. Remove DI API:
    - If you installed the DI API as part of the client installation of SAP Business One, the system automatically removes the DI API when you uninstall the SAP Business One client.
    - If you installed the DI API using the manual setup program in the `b1_shf/B1DIAPI` folder, you must remove it by choosing *Control Panel* > *Programs* > *Programs and Features* and selecting *SAP Business One DI API*.

**Results**

SAP Business One entries no longer appear in the Programs menu and any shortcuts that you may have on the Microsoft Windows desktop are removed.

You can now do the following:

- Manually delete the SAP Business One folders in Microsoft Windows Explorer.
- Remove SAP Business One databases using your database management application.

## Uninstalling SAP Business One Client Agent

The SAP Business One client agent is automatically uninstalled when you uninstall SAP Business One client. However, if the client agent cannot be uninstalled successfully, you can also uninstall it manually.

To uninstall SAP Business One client agent, in the *Programs and Features* window, select SAP Business One Client Agent and choose *Uninstall/Change*.
