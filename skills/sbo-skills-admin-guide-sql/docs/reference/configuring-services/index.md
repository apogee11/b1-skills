# Configuring Services

## [License Control Center](license-control-center.md)
Use when: first-time service configuration after installation; finding the hardware key; importing the license file; licensed users and inconsistent license allocations; 31 days without a license key; what changes the hardware key.
Terms: landscape administrator password, `https://<Server Address>:<Port>/LicenseControlCenter`, `https://<Virtual IP Address>:<port>/LicenseControlCenter`, hardware key, *License Service Information* tab, *Import License File*, *Browse*, *Licensed Users* tab, *Remove Inconsistent License Allocations*, port X and X+1, `40002`, `40003`, CORBA license server, firewall, license server
Not here: SLD control center login and services → [system-landscape-directory](../system-landscape-directory/index.md)

## [job-service/](job-service/index.md)
Use when: configuring the job service Web page `/job`: SBO Mailer, Microsoft Entra ID and Exchange for OAuth 2.0, mailer attachment folder, alert service, refreshing encryption keys.
Terms: Job Service, `https://<Server Address>:<Port>/job`, SBO Mailer, *Mailer Settings*, *Alert Settings*, *Task List*, *Refresh Encryption*, `B1SiteUser`, OAuth 2.0 for Microsoft 365, SMTP
Sections: [SBO Mailer](job-service/sbo-mailer.md) · [Entra ID and Exchange](job-service/mailer-microsoft-entra-and-exchange.md) · [Attachment folder](job-service/mailer-attachments-and-troubleshooting.md) · [Alert settings](job-service/alert-settings.md) · [Refreshing encryption](job-service/refreshing-encryption.md)

## [Additional Services](additional-services.md)
Use when: Microsoft 365 integration (OneDrive, SharePoint export); SBO DI Server; fax services; report scheduling by email; the workflow service.
Terms: Microsoft 365 Integration, OneDrive, SharePoint, SBO DI Server, special license, Microsoft Fax Services, Report Scheduling, Workflow, workflow process templates
Sections: [Microsoft 365](additional-services.md#microsoft-365-integration) · [SBO DI Server](additional-services.md#sbo-di-server) · [Fax](additional-services.md#fax-services) · [Report scheduling](additional-services.md#report-scheduling) · [Workflow](additional-services.md#sap-business-one-workflow)
Not here: Job Service alerts and mailer → [job-service/](job-service/index.md); installing the services → [installing-server-components](../installing-server-components/index.md)

## [Pictures Folder](pictures-folder.md)
Use when: showing company logos and pictures in the client; mounting the shared pictures folder on the SBO Mailer Linux server.
Terms: pictures folder, company logo, *Path* tab, *General Settings*, `BitmapPath`, `OADP`, `mount -t cifs`, `/mnt/sharedpicture`, `b1service0`, no underscores in mount point, shared folder
Not here: mailer attachment folder → [mailer-attachments-and-troubleshooting](job-service/mailer-attachments-and-troubleshooting.md)

## [Service Layer (post-installation)](service-layer-configuration.md)
Use when: starting to work with the Service Layer after installation; SQL privileges for the connection user.
Terms: `SBO-COMMON`, company database, same version, `SELECT`, `INSERT`, `DELETE`, `UPDATE`, `EXECUTE`, grantable, SAP MSSQL database user
Not here: installing the Service Layer and load balancer → [service-layer](../installing-server-components/service-layer.md)

## [web-client/](web-client/index.md)
Use when: setting the default browser for the Web client with Group Policy; enabling OpenTelemetry; analyzing and exporting traces, metrics and logs for performance issues.
Terms: Web client, default browser, Group Policy, OpenTelemetry, `PERF_ANA`, `OTEL_EXPORTER_PROTOCOL`, Grafana, Jaeger, Prometheus, Loki, `X-B1-CorrelationId`
Sections: [Default browser](web-client/default-browser-group-policy.md) · [OpenTelemetry setup](web-client/opentelemetry-setup.md) · [Performance issues](web-client/opentelemetry-performance-issues.md) · [Collecting and exporting](web-client/opentelemetry-collecting-and-exporting.md)
Not here: installing the Web client → [web-client](../installing-server-components/web-client.md)

## [Webhook Messenger (Post-Installation)](webhook-messenger-configuration.md)
Use when: what the Webhook Messenger service does; retries, timeouts and batching of webhook notifications; where its configuration is documented.
Terms: Webhook Messenger, webhook notifications, partners' webhooks, subscribed events, retries, timeouts, message batching, Web Messenger
Not here: installing the Webhook Messenger → [webhook-messenger](../installing-server-components/webhook-messenger.md)
