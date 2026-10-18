# Network, Storage and Keys Security

## [Communication Channels](communication-channels.md)
Use when: which components talk to which, and over which protocol (HTTPS, ODBC, JDBC, SAMBA, SMTP, Kerberos); recommended trusted environment; Citrix for outside access.
Terms: trusted environment, corporate LAN, firewall, Citrix, `b1_shf`, `B1_SHR`, SAMBA, ODBC, JDBC, HTTPS, SMTP, Kerberos, client agent, IM service, Job service, Web browser, domain controller
Not here: default ports → [default-ports](../appendix/default-ports.md); per-service TLS and ports → [secure-service-connections/](secure-service-connections/index.md)

## [secure-service-connections/](secure-service-connections/index.md)
Use when: default ports, TLS 1.2/1.3, cipher suites, certificate formats and config files for each service.
Terms: TLS cipher suites, `server.xml`, `ciphers`, `sslEnabledProtocols`, PKCS 12, JKS, X509, `httpd-b1s-lb.conf`, `SSLProtocol`, `SSLCipherSuite`, self-signed certificate
Sections: [Server Tools](secure-service-connections/server-tools.md) · [Service Layer](secure-service-connections/service-layer.md) · [Browser Access](secure-service-connections/browser-access.md) · [Reverse proxy](secure-service-connections/reverse-proxy.md) · [Integration framework](secure-service-connections/integration-framework.md) · [Web client](secure-service-connections/web-client.md)
Not here: installing these services → [installing-server-components](../installing-server-components/index.md); changing certificates after installation → [reconfiguring-components](../reconfiguring-the-system/reconfiguring-components.md)

## [Security Certificate Verification During SSL Communication](security-certificate-verification.md)
Use when: enabling certificate verification between SAP Business One services; hostname, Common Name and SAN requirements; behaviour before 10.0 SP 2411.
Terms: certificate verification, 10.0 SP 2411, SAP Note 3537539, Common Name, Subject Alternative Name, SAN, FQDN, hostname, 10.0 SP 2408
Not here: how each certificate is used → [security-certificate-usage](../appendix/security-certificate-usage.md); updating certificates → [managing-keys-passwords-and-secrets](managing-keys-passwords-and-secrets.md#managing-certificates-and-private-keys-used-in-https-connection)

## [SSL Encryption, Including Encrypting Communication with Databases](ssl-encryption.md)
Use when: securing server-to-client traffic with SSL; where to obtain certificates (third-party CA or own CA); encrypting SQL Server traffic to clients.
Terms: SSL encryption, Certificate Authority, CA root certificate, annual renewal, SQL SSL, Net-Library Encryption, Client Net-Libraries, database credentials exposed, network performance
Not here: HTTPS certificates for external access → [https-certificates](../demo-databases-and-external-access/external-access/https-certificates.md)

## [Data Storage Security](data-storage.md)
Use when: which database or folder holds SLD data, company data, system data, shared files and integration framework data; who is responsible for storage security.
Terms: SLD database, company database, `SBOCOMMON`, `B1_SHR`, `IFSERV`, shared folder, database provider, exporting the configuration file
Not here: shared folder permissions → [b1-shr-folder-permissions](../sbo-authentication-and-application-security/b1-shr-folder-permissions.md)

## [Data Encryption: SLD Dynamic Keys and Company Data](data-encryption.md)
Use when: creating, enabling or disabling dynamic keys for the SLD database; keystore backup; static keys by default; encrypting company data.
Terms: static keys, dynamic keys, `SLDInstallerTool.jar`, `-generateKey`, `-keyStorePath`, `-keyPassword`, `dynamic_key_control.bat -action on`, `-action off`, `c:\keystore.p12`, `SLDDATA`, `sapmachine_17`, keystore password
Sections: [Creating](data-encryption.md#creating-dynamic-keys) · [Enabling](data-encryption.md#enabling-dynamic-keys) · [Disabling](data-encryption.md#disabling-dynamic-keys) · [Company data](data-encryption.md#company-data-encryption)
Not here: dynamic keys for company databases in the SLD control center (enable, export, import) → [dynamic-keys](../system-landscape-directory/dynamic-keys.md); refreshing keys from the job service → [refreshing-encryption](../configuring-services/job-service/refreshing-encryption.md)

## [Backing Up and Restoring the License Assignment](license-assignment-backup.md)
Use when: backing up or restoring `B1Upf.xml` and the license files after a server crash.
Terms: `B1Upf.xml`, `B1LicenseFile-<installation number>.txt`, `License Service\webapps\lib`, license assignment, server tools stop and start
Not here: importing a license or removing inconsistent allocations → [license-control-center](../configuring-services/license-control-center.md)

## [Configuration Logs and User Settings](configuration-logs-and-user-settings.md)
Use when: where configuration changes are logged and which are not; per-user settings file; SLD log folder on Windows.
Terms: `%ProgramData%\SAP\SAP Business One\Log\SAP Business One\%USERNAME%\BusinessOne`, `xxx.pidxxxxx`, `b1-current-user.xml`, *Change Logs*, Event Viewer, `C:\ProgramData\SAP\SAP Business One\Log\SAP Business One ServerTools\System Landscape Directory`, data ownership, Read-Only DB users
Not here: all log file locations → [log-file-locations](../appendix/log-file-locations.md); SLD audit logs → [audit-logs](../system-landscape-directory/audit-logs.md); security-relevant logging → [security-relevant-logging-and-tracing](../data-protection-logging-and-recommendations/security-relevant-logging-and-tracing.md)

## [Managing Keys, Passwords, and Secrets](managing-keys-passwords-and-secrets.md)
Use when: where keys, HTTPS certificates and database passwords are managed: SLD, authentication service, company databases, integration framework.
Terms: dynamic key, *Components Wizard*, reconfiguration, certificate update, authentication service certificate, *DB Instances and Companies*, `bpc.jdbc_encpassword`, `xcellerator.cfg`, `IntegrationServer\Tomcat\webapps\B1iXcellerator\xcellerator.cfg`, Operations Guide Part Two
Sections: [SLD keys](managing-keys-passwords-and-secrets.md#managing-sld-data-encryption-keys) · [Company keys](managing-keys-passwords-and-secrets.md#managing-encryption-keys-for-company-data) · [Certificates](managing-keys-passwords-and-secrets.md#managing-certificates-and-private-keys-used-in-https-connection) · [SLD and authentication DB passwords](managing-keys-passwords-and-secrets.md#managing-database-passwords-for-sld-and-authentication-service) · [Company DB passwords](managing-keys-passwords-and-secrets.md#managing-database-passwords-for-companies) · [Integration framework DB password](managing-keys-passwords-and-secrets.md#managing-database-password-for-sap-business-one-integration-framework)
Not here: reconfiguring components → [reconfiguring-components](../reconfiguring-the-system/reconfiguring-components.md); the `sa` password → [sa-account-password](../database-authentication/sa-account-password.md)
