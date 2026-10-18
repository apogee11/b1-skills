---
title: Enabling the Remember Sign-In Credentials Option
source: pdf pp. 87-88, sec 9.1.3
summary: How to let users skip entering IDP credentials on each SAP Business One client sign-in, with prerequisites and risks.
---

# Enabling the Remember Sign-In Credentials Option

**Prerequisites**

- You have activated only one identity provider in the SLD control center.
- You have bound the IDP users to SAP Business One company users in the SLD control center.

> **Note**
>
> - When this setting is enabled, only one SAP Business One client can be opened at a time per user session.
> - Selecting this option poses a risk, especially on public computers, as it may allow unauthorized access to SAP Business One company data. Please make sure that you understand the risks before enabling this setting.

**Context**

With the *Remember Sign-In Credentials* functionality enabled, you can log on to the SAP Business One client without the need to provide your credentials every time you access it.

**Procedure**

1. Log in to the SLD control center.
2. On the *Security* tab, in the *Remember Sign-In Credentials* area, select the checkbox *Remember user's IDP sign-in credentials for automatic sign-in to the SAP Business One client*.
3. Choose *Update*.

**Results**

Users will not be prompted to enter their credentials during the next sign-in process when accessing the SAP Business One client.

> **Note**
>
> - The validity period of the *Remember Sign-In Credentials* feature depends on the configurations on the related external IDP sites.
> - If you deselect the checkbox, users will be required to enter their credentials each time they access the SAP Business One client.
