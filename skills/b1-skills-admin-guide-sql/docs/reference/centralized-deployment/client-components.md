---
title: Installing and Uninstalling Client Components
source: pdf pp. 171-174, sec 10.3
summary: Centrally deploying and removing SAP Business One Client and Data Interface API on registered logical machines from the SLD control center.
---

# Installing and Uninstalling Client Components

After registering a logical machine to SAP Business One System Landscape Directory (SLD), you can centrally deploy SAP Business One Client and Data Interface API on the machine from the SLD control center.

You can also uninstall the client components from the SLD control center.

## Installing Client Components

**Prerequisites**

- You have defined an SAP Business One CD repository folder and central log directory during the installation process. If you have not defined the share folders, you can go to the *Global Settings* tab to configure them. For more information, see [Registering SAP Business One Installation CD](registering-installation-cd.md#registering-sap-business-one-installation-cd) [page 163].
- In the SLD control center, you have registered the logical machine on which you will deploy the client components. For more information, see [Registering and Unregistering Logical Machines](sld-agent-wizard-installation.md#registering-and-unregistering-logical-machines) [page 165].

**Procedure**

1. Log in to the SLD control center.
2. On the *Logical Machines* tab, in the *Logical Machines* area, select the machine on which you intend to deploy components.

   > **Note**
   >
   > You can select multiple machines to install the client components on different machines simultaneously.

3. In the *SAP Business One Components* area, choose *Deploy*.
4. In the *Select Components* window, choose the required client components.

   If you have selected multiple machines to deploy client components simultaneously, in this window you can see the component installation status for each selected machine.

   - If a component has been installed on a machine, you cannot install it again.
   - If a component has not been installed on a machine, you can select the machine under the specific component and choose *Next* to continue the deployment.

   > **Note**
   >
   > You should install the *SAP Business One Client* component together with the *Data Interface API* component.

5. In the *Review* window, review the settings you have made and choose *Start*.
6. In the next *Review* window, choose *Close* to close the window. The deployment operation will continue in the background until it is completed.
7. On the *Logical Machines* tab, in the *SAP Business One Components* area, you can see the *Deployment Status* of the components is either *To be deployed* or *Deploying*. Once the deployment process completes, the status changes to *Deployed*.

   > **Note**
   >
   > If you installed components by running the setup wizard from logical machines, you can see the *Deployment Status* of the components are *Deployed Externally*.

**Next Steps**

If you want an overview of all installed components across the whole landscape, go to the *Components* tab.

## Uninstalling Client Components

**Context**

You can uninstall SAP Business One Client and Data Interface API which have been installed from the SLD control center.

**Procedure**

1. Log in to the SLD control center.
2. On the *Logical Machines* tab, in the *Logical Machines* area, select the machine from which you intend to uninstall components.

   > **Note**
   >
   > You can select multiple machines to uninstall the client components from different machines simultaneously.

3. In the *SAP Business One Components* area, choose *Remove*.
4. In the *Remove and Uninstall Components* window, you can choose if you will simultaneously uninstall the selected SAP Business One Client and DI API components from logical machines, and then choose *Continue*.

   > **Note**
   >
   > If you do not enable the checkbox, the selected components will be only removed from the component list, but not uninstalled from the relevant logical machines.

**Next Steps**

After the uninstallation, you can reinstall SAP Business One Client and Data Interface API from the SLD control center.
