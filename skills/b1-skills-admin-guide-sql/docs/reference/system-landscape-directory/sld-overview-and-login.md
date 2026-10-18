---
title: SLD Overview and Logging In
source: pdf pp. 84-85, sec 9*, 9.1*, 9.1.1
summary: Post-installation activities, what the SLD control center is used for, and how to log in to it.
---

# SLD Overview and Logging In

Immediately after installing SAP Business One, you are required to perform the following activities:

- Configure services
- Install the license key
- Assign add-ons
- Perform post-installation activities for the integration framework

> **Recommendation**
>
> - We recommend you configure a backup strategy for databases and application folders. For more information, see [Backing Up Databases](../maintaining-databases/backing-up-databases.md) [page 184]. You can use the remote support platform for SAP Business One to automatically back up data according to a defined strategy. For more information, see the online help for the remote support platform.
> - We strongly recommend that you enable the Identity and Authentication Management (IAM) service via the System Landscape Directory (SLD) control center after installing SAP Business One. Connecting SAP Business One to an identity provider can help you manage user access in a secure manner without compromising on user experience during login to SAP Business One. For more information about how to configure identity and authentication management, see Configuring Identity and Authentication Management in the System Landscape Directory (https://help.sap.com/viewer/548d6202b2b6491b824a488cfc447343/10.0_SP_2608/en-US/cfe62504080c48199d703d0a2092ac72.html).

> **Note**
>
> If you use a proxy for your Internet connection, you must add the full hostname or IP address of any Web server (for example, SLD) to the proxy exception list of your Web browser; in other words, do not use a proxy for these addresses.

## Working with the System Landscape Directory

The System Landscape Directory (SLD) control center is a central workplace where you perform various administrative tasks.

You can access the SLD control center in a Web browser for the following:

- Performing centralized deployment
- Adding services in the System Landscape Directory
- Configurating SAP Business One authentication service
- Managing dynamic keys
- Mapping external addresses to internal addresses
- Working with audit logs
- Managing identity providers
- Managing users
- Activating the `Support` user

> **Note**
>
> For statistics (SAP Business One usage frequency) used internally by SAP only, we use information including system number and hardware key from your SAP Business One landscape.

## Logging in to the System Landscape Directory Control Center

**Context**

After the installation, the SLD service starts automatically. You can then access the SLD control center in a Web browser.

**Procedure**

1. In a Web browser, navigate to the following URL: `https://<Server Address>:<Port>/ControlCenter`

   > **Note**
   >
   > The URL address is case-sensitive.

   The default port number is `40000`.

2. In the logon page, enter the name and password for a landscape administrator (for example, `B1SiteUser`).

   > **Note**
   >
   > The landscape administrator name is case-sensitive.

3. Choose *Log In*.

   > **Note**
   >
   > If you have enabled the Identity and Authentication Management (IAM) service, you are required to change the user password or navigated to the relevant external identity provider login pages before logging into the SLD. For more information, see *Identity and Authentication Management in SAP Business One* on SAP Help Portal (https://help.sap.com/viewer/p/SAP_BUSINESS_ONE_PRODUCT_LINE).
