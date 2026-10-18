---
title: Managing Users in the SLD
source: pdf pp. 98-99, sec 9.1.10
summary: The three types of identity provider users in the SLD control center (authentication server, Windows domain, other external IDP users) and how they bind to company users.
---

# Managing Users in the SLD

In the SLD control center, you can manage the users of identity providers and bind them to SAP Business One company users.

This section introduces the 3 types of IDP users. For more information about how to manage the users, see Managing Identity Provider Users (https://help.sap.com/viewer/548d6202b2b6491b824a488cfc447343/10.0_SP_2608/en-US/973ad6e09282487bafc4fc53f5d2e6a6.html) in *Identity and Authentication Management in SAP Business One*.

**SAP Business One Authentication Server User**

`B1SiteUser` is the super user of SAP Business One authentication server. It was created during the installation of the SLD. When you log in to the SLD, you can find `B1SiteUser` on the *Users* tab.

`B1SiteUser` is a default landscape admin user. You can change the status and password of `B1SiteUser`.

You can also add other users for SAP Business One authentication server in the SLD control center.

**Microsoft Windows Domain User**

You can add Windows domain users if the Active Directory Domain Services is available on the *Identity Providers* tab.

You can change the statuses of Windows domain users or remove domain users from the table.

> **Note**
>
> If you upgrade SAP Business One from a lower version to 10.0 FP 2208 or higher, and in the lower version, you have bound Windows domain users to SAP Business One company users, after the updates, you can find the bound users on the *Users* tab.

**Other External Identity Provider Users**

You can add other external identity provider users if you have registered the relevant identity providers on the *Identity Providers* tab.

- You can change the status or remove external IDP users from the table.

> **Note**
>
> Once you bind IDP users to SAP Business One company users, you cannot log in to SAP Business One with the company user accounts.
