---
title: Microsoft Windows Domain Account Authentication Enablement
source: pdf pp. 213-215, sec 12.2.3.4
summary: Enabling single sign-on with Microsoft Windows domain accounts: registering the SPN, binding users, copying user mappings and enabling SSO in the SLD.
---

# Microsoft Windows Domain Account Authentication Enablement

SAP Business One supports single sign-on (SSO) functionality. You can bind an SAP Business One user account to a Microsoft Windows domain account.

After starting the SAP Business One client, you can start using the application without being prompted to enter your SAP Business One logon credentials.

To use the single sign-on function, you must complete the following steps:

1. Register a Service Principal Name (SPN).
2. Bind SAP Business One company users to Microsoft Windows accounts.
3. Enable the single sign-on function in the SLD.

## Registering the Service Principal Name

**Prerequisites**

You are a domain administrator or have been delegated the appropriate authority.

**Context**

To enable Windows domain single sign-on with SAP Business One, you must register a service principal name (SPN) for the SLD service. The SPN can be registered before or after you install the System Landscape Directory. Nevertheless, if you register the SPN after the installation, the domain user account used for installation must be used for SPN registration.

> **Recommendation**
>
> As this domain user is a service user that functions purely for the purpose of setting up single sign-on, we highly recommend that you create a new domain user and do not assign any additional privileges to the user other than the logon privilege. In addition, keep the user’s password unchanged after enabling single sign-on; otherwise, single sign-on may stop working.

**Procedure**

1. On a Windows computer, run the command prompt as an administrator.
2. Run the following `setspn` command: `setspn -U -A <SPN> <Domain User Name>`.

   An example of an SPN is `SLD/Domain.com`.

## Binding SAP Business One Users to Microsoft Windows Accounts

After you bind SAP Business One users to Microsoft Windows domain accounts, the users can Log in to SAP Business One without specifying their user credentials.

For more information about binding users, see Binding Users (https://help.sap.com/viewer/548d6202b2b6491b824a488cfc447343/10.0_SP_2608/en-US/a64c5f8a475843019bf51e594467bb65.html).

## Copying User Mappings Between Companies

You can copy user mappings between two companies provided that the same user exists in both companies. Each user is identified by the user code (not the user name).

Typical scenarios for this function are as follows:

- You have moved your company database from a test system to a productive system.
- You have moved your company database to another server.
- You have imported and renamed your company database (the old database also exists on the same server).

For more information about copying user mappings, see Copying User Mappings (https://help.sap.com/viewer/548d6202b2b6491b824a488cfc447343/10.0_SP_2608/en-US/433999951bc34b59a6c1378b3e95f8d8.html).

## Enabling Single Sign-On

To enable Single Sign-On, you must go to the SLD control center to activate the identity provider Active Directory Domain Services. For more information about activating IDPs, see Activating Identity Providers (https://help.sap.com/viewer/548d6202b2b6491b824a488cfc447343/10.0_SP_2608/en-US/b89fa071af854a9f904a83a819dce0e4.html).

After enabling SSO, the *Choose Company* window displays only the companies to which your Windows account is bound.

> **Caution**
>
> Enabling SSO in the SLD activates this functionality for all companies in the landscape.

**Result**

Each user must confirm the binding upon first logon. After confirmation, the user can log in to SAP Business One, using the bound Windows account.

> **Caution**
>
> The first time you single sign-on to SAP Business One using your domain user account, ensure you have logged in to the Windows system using the correct domain user name (case sensitive). If not, log out and then log in again using the correct user name; otherwise, single sign-on will not work.

> **Note**
>
> After activating one or more identity providers and binding users, only the bound IDP users, rather than the SAP Business One company user accounts, can log into SAP Business One. For more information about behavior changes after enabling identity providers, see Behavior Changes After Enabling Identity and Authentication Management (https://help.sap.com/viewer/548d6202b2b6491b824a488cfc447343/10.0_SP_2608/en-US/04257eefa3f8400981a007ee8f15f1ef.html).
