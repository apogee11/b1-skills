---
title: Change Log 2026 (10.0 FP 2608, SP 2605, FP 2602)
source: pdf pp. 8-11, sec 2*, 2.1, 2.2, 2.3
summary: Document history of the guide: what changed in 10.0 FP 2608, SP 2605 and FP 2602, with the topics affected.
---

# Change Log 2026 (10.0 FP 2608, SP 2605, FP 2602)

The document history is a record of additions and major changes to the *SAP Business One Administrator/s Guide*.

## Change Log 10.0 FP 2608

<!-- table: t008-01 -->
- **Topic**: Introduction
  - **Description**: A row is added to the table for Electronic File Mapping Transformation Service.
  - **Link to Related Section**: Server Components (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/49a6449d6bb5484584164ebaf57bf33b.html?version=10.0_SP_2608)
- **Topic**: Installing SAP Business One, version for SAP HANA
  - **Description**:

    - Electronic File Mapping Transformation Service is added to the list of server components.
    - The prerequisite of requirement of .NET Core SDK 6.0.302 for installing Electronic Document Service is removed.
    - A new topic about installing Electronic File Mapping Transformation Service is added.

  - **Link to Related Section**:

    - Installing Server Components (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/7228f7bd335344abbb42869bf467f61d.html?version=10.0_SP_2608)
    - Installing Electronic Document Service (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/fc679f408abf486da9a62fe9b415939d.html?version=10.0_SP_2608)
    - Installing Electronic File Mapping Transformation Service (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/e15a3b11ee8b4ed59e46b0f58636e769.html?version=10.0_SP_2608)

- **Topic**: Installing SAP Crystal Reports, version for the SAP Business One Application
  - **Description**: A note about certain runtime files that will no longer be available from 10.0 FP 2608 is added.
  - **Link to Related Section**: Installing SAP Crystal Reports, version for the SAP Business One Application (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/b7816cc9ae3d4bffbb0538871ce603f6.html?version=10.0_SP_2608)
- **Topic**: Upgrading SAP Business One
  - **Description**: A step to show status of backed up databases is added: (`SLDModel.SLDDATA` and `B1AS`)
  - **Link to Related Section**: Upgrading SAP Business One Databases and Components (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/3ac158a25bcd43ec96d505d3b56c2c9a.html?version=10.0_SP_2608)
- **Topic**: Performing Post-Installation Activities
  - **Description**:

    - Electronic File Mapping Transformation Service is added to the list of services added to the SLD and also its URL to the procedure.
    - A section for User Audit Logs is added.
    - Electronic File Mapping Service is added to the table and added a step to the procedure to change its port number.
    - OpenTelemetry integration for end-to-end performance tracing is added.

  - **Link to Related Section**:

    - Adding Services in the System Landscape Directory (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/6fca5612dc634f19830ca92f16c03778.html?locale=en-US&version=10.0_SP_2608)
    - Working with Audit Logs (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/2e9c504419dc466a9533963b3bf7e1b6.html?version=10.0_SP_2608)
    - Reconfiguring the System (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/9662ad31717d4c60bd8885aa7c649747.html?version=10.0_SP_2608)
    - Monitoring Performance with OpenTelemetry (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/680d1ed1a66244aab7dbe40bcff7e4bb.html?version=10.0_SP_2608)
    - Using OpenTelemetry to Address Performance Issues (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/35fb7b25217d4819b45c94ea5b411c88.html?version=10.0_SP_2608)
    - Collecting and Exporting Telemetry Data for Performance Analysis (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/ccd109d0f58b4568ba7fad301013566b.html?version=10.0_SP_2608)

- **Topic**: Managing Security in SAP Business One
  - **Description**:

    - Added topics for Electronics File Mapping Transformation Services under application security
      - Encryption
      - Scheduled Periodic Key Rotation
      - Manual Key Rotation
      - Verification of Key Rotation Results

  - **Link to Related Section**:

    - Electronic File Mapping Transformation Service (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/cd38b725961e493d9a1509330c597079.html?version=10.0_SP_2608)
    - Encryption (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/ed2e90c77fd24cbbaae2d82f552a4721.html?version=10.0_SP_2608)
    - Scheduled Periodic Key Rotation (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/6855dfccf5f64ba182d4e9588e584e5a.html?version=10.0_SP_2608)
    - Manual Key Rotation (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/d4da6cb7b9974c28b70a0a10b373cda0.html?version=10.0_SP_2608)
    - Verification of Key Rotation Results (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/f42bbe0b170e45d1bcd5c98ea4161356.html?version=10.0_SP_2608)

- **Topic**: Appendix
  - **Description**:

    - Added the port for Electronic File Mapping Transformation Service to the list of default ports.
    - Added an entry for Electronic File Mapping Transformation Service to the log file locations table in the server tools section.
    - Added an entry for Electronic File Mapping Transformation Service to the security certificate usage table in the server components section.

  - **Link to Related Section**:

    - List of Default Ports for Different Server Components (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/fc4a12676bdb4729a56bf63adc8478c1.html?version=10.0_SP_2608)
    - List of Log File Locations for SAP Business One Components (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/aea6cf4a20f940ad80ee11d24441b415.html?version=10.0_SP_2608)
    - List of Security Certificate Usage for SAP Business One Components (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/dd0173b26a904d1d8552fd4fd2b23dfe.html?version=10.0_SP_2608)

