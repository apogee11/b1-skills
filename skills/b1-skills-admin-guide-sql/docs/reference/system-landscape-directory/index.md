# System Landscape Directory

## [SLD Overview and Logging In](sld-overview-and-login.md)
Use when: post-installation activities; what the SLD control center is used for; logging in to the SLD control center; enabling IAM after installation; proxy exception for the SLD.
Terms: SLD control center, `https://<Server Address>:<Port>/ControlCenter`, case-sensitive URL, default port `40000`, landscape administrator, `B1SiteUser`, Log In, Identity and Authentication Management (IAM), proxy exception list, centralized deployment, `Support` user, license key, assign add-ons
Not here: SLD Agent installation → [sld-agent-wizard-installation](../centralized-deployment/sld-agent-wizard-installation.md); SLD in the install wizard → [server-components-installation](../installing-server-components/server-components-installation.md)

## [Adding Services in the SLD](adding-services.md)
Use when: a service is missing from the *Services* tab or was deleted; the Service URL for each service type; Version and Certificate Expiration Date columns.
Terms: *Services* tab, *Add Service*, Service type, Service name, Service Unit, Service URL, `/LicenseControlCenter`, `/job`, `dispatcher`, `/workflow`, `/ServiceLayerController`, `/mobileservice`, `/WebhookMessenger`, `/ms365i`, high availability, Virtual IP Address, Version column, Certificate Expiration Date column, 30 days, 10.0 FP 2602
Not here: installing the services → [installing-server-components](../installing-server-components/index.md)

## [Enabling the Remember Sign-In Credentials Option](remember-sign-in-credentials.md)
Use when: letting users skip IDP credentials at each client sign-in; its prerequisites and risks.
Terms: Remember Sign-In Credentials, *Security* tab, Update, one active identity provider, bound IDP users, one client at a time per user session, public computers

## [Configuring the Authentication Service](authentication-service.md)
Use when: changing the SLD or authentication server address and port; the address after upgrading to 10.0 FP 2208 or higher.
Terms: SAP Business One Authentication Service, *Security* tab, *Edit*, *Update Address*, authentication server address, nginx reverse proxy, updated nginx file, 10.0 FP 2208, restart all component services
Not here: external address mapping → [external-address-mapping](external-address-mapping.md); authentication service security settings → [managing-keys-passwords-and-secrets](../network-storage-and-keys-security/managing-keys-passwords-and-secrets.md)

## [Managing Dynamic Keys for Company Databases](dynamic-keys.md)
Use when: enabling, disabling, exporting or importing dynamic encryption keys for company databases; moving a company schema to another SLD; lost dynamic key.
Terms: dynamic key, Enable Dynamic Key Generation, Disable Dynamic Key Generation, Enable Dynamic Key, Disable Dynamic Key, Dynamic Key Management, Dynamic Key Status, *DB Instances and Companies* tab, *Dynamic Keys* table, Export, Import, Path to Dynamic Key File, p12, 128 KB, password policy, `SLDDATA`, `<installation folder>\SAP Business One ServerTools\System Landscape Directory\incoming`, Refreshing Encryption
Sections: [Enabling](dynamic-keys.md#enabling-dynamic-keys) · [Disabling](dynamic-keys.md#disabling-dynamic-keys) · [Exporting](dynamic-keys.md#exporting-dynamic-keys) · [Importing](dynamic-keys.md#importing-dynamic-keys)
Not here: encryption and key security → [data-encryption](../network-storage-and-keys-security/data-encryption.md), [managing-keys-passwords-and-secrets](../network-storage-and-keys-security/managing-keys-passwords-and-secrets.md); refreshing encryption → [refreshing-encryption](../configuring-services/job-service/refreshing-encryption.md)

## [Mapping External Addresses to Internal Addresses](external-address-mapping.md)
Use when: giving components an external access URL; external address of the SLD and authentication server; services to restart afterwards.
Terms: *External Address Mapping* tab, Register, *Edit External Address*, External URL, `<protocol>://<Path>:<Port>`, `https://testsap:8100/dispatcher`, reverse proxy mode, NAT/PAT mode, nginx, Extension Manager URL, `/ExtensionManager`, SAP Business One Browser Access Server Gatekeeper, `WebClientStartup.ps1 "restart"`, `C:\Program Files\SAP\SAP Business One Web`
Not here: enabling external access, reverse proxy and NAT setup → [choosing-a-method](../demo-databases-and-external-access/external-access/choosing-a-method.md)

## [Disabling Certificate Expiry Warnings](certificate-expiry-warnings.md)
Use when: turning off the certificate expiry warning shown on opening the SLD control center.
Terms: *Global Settings* tab, Certificate Expiry Warnings, Disable Certificate Expiry Warnings, 30 days, 10.0 FP 2602
Not here: where the expiration date is shown → [adding-services](adding-services.md)

## [Working with Audit Logs](audit-logs.md)
Use when: reviewing changes to SLD resources or users; filtering audit logs; cleaning up audit logs when the SLD database is large or the SLD upgrade errors.
Terms: *Audit Logs* tab, Landscape Audit Logs, User Audit Logs, Sequence Number, Request, Resource, User Name, Changed On, Audit Log Details, Property, Previous Value, New Value, Source Address, Event Type, Clean Up, Clean Up Audit Log, To Date
Not here: database audit logs → [preventing-audit-log-tampering](../database-authentication/preventing-audit-log-tampering.md), [security-relevant-logging-and-tracing](../data-protection-logging-and-recommendations/security-relevant-logging-and-tracing.md)

## [Managing Identity Providers](identity-providers.md)
Use when: registered identity providers; adding an external OIDC provider; activating or deleting an identity provider; Active Directory Domain Services after upgrade.
Terms: *Identity Providers* tab, Identity and Authentication Management (IAM), SAP Business One authentication server, Active Directory Domain Services, OpenID Connect (OIDC), external IDP, Activate, Inactive, Windows domain single sign-on (SSO), 10.0 FP 2208
Not here: security of identity management → [user-types](../security-landscape-users-authorization/user-types.md), [restricting-database-access](../sbo-authentication-and-application-security/restricting-database-access.md); managing the IDP users → [managing-users](managing-users.md)

## [Managing Users in the SLD](managing-users.md)
Use when: the three types of IDP users; binding IDP users to company users; `B1SiteUser` status and password.
Terms: *Users* tab, `B1SiteUser`, landscape admin user, SAP Business One authentication server user, Microsoft Windows domain user, external identity provider users, bind to company users, 10.0 FP 2208
Not here: registering identity providers → [identity-providers](identity-providers.md)

## [Activating the Support User](support-user.md)
Use when: activating the `Support` user from the SLD control center; its 4-hour session timeout; activating through the Remote Support Platform instead.
Terms: `Support` user, Activate Support User, *DB Instances and Companies* tab, Support User Status / Remaining Session Time, Active / 3 Hours 59 Minutes, 4 hours, Remote Support Platform (RSP), System Status Report (SSR), RSP PL 19, SAP Note 3569124, 10.0 FP 2502
