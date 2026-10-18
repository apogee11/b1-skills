---
title: User Types
source: pdf pp. 203-205, sec 12.2*, 12.2.1
summary: Tools for user management and the user types in SAP Business One (landscape administrators, SAP Business One users, company users, Windows domain users).
---

# User Types

## User Administration and Authentication

This section provides an overview of how SAP Business One supports an integrated approach to user management and authentication.

The table below shows the tools to use for user management and user administration with the SAP Business One.

User Management Tools

<!-- table: t203-01 -->
- **Tool**: System Landscape Directory
  - **Detailed Description**: The System Landscape Directory (SLD) control center is a central workplace where you perform various administrative tasks. For more information, see [Working with the System Landscape Directory](../system-landscape-directory/sld-overview-and-login.md#working-with-the-system-landscape-directory) [page 84].
  - **Prerequisites**: You have the account information for the landscape super user (`B1SiteUser`).
- **Tool**: SAP Business One Client
  - **Detailed Description**: The application executable. For more information, see [Client Components](../introduction-and-prerequisites/application-components.md#client-components) [page 25].
  - **Prerequisites**: You have the SAP Business One user account with the user related permissions.

## User Types

It is necessary to specify different security policies for different types of users. For example, your policy may specify that individual users who perform tasks interactively have to change their passwords on a regular basis, but not users who process job runs. Therefore, SAP classifies these types of users in the application as follows.

### SAP Business One Landscape Administrators

The landscape administrator (site user) is not a company user type that can log in to the SAP Business One client application, but serves as site-level authentication for performing the following activities:

- Creating new companies
- Installing or upgrading SAP Business One
- Configuring security settings in the SLD service
- Registering database instances in the SLD service

The landscape administrator account serves as site-level authentication for performing various administrative tasks, as listed in the table below:

<!-- table: t203-02 -->
<!-- table: t204-01 -->
<!-- table: t204-02 -->
<!-- table: t204-03 -->
<!-- table: t204-04 -->
<!-- table: t204-05 -->
- **Landscape Administrators**: `B1SiteUser`
  - **Function**:
    - Life cycle management: installation, upgrade, uninstallation
    - Configuring services installed on Windows (for example, Workflow service)
    - Company creation
- **Landscape Administrators**: All
  - **Function**:
    - All operations performed in the System Landscape Directory
    - Accessing and performing operations in Web-based service control centers (for example, job service)

### SAP Business One User

As of 10.0 FP 2208, SAP Business One supports the identity and authentication management (IAM) service. To enable the IAM service, you need to add identity provider users and bind identity provider users to SAP Business One company users.

When an identity provider user is added in the SLD control center, the default role of the IDP user is *SAP Business One User*.

> **Note**
>
> If you set an IDP user as *Landscape Administrator* in the SLD control center, the user is not *SAP Business One User*.
>
> You cannot bind a landscape administrator to an SAP Business One company user.

After binding an SAP Business One user to a company user, you can log in to the SAP Business One client with the SAP Business One user account.

For more information, see [Managing Users](../system-landscape-directory/managing-users.md) [page 98].

### SAP Business One Company User

**Superusers**

A superuser can access all windows and perform all functions in SAP Business One, as well as limiting the authorizations of users that are not superusers. When you create a company, some predefined superusers exist in the system. For more information about superusers, see [Standard Users](standard-users.md) [page 205].

**Regular Users**

You can define company regular users according to different business role requirements.

The responsibilities of a regular user are to perform the relevant business work in the SAP Business One application.

### Microsoft Windows Domain User

You can assign appropriate Microsoft Windows domain users as SAP Business One landscape administrators to perform administrative tasks that require fewer privileges in the System Landscape Directory. One landscape administrator can be bound with more than one Windows domain accounts.

You can also bind an SAP Business One company user account to a Microsoft Windows domain account. After starting the SAP Business One client, users can start using the application without being prompted to enter their SAP Business One logon credentials. One Windows domain account can be bound with more than one companies. But in one company, one Windows domain account can be bound with only one company user. For more information about the Microsoft Windows domain account authentication enablement, see [Microsoft Windows Domain Account Authentication Enablement](windows-domain-account-authentication.md) [page 213].
