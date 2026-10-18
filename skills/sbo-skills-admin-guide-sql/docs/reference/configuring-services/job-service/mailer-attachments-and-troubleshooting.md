---
title: "SBO Mailer: attachment folder and troubleshooting"
source: pdf pp. 111-112, sec 9.2.2.1.2, 9.2.2.1.3
summary: Setting up a local or shared attachment folder for the SBO Mailer, and troubleshooting tips for the mail services.
---

# SBO Mailer: attachment folder and troubleshooting

- [Setting Up an Attachment Folder](#setting-up-an-attachment-folder)
- [Troubleshooting](#troubleshooting)

## Setting Up an Attachment Folder

**Context**

If your attachment folder is stored on the same machine as the SBO Mailer, you can define a local path as an attachment folder from the *Administration* > *System Initialization* > *General Settings* > *Path* tab.

If your attachment folder is stored on a different machine, perform the following steps.

**Procedure**

1. Define a Web path (for example, `\\<server address>\folder\shared_folder`) as an attachment folder in the SAP Business One client (*Administration* > *System Initialization* > *General Settings* > *Path* tab).
2. Access the Windows machine where the shared folder is located, and grant full permissions to the machine on which your SBO Mailer is installed.
   1. Navigate to the shared folder.
   2. Right-click on the shared folder and choose *Properties* in the context menu.
   3. In the *Properties* window, choose the *Sharing* tab.
   4. In the *Network File and Folder Sharing* area, choose *Sharing...*.
   5. Enter the hostname of the machine where your SBO Mailer is installed, followed by the suffix `$`. For example, `sqlserver$`.
   6. Choose *Add*.
   7. Locate the machine's line in the list and grant *Read/Write* permission.
   8. Choose *Share*.

## Troubleshooting

The following troubleshooting information may be helpful when configuring the mail services:

- Ensure that you have already set up an email account for the SAP Business One users on your mail server.
- To verify the connection with the mail server, choose *Test Connection*.
- The mail service checks the connection with the specified mail server and email account and displays an appropriate message.
- If the SMTP server requires authentication, for example, if the SMTP server is configured to accept only logon-authenticated mails, you must not select the *Anonymous Access* option in the *Mail Settings* area.
- To check whether the connection to the SMTP server works, send a test email. If the connection fails, ensure that you have done the following:
  - Entered the correct name of your mail server
  - Entered the correct user ID and password
  - Restarted the SBO-Mailer service after changing any of the settings
