---
title: Standard Users
source: pdf pp. 205-208, sec 12.2.2
summary: The predefined standard users needed to operate SAP Business One (B1SiteUser, manager, B1i, Workflow, Support), with their type, password and purpose.
---

# Standard Users

The table below shows the standard users that are necessary for operating SAP Business One.

> **Recommendation**
>
> For security reasons, we recommend that at the first logon, you create another standard user account as a substitute for the `default standard` user and disable the default user.

> **Recommendation**
>
> For security reasons, we recommend that at the first logon, you create another standard user account which is assigned only necessary authorizations as a substitute for the `default standard` user and disable the default user.

<!-- table: t206-01 -->
<!-- table: t206-02 -->
<!-- table: t206-03 -->
<!-- table: t207-01 -->
<!-- table: t207-02 -->
<!-- table: t208-01 -->
- **System**: System Landscape Directory
  - **User ID**: `B1SiteUser`
  - **Type**: Landscape administrator
  - **Password**: The password defined during the SLD installation process.
  - **Description**: It serves as site-level authentication for performing various administrative tasks with the following functions:
    - Life cycle management: installation, upgrade, uninstallation
    - Configuring services installed on Windows (for example, Workflow service)
    - Company creation
- **System**: SAP Business One Company
  - **User ID**: `manager`
  - **Type**: Company superuser
  - **Password**:
    - `manager`: All except Hebrew
    - **מנהל**: Only for Hebrew
  - **Description**: When you create a company, a predefined superuser named `manager` exists in the system. Due to the password policy, you must change the password of the `manager` user at the first logon.

    You can also create new superusers. The responsibilities of a superuser include:
    - Defining users in companies and setting user permissions
    - Assigning licenses
    - Configuring password policy at the company level
    - Upgrading companies
- **System**: SAP Business One Company
  - **User ID**: `B1i`
  - **Type**: Company superuser
  - **Password**: A randomly generated password. You can change it when logging on with another superuser account.
  - **Description**: The `B1i` user is a default technical user for the integration framework. The integration framework uses the `B1i` user to connect to SAP Business One (for example, to check authentication when using the mobile solution).

    For more information, see [Technical B1i User](../integration-framework-post-install/maintenance-monitoring-and-security.md#technical-b1i-user) [page 149].
- **System**: SAP Business One Company
  - **User ID**: `Workflow`
  - **Type**: Company superuser
  - **Password**: A randomly generated password. You can change it when logging on with another superuser account.
  - **Description**: The `Workflow` user is a default technical user used for the workflow service. This technical user is used for logging in to DI and running the workflow script.

    As of 10.0 FP 2208. The `Workflow` user is used for the alert service instead of the `AlertSvc` user.

    For more information about activating the `Workflow` user in SAP Business One Client, see *How to Configure the Workflow Service and Design the Workflow Process Templates* at SAP Help Portal (https://help.sap.com/viewer/p/SAP_BUSINESS_ONE_PRODUCT_LINE).
- **System**: SAP Business One Company
  - **User ID**: `Support`
  - **Type**: Company superuser
  - **Password**: A randomly generated password. You can change it when logging on with another superuser account.
  - **Description**: A `Support` user (user code: `Support`) is created upon the installation or upgrade of SAP Business One companies. This new user is provided for support and consulting purposes.

    The `Support` user does not require a license to access the system. This can minimize the disruption to business where a user may previously have needed to log off the system to free up a license for support.

    > **Note**
    >
    > Certain advanced features (such as the analytics features) are not available for the `Support` user.

    While the `Support` user does not need a license, they have the same access rights as those of a user with a Professional User license. Therefore, strict usage rules are applied to the `Support` user to prevent misuse, as follows:
    - After logging on to the company using the `Support` user account, the user must identify him/herself by entering his/her real name and selecting a login reason in the *Support User Login* window.
    - You can active the `Support` user either via the System Status Report (SSR) upload from the Remote Support Platform (RSP), or through the SLD control center. The session timeout for the `Support` user is standardized to 4 hours, irrespective of the activation method used.
    - The usage of the `Support` user is recorded (including the real name and the login reason). You can review the log records in the *Support User Log* window under *Administration* > *License*.

    > **Note**
    >
    > If you had already created a user account `Support` before upgrading companies, the `Support` user will have the features described above after the upgrade. The licenses assigned to the original user account, the password and all other settings for the original user account remain unchanged. You can transfer any license assignments of this account to another user because they are no longer required by the `Support` user.

    A `Support` user is allowed to log into an SAP Business One client via two sessions at the same time. You can use the `Support` user to open another session without locking the first one.

    A `Support` user must be bound to one identity provider user if an identity provider is activated.
