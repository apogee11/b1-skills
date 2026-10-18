---
title: Integration Framework-Related Information About Dashboard Widgets for the Cockpit
source: pdf pp. 157-158, sec 9.7.10
summary: Troubleshooting the Cockpit dashboard widgets with integration framework version 1 (401 and 404 errors, Adobe Flash Player requirement).
---

# Integration Framework-Related Information About Dashboard Widgets for the Cockpit

This information applies to integration framework version 1.

- If the B1i user password is not correct or licenses are not properly assigned to the user, Dashboard widgets display the `401 not authorized` error. In the integration framework, adjust the B1i user password in SLD. Ensure that licenses are correctly assigned. For more information, see the [Licensing](maintenance-monitoring-and-security.md#licensing) [page 149] section.
- If Dashboards have been activated, but not properly deployed in the integration framework, the `404 file not found` error mentioning `DASHBOARD` is displayed.

  Check that all services for the integration framework are running. Deactivate the Dashboard widgets, log off and logon again, and activate the Dashboard widgets.

- To support the display of dashboards, ensure that Adobe Flash Player 10.0 is installed on the client workstation.
- For information about creating dashboards, see *How to Develop Your Own Dashboards for SAP Business One* on SAP Help Portal (https://help.sap.com/viewer/p/SAP_BUSINESS_ONE_PRODUCT_LINE).
