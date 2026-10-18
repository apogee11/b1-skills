---
title: Preventing Audit Log Tampering in Database
source: pdf pp. 237-238, sec 12.7.2
summary: Where SAP Business One audit log tables live in the B1LOGGING database and which dedicated users (LOG_WRITER, LOG_CLEANER) protect them from tampering.
---

# Preventing Audit Log Tampering in Database

SAP Business One audit log tables are stored in the `B1LOGGING` database.

<!-- table: t237-01 -->
| Audit Log Table | Audit Log Table Name | Synonym | Remarks |
|---|---|---|---|
| Common audit log table | SBOCOMMON_<common_ID> | SBOCOMMON.SAULG | <Common_ID> is an internal ID managed by SAP Business One System Landscape Directory (SLD). |
| Company audit log table | <company_database>_<company_ID> | <company_database>.CAULG | <Company_ID> is an internal ID managed by SAP Business One System Landscape Directory (SLD). |

To prevent audit logs being tampered with in database, the following users are created exclusively for the specific operations in the `B1LOGGING` database:

- The user `LOG_WRITER` is created exclusively for writing audit logs into audit log tables.
- The user `LOG_CLEANER` is created exclusively for cleaning audit logs from audit log tables (log retention).

> **Note**
>
> All the other SAP Business One database users (except for the database administrator) have no permission to access the `B1LOGGING` database.

- To access the audit logs, see [Database Access Control for Audit Logs](audit-log-reader-role.md) [page 238].
