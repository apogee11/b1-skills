# Database Authentication

## [Securing the Database Administrator (sa) Account](sa-account-password.md)
Use when: setting a strong `sa` password; TLS between SQL Server and the SAP Business One components; strong password rules; creating a substitute superuser for `sa`.
Terms: `sa`, database administrator, strong password, Windows Authentication, TLS, Transport Layer Security, dictionary attack, SQL Server Management Studio, *Security*, *Logins*
Not here: setting up an alternative admin user (sec 12.10.2.1) → [sql-server-security](../sql-server-security/sql-server-security.md#setting-up-an-alternative-admin-user)

## [Managing Data Encryption in Microsoft SQL Server (Enabling TDE)](transparent-data-encryption.md)
Use when: enabling Transparent Data Encryption on a company database; backing up the TDE certificate and master key; verifying encryption.
Terms: TDE, Transparent Data Encryption, DEK, Database Encryption Key, `CREATE MASTER KEY`, `CREATE CERTIFICATE`, `MyServerCert`, `ALTER DATABASE ... SET ENCRYPTION ON`, `sys.databases`, `is_master_key_encrypted_by_server`, SQL Server 2017
Sections: [Enabling TDE](transparent-data-encryption.md#enabling-transparent-data-encryption)
Not here: removing TDE → [removing-transparent-data-encryption](removing-transparent-data-encryption.md); SAP Business One encryption keys and secrets (sec 12.5.2, 12.6) → [data-encryption](../network-storage-and-keys-security/data-encryption.md), [managing-keys-passwords-and-secrets](../network-storage-and-keys-security/managing-keys-passwords-and-secrets.md)

## [Removing Transparent Data Encryption](removing-transparent-data-encryption.md)
Use when: disabling TDE on a database; what to back up and consider before deleting the certificate or master key; temporary TDE removal.
Terms: `ALTER DATABASE ... SET ENCRYPTION OFF`, `DROP DATABASE ENCRYPTION KEY`, `DROP CERTIFICATE`, `DROP MASTER KEY`, `MyServerCert`, TDE scanning, off-hours, full database backup
Not here: enabling TDE → [transparent-data-encryption](transparent-data-encryption.md)

## [Preventing Audit Log Tampering in Database](preventing-audit-log-tampering.md)
Use when: where the SAP Business One audit log tables are stored; which database users write and clean audit logs; who may access the `B1LOGGING` database.
Terms: `B1LOGGING`, `SBOCOMMON_<common_ID>`, `<company_database>_<company_ID>`, `SBOCOMMON.SAULG`, `CAULG`, `SAULG`, `LOG_WRITER`, `LOG_CLEANER`, synonym
Not here: SLD audit logs (sec 9.1.8) → [audit-logs](../system-landscape-directory/audit-logs.md); security-relevant logging overview (sec 12.13) → [security-relevant-logging-and-tracing](../data-protection-logging-and-recommendations/security-relevant-logging-and-tracing.md)

## [Database Access Control for Audit Logs (reader role and user)](audit-log-reader-role.md)
Use when: creating a read-only role and login that can read the audit log tables in SQL Server.
Terms: audit log reader, `AUDIT_LOG_READER_ROLE`, `AUDIT_LOG_READER`, `CREATE ROLE`, `GRANT SELECT ON OBJECT::dbo.CAULG`, `dbo.SAULG`, `B1LOGGING`
Sections: [Creating the role](audit-log-reader-role.md#creating-the-audit-log-reader-role) · [Creating the reader and granting the role](audit-log-reader-role.md#creating-the-audit-log-reader-and-grant-the-role)
Not here: querying the tables as the reader → [checking-audit-logs](checking-audit-logs.md); tracing the reader's logins → [tracing-audit-log-reader-activity](tracing-audit-log-reader-activity.md)

## [Checking Audit Logs of SAP Business One](checking-audit-logs.md)
Use when: querying the company or `SBO-COMMON` audit log tables with the reader account.
Terms: `select * from [B1LOGGING].dbo.<company_database>_<company_ID>`, `select * from <company_database>.dbo.CAULG`, `[SBO-COMMON].dbo.SAULG`, `SBOCOMMON_<common_ID>`, `SBODEMOUS`
Not here: viewing the SQL Server audit of the reader's own activity (sec 12.7.3.4.4) → [tracing-audit-log-reader-activity](tracing-audit-log-reader-activity.md#reading-the-audit-logs-and-activities); SLD audit logs → [audit-logs](../system-landscape-directory/audit-logs.md)

## [Tracing the Audit Log Reader's Login and Reading Activities](tracing-audit-log-reader-activity.md)
Use when: auditing who logged in as the audit log reader and which audit tables they read; SQL Server audit, server audit specification and database audit specification.
Terms: *New Audit*, *Audit Properties*, `server_principal_name`, *Server Audit Specifications*, `SUCCESSFUL_LOGIN_GROUP`, `FAILED_LOGIN_GROUP`, *Database Audit Specifications*, *Enable Audit*, *View Audit Logs*, `C:\temp\`
Sections: [Creating the audit](tracing-audit-log-reader-activity.md#creating-the-audit) · [Server audit specification](tracing-audit-log-reader-activity.md#creating-server-audit-specification) · [Database audit specification](tracing-audit-log-reader-activity.md#creating-database-audit-specification) · [Reading the audit logs](tracing-audit-log-reader-activity.md#reading-the-audit-logs-and-activities)
Not here: reading the SAP Business One audit tables themselves → [checking-audit-logs](checking-audit-logs.md)

## [Retention Period of Audit Logs in the Database](audit-log-retention.md)
Use when: how long audit log entries are kept; changing the retention value.
Terms: `63072000000`, 730 days, `604800000`, 1 week, `[SBO-COMMON].dbo."SCCFG"`, retention period
