---
title: Working with Audit Logs
source: pdf pp. 95-97, sec 9.1.8
summary: What the Landscape Audit Logs and User Audit Logs areas of the SLD control center show, how to filter them, and how to clean up audit log records.
---

# Working with Audit Logs

The audit log records a time stamped list of all changes to system landscape directory resources, including the user who made the change and the request. It records the changes that have been made using the SLD control center.

The records are displayed in the *Landscape Audit Logs* and *User Audit Logs* areas.

To access the audit log in the SLD control center, choose the *Audit Logs* tab.

## Landscape Audit Logs

The *Landscape Audit Logs* area provides an overview of all changes to SLD resources, and displays the following information for each change:

- *Sequence Number*: Indicates the order in which the changes to SLD resources occurred.
- *Request*: The request sent to the SLD Service API. The request is either an SLD function or an SLD entity.
- *Resource*: The SLD resource that was changed and the operation that was performed.
- *User Name*: The name of the landscape administrator who made the change.
- *Changed On*: The date and time at which the SLD resource was changed.

You can use the controls and the top of the *Landscape Audit Logs* area to filter the entries displayed in the audit log. For example, you can filter by specific users, requests, and time periods.

To view detailed information about the properties that were changed for a specific resource, select the row for the corresponding request in the audit log. The *Audit Log Details* area displays the following information:

- *Property*: This column lists all the changed and unchanged properties for the selected resource.
- *Previous Value*: The value of the property before the change occurred.
- *New Value*: The updated value of the property after the changed occurred.

## User Audit Logs

The *User Audit Logs* area provides an overview of all changes made to users managed in SLD, in a readable, tabular format, and displays the following information for each change:

- *Source Address*: It is the SLD address from where the user has logged in.
- *Event Type*: It states the action performed by the user. For example, add user.
- *Resource*: The description of the event.
- *User Name:* The name of the landscape administrator who made the change.
- *Changed On:* The date and time at which the SLD resource was changed.

You can use the controls at the top of the *User Audit Logs* area to filter the entries by specific users and time periods to display them in the user audit log. For example, you can filter by specific users and time periods.

## Cleaning Up Audit Logs

Failing to delete audit log records can cause the SLD database to become relatively large, which may result in errors during the upgrade of the SLD. The cleanup audit log function allows you to clean up your audit logs.

**Procedure**

To clean up audit log records of changes to system landscape directory resources, perform the following:

1. In the SLD control center, choose the *Audit Logs* tab.
2. Choose the *Clean Up* button.
3. In the *Clean Up Audit Log* window, in the *To Date* field, select the date up to which you want to delete your audit logs.
4. Choose the *Clean Up* button, and then choose *Yes* in the *Confirmation* window.
