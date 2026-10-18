---
title: Uninstalling the Integration Framework
source: pdf pp. 67-68, sec 7.2
summary: Prerequisites and steps for uninstalling the integration framework with the Change SAP Business One Integration program.
---

# Uninstalling the Integration Framework

**Prerequisites**

- To disable further event creation for the company databases in SAP Business One, run the event sender setup and in step 4, deselect the company databases.
- You have administrative rights on the PC where you uninstall the integration framework.
- You have made a backup of the database of the integration framework.
- You have made a backup of the *B1iXcellerator* folder. To find the folder, select *IntegrationServer* > *Tomcat* > *webapps* > *B1iXcellerator*.

**Context**

To uninstall the integration framework, use the *Change SAP Business One Integration* program. With this program you can add or remove features, repair the installation or uninstall the integration framework.

**Procedure**

1. Choose *Start* > *All programs* > *Integration Framework for SAP Business One* > *Change SAP Business One Integration*.

    The *SAP Business One Integration Wizard Introduction* window opens.

2. In the *Maintenance Mode* window select *Uninstall Product* and choose *Next*.

    The system notifies you that it uninstalls the integration framework.

3. Choose *Uninstall*.

    The system uninstalls your installation.

4. To finish the procedure, choose *Done*.

**Results**

The program uninstalls the integration framework, but it does not remove the database. Remove it separately.
