---
title: SBO Mailer
source: pdf pp. 102-105, sec 9.2.2*, 9.2.2.1*, 9.2.2.1.1*
summary: What the job service and SBO Mailer do, and how to configure SBO Mailer (SMTP settings, authentication type, starting the connection, enabling the mailer per company).
---

# SBO Mailer

## Job Service

The job service manages the following settings on the server side:

- SBO Mailer settings
- Alert and scheduling settings

## SBO Mailer

This optional service enables you to send emails from SAP Business One.

## Configuring SBO Mailer

The process of configuring the SBO Mailer is comprised of the following steps:

1. Define the mail settings and connect to the SMTP server from the SAP Business One Job Service Web page.
2. Enable the mailer service from the SAP Business One client or from the SLD control center.

> **Note**
>
> The SBO Mailer configuration Web page does not provide access to the SBO Mailer email signature settings.
>
> To access these settings, from the SAP Business One *Main Menu*, choose *Administration* > *System Initialization* > *Email Settings*.

> **Note**
>
> As of 10.0 FP 2508, a new authentication method *OAuth 2.0 for Microsoft 365* is available for use with the SBO Mailer. If you intend to choose this authentication method, make sure you have completed the following prerequisties before configuring the SBO Mailer:
>
> 1. [Registering an Application on Microsoft Entra ID](mailer-microsoft-entra-and-exchange.md#registering-an-application-on-microsoft-entra-id) [page 105]
> 2. [Registering the Service Principal in Exchange Server](mailer-microsoft-entra-and-exchange.md#registering-the-service-principal-in-exchange-server) [page 110]

**Procedure**

1. In a Web browser, navigate to the following URL: `https://<Server Address>:<Port>/job` Alternatively, on the *Services* tab in the system landscape directory, you can click the *Job Service* link to access the settings.

   > **Note**
   >
   > - If you use a proxy for your Internet connection, you must add the full hostname or IP address of any Web server (for example, SLD) to the proxy exception list of your Web browser; in other words, do not use a proxy for these addresses.
   > - The URL of the service is case-sensitive.
   > - On the *Services* tab in the System Landscape Directory, make sure that the job service is already bound to a database instance which is registered in the SLD control center.

2. If you have not logged in to the SLD service, in the login page, enter the landscape administrator name (`B1SiteUser`) and password, and then choose *Log In*.

   > **Note**
   >
   > The landscape administrator name is case-sensitive.

3. On the *Mailer Settings* tab, specify the following mandatory mail settings information and choose *Save*:
   - *SMTP Server*: Name or IP address of your outgoing mail server.
   - *SMTP Port*: Port number for the SMTP server.

     > **Note**
     >
     > If your SMTP server does not allow anonymous connection, specify a user name and password; otherwise, select the *Anonymous* checkbox.

     > **Note**
     >
     > As of SAP Business One 10.0 SP 2311, SEE4C is no longer supported as an SMTP client. If you have set SEE4C as the SMTP client, Microsoft.Net will replace SEE4C after the upgrade with SAP Business One 10.0 SP 2311. You need to adjust your SMTP configuration after the upgrade. For more information, see SAP Note 3367990 (https://me.sap.com/notes/3367990).

   - *Authentication Type*: Select the authentication method you want to use: *Basic Authentication* or *OAuth 2.0 for Microsoft 365*, and enter the required *User Name* and *Password*.

     > **Note**
     >
     > You can only enter an email address as a user name.
     >
     > When configuring *OAuth 2.0 for Microsoft 365*, ensure that the email address specified here matches the email address used during the service principal registration in the Exchange Server. For more information about the service principal registration in Exchange Server, see [Registering the Service Principal in Exchange Server](mailer-microsoft-entra-and-exchange.md#registering-the-service-principal-in-exchange-server) [page 110].

   - *Client ID* – Paste the value of th e*Application (client) ID* that you registered and recorded on Microsoft Entra ID previously. This field is only displayed when you select *OAuth 2.0 for Microsoft 365*.
   - *Client Secret* – Paste the value of the client secret that you added and recorded on Microsoft Entra ID previously. This field is only displayed when you select *OAuth 2.0 for Microsoft 365*.
   - In the *Language* dropdown list, select the language for email text.
   - If your SMTP server requires TLS encryption, make sure the *Use TLS Encryption* checkbox is selected.
   - If you are using a right-to-left language, select the *Right-to-Left* checkbox.
   - To include the subject line in the body of the message, select the *Include Subject in Message Body* checkbox.
4. To connect to the SMTP server, choose *Start*. The status changes to `RUNNING` and the button changes to *Stop*.

   > **Note**
   >
   > To change the SMTP server, or to add or remove companies, you must first stop the connection by choosing *Stop*.

5. Log in to the SAP Business One client as a superuser or a power user and do the following to enable mailing services for databases.
   1. Select the database for which you want to enable the mailing service.
   2. On the *Service* tab of the *General Settings* window (*Main Menu* > *Administration* > *System Initialization* > *General Settings*), select the *Enable Mailer* checkbox.

   Alternatively, you can also enable mailing services for databases from the System Landscape Directory control center as follows:

   1. Log in to the SLD control center.
   2. On the *DB Instances and Companies* tab, in the *Companies* area, select the databases on which you intend to enable the mailing services and choose *Enable Company Specific Mailer Configuration*.

**Result**

You can now proceed to set up an attachment folder. For more information, see [Setting Up an Attachment Folder](mailer-attachments-and-troubleshooting.md#setting-up-an-attachment-folder) [page 111].
