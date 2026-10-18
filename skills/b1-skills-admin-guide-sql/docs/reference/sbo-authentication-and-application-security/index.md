# SAP Business One Authentication and Application Security

## [Restricting Database Access](restricting-database-access.md)
Use when: why end users never see database credentials; how the SLD supplies credentials to the client, DI API and services; security workflow.
Terms: database credentials, System Landscape Directory, SLD database, landscape administrator authentication, database user per company, DI-API
Not here: database users and levels set per company → [changing-security-levels](changing-security-levels.md); the `sa` password (sec 12.7) → [sa-account-password](../database-authentication/sa-account-password.md)

## [Changing Security Levels](changing-security-levels.md)
Use when: choosing how SAP Business One connects to the database per company; automatically created database users; scheduling regular password changes of those users.
Terms: `https://<Server Address>:<Port>/ControlCenter`, `B1SiteUser`, *DB Instances and Companies*, *Edit Company*, *Use Specified Database User*, *Use Specified Database User for Each Business One User*, `SBOCOMMON`, read-only database user, password change schedule
Not here: reading audit logs of the database (sec 12.7.3) → [database-authentication](../database-authentication/index.md); read-only user for queries → [queries-read-only-authorization](queries-read-only-authorization.md)

## [B1_SHR Folder Permissions](b1-shr-folder-permissions.md)
Use when: operating system permissions on the B1_SHR folder with the client setup files.
Terms: `B1_SHR`, `SBO_SHR`, Power User, User, Modify, Write, Read and execute, List folder contents
Not here: installing the client from B1_SHR → [installing-client-components](../installing-client-components/index.md)

## [Queries: Granting Read-Only Authorization for Query Results](queries-read-only-authorization.md)
Use when: users running queries that should only read; non-superusers and the non-select SQL permission.
Terms: query wizard, query generator, `Execute Non-select SQL Statement`, *General Authorizations*, *Read-Only DB User*, `SELECT`, No authorization
Sections: [Granting read-only authorization](queries-read-only-authorization.md#granting-read-only-authorization-for-query-results)
Not here: authorizations in general (sec 12.3) → [authorization](../security-landscape-users-authorization/authorization.md)

## [Add-On Access Protection and Dashboards](add-on-access-and-dashboards-security.md)
Use when: how add-ons are identified; scanning partner dashboard content.
Terms: MD5, digital signature, message-digest algorithm, add-on, dashboards, cockpit, virus scan
Sections: [Add-on access protection](add-on-access-and-dashboards-security.md#add-on-access-protection) · [Dashboards](add-on-access-and-dashboards-security.md#dashboards)
Not here: configuring the client and assigning add-ons (sec 9.5, 9.6) → [client-configuration-and-add-ons](../client-configuration-and-add-ons/assigning-add-ons.md)

## [Browser Access: Secure Configuration](browser-access-security.md)
Use when: operating system users for the browser access backend GUI server; sharing the GUI server between customers.
Terms: backend GUI server, browser access, operating system user, SAP Note 2876621
Not here: installing the browser access service → [browser-access-service](../installing-server-components/browser-access-service.md)

## [Security Information for Integration Solutions](integration-solutions-security.md)
Use when: security of DATEV-HR, Mobile, SAP Customer Checkout and RFQ solutions; HTTPS for the integration framework; mobile user checks and license control.
Terms: DATEV-HR, DATEV eG, Mobile solution, mobile device ID, MAC address, HTTPS, SAP Customer Checkout, RFQ, online quotation, license control, firewall
Sections: [DATEV-HR](integration-solutions-security.md#security-aspects-related-to-the-datev-hr-solution) · [Mobile](integration-solutions-security.md#security-aspects-related-to-the-mobile-solution) · [HTTPS](integration-solutions-security.md#using-https) · [License control](integration-solutions-security.md#license-control) · [SAP Customer Checkout](integration-solutions-security.md#security-aspects-related-to-the-integration-with-sap-customer-checkout) · [RFQ](integration-solutions-security.md#security-aspects-related-to-the-rfq-scenario-with-online-quotation)
Not here: integration framework maintenance, monitoring and security after installation (sec 9.7) → [maintenance-monitoring-and-security](../integration-framework-post-install/maintenance-monitoring-and-security.md); communication channels (sec 12.4) → [communication-channels](../network-storage-and-keys-security/communication-channels.md)

## [Electronic Document Service: Encryption and Key Rotation](electronic-document-service-security.md)
Use when: how EDS encrypts data; scheduled or manual key rotation; checking the rotation result.
Terms: EDS, `EDSRotateKeyTask`, `EDSTool.exe RotateKey`, `SAPB1EDFBackend`, Task Scheduler, every 30 days at 02:00, symmetric encryption
Sections: [Encryption](electronic-document-service-security.md#encryption) · [Scheduled rotation](electronic-document-service-security.md#scheduled-periodic-key-rotation) · [Manual rotation](electronic-document-service-security.md#manual-key-rotation) · [Verification](electronic-document-service-security.md#verification-of-key-rotation-results)
Not here: installing EDS → [electronic-document-service](../installing-server-components/electronic-document-service.md); keys and secrets in general (sec 12.5, 12.6) → [managing-keys-passwords-and-secrets](../network-storage-and-keys-security/managing-keys-passwords-and-secrets.md)

## [Electronic File Mapping Transformation Service: Encryption and Key Rotation](efm-transformation-service-security.md)
Use when: how the Electronic File Mapping Transformation Service encrypts data; scheduled or manual key rotation; verification.
Terms: `EFMRotateKeyTask`, `SAPB1EFMTService`, Task Scheduler, `Get-ScheduledTask`, every thirty days at 03:00, symmetric encryption
Sections: [Encryption](efm-transformation-service-security.md#encryption) · [Scheduled rotation](efm-transformation-service-security.md#scheduled-periodic-key-rotation) · [Manual rotation](efm-transformation-service-security.md#manual-key-rotation) · [Verification](efm-transformation-service-security.md#verification-of-key-rotation-results)
Not here: installing the service → [electronic-file-mapping-transformation-service](../installing-server-components/electronic-file-mapping-transformation-service.md)
