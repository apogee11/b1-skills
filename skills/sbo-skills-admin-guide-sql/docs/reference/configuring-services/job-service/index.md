# Job Service

## [SBO Mailer](sbo-mailer.md)
Use when: what the job service manages; configuring the SBO Mailer SMTP settings; choosing Basic Authentication or OAuth 2.0 for Microsoft 365; starting the mailer; enabling the mailer per company; email signature settings.
Terms: Job Service, `https://<Server Address>:<Port>/job`, `B1SiteUser`, *Mailer Settings*, *SMTP Server*, *SMTP Port*, *Authentication Type*, *Basic Authentication*, *OAuth 2.0 for Microsoft 365*, *Client ID*, *Client Secret*, *Anonymous*, *Use TLS Encryption*, *Right-to-Left*, *Include Subject in Message Body*, *Start*, `RUNNING`, *Enable Company Specific Mailer Configuration*, *Email Settings*, SEE4C, SAP Note 3367990, 10.0 FP 2508
Not here: alert service → [alert-settings](alert-settings.md); Microsoft 365 document export → [additional-services](../additional-services.md)

## [Microsoft Entra ID application and Exchange service principal](mailer-microsoft-entra-and-exchange.md)
Use when: registering an application on Microsoft Entra ID for OAuth 2.0 for Microsoft 365; registering the service principal in Exchange; SMTP AUTH; Send As permission.
Terms: Azure Portal, *App registrations*, *New registration*, *Application (client) ID*, *Directory (tenant) ID*, *Object ID*, *Certificates & secrets*, *New client secret*, *API permissions*, *Office 365 Exchange Online*, *SMTP SendAsApp*, *Grant admin consent*, `Install-Module -Name ExchangeOnlineManagement`, `Connect-ExchangeOnline`, `New-ServicePrincipal`, `Add-MailboxPermission`, FullAccess, Send As
Sections: [Entra ID](mailer-microsoft-entra-and-exchange.md#registering-an-application-on-microsoft-entra-id) · [Exchange](mailer-microsoft-entra-and-exchange.md#registering-the-service-principal-in-exchange-server)

## [SBO Mailer: attachment folder and troubleshooting](mailer-attachments-and-troubleshooting.md)
Use when: local or shared attachment folder for the mailer; granting the mailer machine access; test connection; mail not sending.
Terms: attachment folder, `\\<server address>\folder\shared_folder`, *Sharing*, `sqlserver$`, *Read/Write*, *Test Connection*, *Anonymous Access*, *Mail Settings*, SBO-Mailer service restart
Sections: [Attachment folder](mailer-attachments-and-troubleshooting.md#setting-up-an-attachment-folder) · [Troubleshooting](mailer-attachments-and-troubleshooting.md#troubleshooting)
Not here: pictures folder → [pictures-folder](../pictures-folder.md)

## [Alert Settings](alert-settings.md)
Use when: starting the alert service; enabling alert and scheduling services per company; monitoring alert task statuses; task execution timeout.
Terms: *Alert Settings* tab, *Start*, `RUNNING`, *Enable Alert*, *DB Instances and Companies*, *Task List* tab, *Execution Timeout*, `1440` minutes, *Waiting*, *Running*, *Interrupted*, *Error*, *Company Name*, *Time of Adding to List*, *Status Change Time*, `https://<Server Address>:<Port>/job`, Service Layer 10.0 PL02
Not here: workflow service → [additional-services](../additional-services.md#sap-business-one-workflow)

## [Refreshing Encryption](refreshing-encryption.md)
Use when: manually refreshing all encryption keys from the Job Service page; static and dynamic keys.
Terms: *Refresh Encryption*, encryption keys, encrypted fields, dynamic keys, static keys, `https://<Server Address>:<Port>/job`
Not here: enabling or exporting dynamic keys → [dynamic-keys](../../system-landscape-directory/dynamic-keys.md)
