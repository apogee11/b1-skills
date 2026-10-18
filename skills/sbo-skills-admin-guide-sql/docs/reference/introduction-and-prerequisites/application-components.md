---
title: Application Components Overview
source: pdf pp. 22-26, sec 3.2
summary: The server and client components of SAP Business One, with a description, 32-bit or 64-bit type and whether each is mandatory.
---

# Application Components Overview

This section provides a description of the software components of SAP Business One and how they are used by the business processes of SAP Business One.

## Server Components

Some server components are essential to the system landscape and are thus mandatory, while the others are optional, and you can install them if there's a business need.

<!-- table: t022-01 -->
- **Component**: System Landscape Directory (SLD)
  - **Description**: Authenticates users and manages an entire SAP Business One landscape. Precondition for all other components.
  - **Type**: 64-bit
  - **Mandatory?**: Yes
- **Component**: License Service
  - **Description**: Manages license requests.
  - **Type**: 64-bit
  - **Mandatory?**: Yes
- **Component**: Extension Manager
  - **Description**: Manages deployment of lightweight add-ons.
  - **Type**: 64-bit
  - **Mandatory?**: No
- **Component**: Job Service
  - **Description**:

    Manages alert settings and SBO Mailer settings on the server side.

    The SBO Mailer allows you to send documents directly from the client application through email.

  - **Type**: 64-bit
  - **Mandatory?**: No
- **Component**: Microsoft 365 Integration
  - **Description**: Enables export of documents, reports and queries to Microsoft OneDrive or SharePoint, and allows sending emails and meeting requests using a connected Microsoft 365 account.
  - **Type**: 64-bit
  - **Mandatory?**: No
- **Component**: Workflow Service
  - **Description**: Enables you to implement user-defined business processes.
  - **Type**: 64-bit
  - **Mandatory?**: No
- **Component**: Mobile Service
  - **Description**:

    Enables you to use mobile apps (for example, SAP Business One Sales) based on the Service Layer.

    The Service Layer is required to be installed on the database instance to which the mobile service connects.

  - **Type**: 64-bit
  - **Mandatory?**: No
- **Component**: Browser Access Service
  - **Description**: Enables you to access the SAP Business One client application in a Web browser.
  - **Type**: 64-bit
  - **Mandatory?**: No
- **Component**: Data Interface Server (DI Server)
  - **Description**: Supports high-volume data integration and enables multiple clients to access and manipulate SAP Business One company databases (schemas).
  - **Type**: 64-bit
  - **Mandatory?**: No
- **Component**: Repository
  - **Description**:

    Includes:

    - System database `SBOCOMMON` that holds system data, version information, and upgrade information. Unlike company databases, `SBOCOMMON` does not store any business or transactional data.
    - Shared folder `B1_SHR` that contains central configuration data as well as installation files for various client components.

  - **Type**: 32-bit
  - **Mandatory?**: Yes
- **Component**: Remote Support Platform (RSP)
  - **Description**: Proactively monitors the health of an SAP Business One installation and provides automated healing, backup support, and download of software patches.
  - **Type**: 32-bit
  - **Mandatory?**: Yes

