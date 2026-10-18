---
title: Change Log 2025 (10.0 SP 2511, FP 2508, SP 2505, FP 2502)
source: pdf pp. 11-13, sec 2.4, 2.5, 2.6, 2.7
summary: Document history of the guide: what changed in 10.0 SP 2511, FP 2508, SP 2505 and FP 2502, with the topics affected.
---

# Change Log 2025 (10.0 SP 2511, FP 2508, SP 2505, FP 2502)

## Change Log 10.0 SP 2511

<!-- table: t011-01 -->
- **Topic**: Prerequisites
  - **Description**: SAP Business One newly supports Microsoft Windows Server 2025.
  - **Link to Related Section**: Prerequisites (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/a3f76b099c294630a7b38c2aba1de758.html?version=10.0_SP_2511)
- **Topic**: Installing SAP Business One
  - **Description**: New installation steps for defining service ports are added.
  - **Link to Related Section**: Installing Server Components (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/7228f7bd335344abbb42869bf467f61d.html?version=10.0_SP_2511)
- **Topic**: Upgrading SAP Business One
  - **Description**: New upgrade steps for defining service ports are added.
  - **Link to Related Section**: Upgrading SAP Business One Databases and Components (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/3ac158a25bcd43ec96d505d3b56c2c9a.html?version=10.0_SP_2511)
- **Topic**: Performing Post-Installation Activities
  - **Description**: New reconfiguration steps for defining service ports are added.
  - **Link to Related Section**: Reconfiguring Server Tools, Service Layer, Web Client, Electronic Document Service and SLD Agent (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/9662ad31717d4c60bd8885aa7c649747.html?version=10.0_SP_2511)
- **Topic**: Managing Security in SAP Business One
  - **Description**:

    - New ports are added and the Tomcat configuration file path is updated.
    - The section *Workflow* is removed and its relevant content is integrated into the section *Components in Tomcat Instances*.

  - **Link to Related Section**: Components in Tomcat Instances (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/7e4904eaff644b1984b44629b5cb7b6b.html?version=10.0_SP_2511)
- **Topic**: Appendix
  - **Description**: New ports are added for the license service, job service, service layer controller and mobile service.
  - **Link to Related Section**: List of Default Ports for Different Server Components (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/fc4a12676bdb4729a56bf63adc8478c1.html?version=10.0_SP_2511)

## Change Log 10.0 FP 2508

<!-- table: t011-02 -->
- **Topic**: Installing SAP Business One
  - **Description**: A note for the *Landscape Server* window is added.
  - **Link to Related Section**:

    - Installing the Service Layer (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/10fd5e1cc64447098fb8feb73276f114.html?version=10.0_SP_2508)
    - Installing Web Client (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/750887bc56224ebfa2b4877c6d5c55e2.html?version=10.0_SP_2508)
    - Installing Electronic Document Service (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/fc679f408abf486da9a62fe9b415939d.html?version=10.0_SP_2508)

<!-- table: t012-01 -->
- **Topic**: Performing Post-Installation Activities
  - **Description**:

    - A new section *Enabling the Remember Sign-In Credentials Option* is added.
    - The SBO Mailer is moved from the Server Tools interface to the Job Service Web page.
    - A new authentication type is added in the step of configuring the SBO Mailer in the Job Service Web page.
    - A new section *Registering an Application on Microsoft Entra ID* is added.
    - A new section *Registering the Service Principal in Exchange Server* is added.

  - **Link to Related Section**:

    - Enabling the Remember Sign-In Credentials Option (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/ee2a3f4d745c42e68b91af7b6cce4616.html?version=10.0_SP_2508)
    - Configuring SBO Mailer (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/56692d97187a483a8df67618e5c67302.html?version=10.0_SP_2508)
    - Registering an Application on Microsoft Entra ID (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/dba48b1e2d624648b9079b8e1d76c49b.html?version=10.0_SP_2508)
    - Registering the Service Principal in Exchange Server (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/b19b2e4e8ba64e25bfd7c3b82cf62fdb.html?version=10.0_SP_2508)

## Change Log 10.0 SP 2505

<!-- table: t012-02 -->
- **Topic**: Performing Post-Installation Activities
  - **Description**:

    - A recommendation about enabling the IAM service is added.
    - A new section about setting up an attachment folder is added.

  - **Link to Related Section**:

    - Performing Post-Installation Activities (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/a605c484ffe74a9fb114246d8df13fc3.html?version=10.0_SP_2505)
    - Setting Up an Attachment Folder (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/00e1c48339854d88b3e6fdf841e63dca.html?version=10.0_SP_2505)

- **Topic**: Managing Security in SAP Business One
  - **Description**:

    - The link to *Password Administration* is referenced.
    - A paragraph about supporting the TLS protocol during the installation is added.
    - The obsolete procedure is deleted and a new note is added.
    - A new section *Database Connection Security for SAP Crystal Reports, version for the SAP Business One Application* is added.
    - The prcedure for enabling encryption keys for SLD data is updated and the new sections about creating and disabling dynimic keys are added.

  - **Link to Related Section**:

    - Changing Passwords (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/8213d9d91dfd40ae84563a588f920549.html?version=10.0_SP_2505)
    - Database Authentication (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/a53fc09224d44f13a14d46686e42430e.html?version=10.0_SP_2505)
    - Enabling Single Sign-On (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/a94724422d8d438a8a349d316ea84de8.html?version=10.0_SP_2505)
    - Database Connection Security for SAP Crystal Reports, version for the SAP Business One Application (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/b1583a3c5f9c40c7ba139c8e8b4dac9b.html?version=10.0_SP_2505)
    - System Landscape Directory Data Encryption (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/01b5904606924f05aa8d40353836b831.html?version=10.0_SP_2505)

## Change Log 10.0 FP 2502

<!-- table: t013-01 -->
- **Topic**: Introduction
  - **Description**: The typle of SBO Mailer is changed to 64-bit.
  - **Link to Related Section**: Server Components (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/49a6449d6bb5484584164ebaf57bf33b.html?version=10.0_SP_2502)
- **Topic**: Performing Post-Installation Activities
  - **Description**:

    - The sections *Enabling Dynamic Encryption Keys for the Data in Company Databases* and *Exporting and Importing Configuration File* are deleted.
    - A new section about managing dynamic keys is added.
    - A new section about activating the `Support` user is added.
    - A new section about refreshing encryption is added.

  - **Link to Related Section**:

    - Managing Dynamic Keys (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/b3186e9b66e14ea7924a20cc4a3e3443.html?version=10.0_SP_2502)
    - Activating the Support User (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/766db2dd75094f239edffb9bf1cd9b96.html?version=10.0_SP_2502)
    - Refreshing Encryption (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/143d4cb58a044db58928552efba24915.html?version=10.0_SP_2502)

- **Topic**: Managing Security in SAP Business One
  - **Description**: The sections *Exporting Configuration Files* and *Importing Configuration Files* are deleted.
