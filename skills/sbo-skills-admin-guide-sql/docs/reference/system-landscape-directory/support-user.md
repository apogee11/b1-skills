---
title: Activating the Support User
source: pdf pp. 99-100, sec 9.1.11
summary: How to activate the Support user from the SLD control center, the 4-hour session timeout, and the alternative activation through the Remote Support Platform.
---

# Activating the Support User

**Context**

As of 10.0 FP 2502, you can activate the `Support` user directly from the System Landscape Directory (SLD) control center.

> **Note**
>
> As of 10.0 FP 2502, the session timeout for the `Support` user is standardized to 4 hours, regardless of whether it is activated from the SLD control center or the Remote Support Platform (RSP).

**Procedure**

1. Log in to the SLD control center.
2. On the *DB Instances and Companies* tab, select one or more companies and choose *Activate Support User*.
3. In the *Activate Support User* window, read the disclaimer and choose *Activate*.

**Results**

- In the *Companies* table on the *DB Instances and Companies* tab, the *Support User Status / Remaining Session Time* for the selected companies is set to *Active / 3 Hours 59 Minutes*. Every time the page is refreshed, the remaining time is updated. When the countdown reaches 4 hours, the `Support` user status is automatically changed to *Inactive*.
- You can log in to the SAP Business One client and Web client with the *Support* user account. The session timeout for the `Support` user is 4 hours.

> **Note**
>
> The option to activate the Support User via System Status Report (SSR) upload from the Remote Support Platform (RSP) remains available. If you prefer this method, ensure that you have upgraded to the latest RSP release (RSP PL 19 or higher) to use this feature.
>
> For more information about the compatibility of Support user activation based on various combinations of RSP and SAP Business One versions, see SAP Note 3569124 (https://me.sap.com/notes/3569124).
