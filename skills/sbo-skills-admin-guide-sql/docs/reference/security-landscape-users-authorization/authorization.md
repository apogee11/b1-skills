---
title: Authorization
source: pdf pp. 216-216, sec 12.3
summary: How SAP Business One authorizations work and the difference between regular users and superusers.
---

# Authorization

Authorizations allow users to view, create, and update documents that you assign to them, according to data ownership definitions. By default, a new user has no authorizations. Each user can have only one manager who assigns permissions.

You can define users as either regular users or superusers.

- Regular Users:
  - Can perform certain actions, for example, award discounts, change prices, or access confidential accounts, with the proper authorizations.
  - Cannot assign authorizations to other users.
- Superusers:
  - Have full and unrestricted authorization to access users in the system, apart from to their own logins.
  - Automatically have full authorization to access all functions in the system.
  - Can define authorizations and permissions for other users.

> **Note**
>
> For security reasons, we recommend that you create specific regular user accounts, which are only assigned the necessary authorizations to perform daily administration actions instead of superusers.

For more information about SAP Business One user authorization, see the SAP Business One online help.