## Change Log 10.0 SP 2605

<!-- table: t009-02 -->
- **Topic**: Performing Post-Installation Activities
  - **Description**: A new section about reconfiguring the Browser Access Service is added.
  - **Link to Related Section**: Reconfiguring the Browser Access Service (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/28f2aab29a964eba81faa20c903ff479.html?version=10.0_SP_2605)
- **Topic**: Managing Security in SAP Business One
  - **Description**:

    - The minimum value of the retention period for an audit log entry in the database is changed to `604800000` milliseconds (1 week).
    - The SAP JVM version is upgraded to SAP Machine 21.

  - **Link to Related Section**:

    - Retention Period of Audit Logs in the Database (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/7809d0ad82db494fb237aceebce9d036.html?version=10.0_SP_2605)
    - Other Security Recommendations (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/0fd5740b618c4ed494fb17f6d1547256.html?version=10.0_SP_2605)

- **Topic**: Appendix
  - **Description**: A new list about security certificate usage is added.
  - **Link to Related Section**: List of Security Certificate Usage for SAP Business One Components (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/dd0173b26a904d1d8552fd4fd2b23dfe.html?version=10.0_SP_2605)

## Change Log 10.0 FP 2602

<!-- table: t010-01 -->
- **Topic**: Introduction
  - **Description**: Two new server components, Microsoft 365 Integration and Webhook Messenger, are introduced.
  - **Link to Related Section**: Server Components (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/49a6449d6bb5484584164ebaf57bf33b.html?version=10.0_SP_2602)
- **Topic**: Installing SAP Business One
  - **Description**: The installation of the new server components, Microsoft 365 Integration and Webhook Messenger, are introduced.
  - **Link to Related Section**:

    - Installing Server Components (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/7228f7bd335344abbb42869bf467f61d.html?version=10.0_SP_2602)
    - Installing Webhook Messenger (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/566832782c14418e9a466ebfae1c028b.html?version=10.0_SP_2602)

- **Topic**: Upgrading SAP Business One
  - **Description**: The upgrade of the new server component, Microsoft 365 Integration, is introduced.
  - **Link to Related Section**:

    - Upgrading SAP Business One Databases and Components (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/3ac158a25bcd43ec96d505d3b56c2c9a.html?version=10.0_SP_2602)
    - Performing Silent Upgrades (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/8a19aa3b8d454b90aedca1ab0d5f75b2.html?version=10.0_SP_2602)

- **Topic**: Performing Post-Installation Activities
  - **Description**:

    - A new paragraph for the new columns is added
    - A new section *Disabling Certificate Expiry Warnings* is added.
    - License Control Center is updated.
    - The Service URLs for Microsoft 365 Integration and Webhook Messenger are added.
    - The reconfiguration information of Microsoft 365 Integration and Webhook Messenger is added.
    - A new section about configuring Microsoft 365 Integration is added.
    - A new section about configuring Webhook Messenger is added.
    - Enabling external access to Microsoft 365 Integration is added.

  - **Link to Related Section**:

    - Adding Services in the System Landscape Directory (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/6fca5612dc634f19830ca92f16c03778.html?version=10.0_SP_2602)
    - Disabling Certificate Expiry Warnings (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/93e36a1366cc4911a4988e4a0f218e6d.html?version=10.0_SP_2602)
    - License Control Center (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/25a9e521a7e445fb92bfcd90baae1fa0.html?version=10.0_SP_2602)
    - Reconfiguring Server Tools, Service Layer, Web Client, Webhook Messenger, Electronic Document Service and SLD Agent (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/9662ad31717d4c60bd8885aa7c649747.html?version=10.0_SP_2602)
    - Microsoft 365 Integration (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/cef4f28264904dccb1e183525f67f4ee.html?version=10.0_SP_2602)
    - Webhook Messenger (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/9adbe1258bc949ccb54bd2cddbe47abc.html?version=10.0_SP_2602)
    - Reverse Proxy Mode (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/4eaeaad14eb841f2bda88107c45d6f70.html?version=10.0_SP_2602)
    - NAT/PAT (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/ca12d8409ad74a9c80627b0ce0648e40.html?version=10.0_SP_2602)
    - Mapping External Addresses to Internal Addresses (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/09a4fa3b343e43f7bfa65c56c664ea52.html?version=10.0_SP_2602)

- **Topic**: Managing Security in SAP Business One
  - **Description**: The default port number for Microsoft 365 Integration is added.
  - **Link to Related Section**: Components in Tomcat Instances (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/7e4904eaff644b1984b44629b5cb7b6b.html?version=10.0_SP_2602)
- **Topic**: Appendix
  - **Description**: The default port numbers for Microsoft 365 Integration and Webhook Messenger are added.
  - **Link to Related Section**: List of Default Ports for Different Server Components (https://help.sap.com/docs/SAP_BUSINESS_ONE_ADMIN_GUIDE_SQL/f6fb230cc90949d8b66586a39189992b/fc4a12676bdb4729a56bf63adc8478c1.html?version=10.0_SP_2602)
