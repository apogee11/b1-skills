---
title: Security Certificate Usage for SAP Business One Components
source: pdf pp. 278-280, sec 15.3
summary: Which certificate (shared Server Tools or dedicated) each SAP Business One service uses, how to renew it, and how to start the reconfiguration.
---

# Security Certificate Usage for SAP Business One Components

The following table lists the security certificate usage for SAP Business One components and services.

<!-- table: t278-02 -->
- **Component**: System Landscape Directory (SLD)
  - **Service Name**: SAP Business One Server Tools Service (64-bit) (B1ServerTools64)
  - **Certificate Usage**: Shared (Server Tools) certificate
  - **Certificate Renewal Approach**: Perform reconfiguration using SAP Business One Components Wizard
- **Component**: Authentication Service in the SLD
  - **Service Name**: SAP Business One Server Tools Authentication Service (B1ServerToolsAuthentication)
  - **Certificate Usage**: Shared (Server Tools) certificate
  - **Certificate Renewal Approach**: Perform reconfiguration using SAP Business One Components Wizard
- **Component**: License Service
  - **Service Name**: SAP Business One License Service (64-bit) (B1ServerTools64License)
  - **Certificate Usage**: Shared (Server Tools) certificate
  - **Certificate Renewal Approach**: Perform reconfiguration using SAP Business One Components Wizard
- **Component**: Job Service
  - **Service Name**: SAP Business One Job Service (64-bit) (B1ServerTools64JobService)
  - **Certificate Usage**: Shared (Server Tools) certificate
  - **Certificate Renewal Approach**: Perform reconfiguration using SAP Business One Components Wizard
- **Component**: Workflow Service
  - **Service Name**: SAP Business One Workflow Engine (B1Workflow)
  - **Certificate Usage**: Shared (Server Tools) certificate
  - **Certificate Renewal Approach**: Perform reconfiguration using SAP Business One Components Wizard
- **Component**: Mobile Service
  - **Service Name**: SAP Business One Service Layer Controller (64-bit) (B1ServerTools64ServiceLayerController)
  - **Certificate Usage**: Shared (Server Tools) certificate
  - **Certificate Renewal Approach**: Perform reconfiguration using SAP Business One Components Wizard
- **Component**: Browser Access Service
  - **Service Name**: SAP Business One Browser Access Server Gatekeeper (64-bit) (Gatekeeper64)
  - **Certificate Usage**: Dedicated certificate
  - **Certificate Renewal Approach**:

    Perform reconfiguration using the InstallShield Wizard (*Control Panel* > *Programs* > *Programs and Features* > *SAP Business One Browser Access Server Gatekeeper* > *Uninstall*)

    The approach is available since 10.0 SP 2605.

- **Component**: Integration Framework
  - **Service Name**: SAP Business One Integration Service (Tomcat10)
  - **Certificate Usage**: Dedicated certificate
  - **Certificate Renewal Approach**: Manually generate and update the SSL certificates. For more information, see SAP Note 3743471 (https://me.sap.com/notes/0003743471).
- **Component**: Service Layer
  - **Service Name**:

    SAP Business One Service Layer Load Balancer (b1s50000)

    SAP Business One Service Layer Node (50001..50010) (b1s50001..b1s50010)

  - **Certificate Usage**: Shared (Server Tools) certificate
  - **Certificate Renewal Approach**: Perform reconfiguration using SAP Business One Components Wizard
- **Component**: Web Client
  - **Service Name**: WebClient (WebClient)
  - **Certificate Usage**: Shared (Server Tools) certificate
  - **Certificate Renewal Approach**: Perform reconfiguration using SAP Business One Components Wizard
- **Component**: Webhook Messenger
  - **Service Name**: SAP Business One Webhook Messenger (WebhookMessengers)
  - **Certificate Usage**: Shared (Server Tools) certificate
  - **Certificate Renewal Approach**: Perform reconfiguration using SAP Business One Components Wizard
- **Component**: Electronic Document Service
  - **Service Name**: SAP Business One EDF Back-end (SAPB1EDFBackend)
  - **Certificate Usage**: Shared (Server Tools) certificate
  - **Certificate Renewal Approach**: Perform reconfiguration using SAP Business One Components Wizard
- **Component**: Electronic File Mapping Transformation Service
  - **Service Name**: SAP Business One EFM Transformation Service (SAPB1EFMTService)
  - **Certificate Usage**: Shared (Server Tools) certificate
  - **Certificate Renewal Approach**: Perform reconfiguration using SAP Business One Components Wizard
- **Component**: API Gateway Service
  - **Service Name**: SAP Business One API Gateway Service (b1gatewaysvc)
  - **Certificate Usage**: Shared (Server Tools) certificate
  - **Certificate Renewal Approach**: Perform reconfiguration using SAP Business One Components Wizard

To perform the reconfiguration process in a Windows machine, run the `setup.exe` file from the SAP Business One installation folder. The default path is `C:\Program Files\SAP\SAP Business One SetupFiles`

You can also start the Components Wizard in the *Programs and Features* window (*Control Panel* > *Programs* > *Programs and Features* > *SAP Business One Components Wizard*).

For more information about the reconfiguration process, see [Reconfiguring the System](../reconfiguring-the-system/reconfiguring-components.md) [page 158].

> **Note**
>
> **SAP Business One Components Wizard** is used by the **SAP Business One Setup Wizard** in the background to install the SLD and selected components, and it can also be used as a standalone tool to install server-side components.