<!-- table: t024-01 -->
- **Component**: Integration Framework
  - **Description**:

    A set of business scenarios that enable integration of the SAP Business One application with third-party software and mobile devices.

    The integration packages include:

    - Mobile Solution
      For more information about mobile scenarios, search for the user guide for the SAP Business Mobile app on SAP Help Portal (https://help.sap.com/viewer/p/SAP_BUSINESS_ONE_PRODUCT_LINE). Note that there are different user guides for the iOS and the Android versions.
    - DATEV HR (Germany only)
      For more information about DATEV HR, see *Leitfaden zur Personalabrechnung mit DATEV HR (German only)* on SAP Help Portal.
    - Electronic Invoices (Mexico only)
    - Support for Document Approval (Portugal only)
    - Support for SAP Customer Checkout
      For more information, see the *SAP Customer Checkout with SAP Business One: Integration* (https://help.sap.com/docs/SAP_CUSTOMER_CHECKOUT/b3ef5bb1234b4776bc5f19afbc601405/b3de0a0ba5e849c39af0f392beea6198.html?version=2.0.21_Corr4) guide. To display the guide in the integration framework, choose *Scenarios* > *Control* and for `sap.CustomerCheckout`, choose *Docu*.

  - **Type**: 32-bit
  - **Mandatory?**: No
- **Component**: Add-Ons
  - **Description**:

    Add-ons are additional components or extensions for SAP Business One.

    SAP Business One provides the 64-bit add-ons as follows:

    - Electronic File Manager Format Definition
    - Microsoft Outlook Integration
    - Payment Engine

  - **Type**: 64-bit
  - **Mandatory?**: No
- **Component**: Outlook Integration Server
  - **Description**: Includes Microsoft Office templates required for the Microsoft Outlook integration add-on.
  - **Type**: 64-bit
  - **Mandatory?**: No
- **Component**: Outlook Integration Standalone
  - **Description**: Standalone installer that allows you to install the Microsoft Outlook integration add-on without installing the SAP Business One client on your PC.
  - **Type**: 64-bit
  - **Mandatory?**: No
- **Component**: Service Layer
  - **Description**: An application server that provides Web access to SAP Business One services and objects.
  - **Type**: 64-bit
  - **Mandatory?**: No
- **Component**: Web Client
  - **Description**: Offers the SAP Business One core business logic and processes provided in the new SAP Fiori user experience.
  - **Type**: 64-bit
  - **Mandatory?**: No
- **Component**: Webhook Messenger
  - **Description**: Is a high-performance component running in the SAP Business One landscape, designed to efficiently retrieve and deliver event notifications to partners' webhooks on a company database basis.
  - **Type**: 64-bit
  - **Mandatory?**: No
- **Component**: Electronic Document Service
  - **Description**: Processes and monitors the communication of electronic transactions in a customizable platform.
  - **Type**: 64-bit
  - **Mandatory?**: No
- **Component**: Electronic File Mapping Transformation Service
  - **Description**: Enables users to transform data from an input source to an output format that is desired by the user.
  - **Type**: 64-bit
  - **Mandatory?**:

    No.

    Required only if users need electronic documents and report functionality.

- **Component**: API Gateway Service
  - **Description**: Serves as the gateway to authenticate SBO users and forward requests for backend services, such as the Reporting Service.
  - **Type**: 64-bit
  - **Mandatory?**: No

## Client Components

<!-- table: t025-02 -->
- **Component**: SAP Business One Client
  - **Description**: The application executable. You can also install the client application on a terminal server or in a Citrix environment.
  - **Type**: 64-bit
  - **Mandatory?**: Yes
- **Component**: SAP Business One Client Agent
  - **Description**:

    Performs actions that require administrator rights on the local system (for example, upgrading the SAP Business One client and add-ons).

    > **Note**
    >
    > As of the release 10.0 FP 2305, the SAP Business One client agent does not move SAP Business One log files to the central log folder in the shared folder.

    > **Note**
    >
    > The client agent is part of the client installation process and is installed by default.

  - **Type**: 32-bit
  - **Mandatory?**: Yes
- **Component**: DI API
  - **Description**: Data interface API, a COM-based API and an applicative DLL file (`OBSever.dll`) that enables add-ons to access and use SAP Business One business objects.
  - **Type**: 64-bit
  - **Mandatory?**: Yes
- **Component**: UI API
  - **Description**: User interface API, a COM-based API that is connected to the running application and which enables add-ons to perform runtime manipulation and enhancement of the SAP Business One GUI and its flow.
  - **Type**: 64-bit
  - **Mandatory?**: Yes
- **Component**: Software Development Kit
  - **Description**: Documentation and samples for the SAP Business One SDK.
  - **Type**: 32-bit
  - **Mandatory?**: No
- **Component**: DTW
  - **Description**: Data transfer workbench which enables importing and updating data in large volumes.
  - **Type**: 64-bit
  - **Mandatory?**: No
- **Component**: SAP Business One Studio Suite
  - **Description**: An integrated development environment based on the Microsoft .NET Framework, which supports you in developing extensions on top of SAP Business One.
  - **Type**: 64-bit
  - **Mandatory?**: No
- **Component**: Solution Packager
  - **Description**: A tool for packaging your industry solutions for fast deployment. For example, you can package your user-defined tables and fields, queries, reports, and configurations, and then use the package to create new, but pre-configured, companies in SAP Business One.
  - **Type**: 64-bit
  - **Mandatory?**: No

> **Note**
>
> If you intend to install the SLD Agent on the server or workstations, you need to run the **Components Setup Wizard**. For more information, see [Manually Installing SLD Agent Service](../centralized-deployment/sld-agent-wizard-installation.md#manually-installing-sld-agent-service) [page 165].
