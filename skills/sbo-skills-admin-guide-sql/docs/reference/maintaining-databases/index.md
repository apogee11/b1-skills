# Maintaining Databases

## [Starting and Stopping Database Services](starting-and-stopping-database-services.md)
Use when: chapter introduction to database maintenance; stopping or starting SQL Server before a full backup; the company list is empty at logon.
Terms: SQL Server Management Studio, *Object Explorer*, *Stop*, *Start*, empty company list, database services, user processes
Sections: [Database server administration](starting-and-stopping-database-services.md#database-server-administration) · [Procedure](starting-and-stopping-database-services.md#procedure)

## [Weekly Tasks](weekly-tasks.md)
Use when: scheduling the weekly database consistency check; running UPDATE STATISTICS.
Terms: `DBCC CHECKDB`, database consistency check, `UPDATE STATISTICS`, `sp_updatestats`, remote support platform, SQL Server Agent job, I/O intensive
Sections: [Checking Database Consistency](weekly-tasks.md#checking-database-consistency) · [UPDATE STATISTICS](weekly-tasks.md#running-the-update-statistics-statement)
Not here: the shorter "Checking Databases" (disk size, autogrowth, error logs) → [regular-tasks](regular-tasks.md#checking-databases)

## [Regular Tasks](regular-tasks.md)
Use when: the daily or regular checks: server running, backup succeeded, data and log file size, autogrowth, shrinking the transaction log, free disk space.
Terms: System Status Report, "Database backed up. Database:", *Management* folder, *SQL Server Logs*, *Disk Usage*, *Autogrowth*, `BACKUP LOG <sid> WITH NO_LOG`, `DBCC SHRINKFILE`, `DBCC SHRINKDATABASE`, transaction log 60-70% of disk, SAP Note 557412
Sections: [Server running](regular-tasks.md#verifying-database-servers-are-running) · [Verifying Backups](regular-tasks.md#verifying-backups) · [Checking Databases](regular-tasks.md#checking-databases) · [Shrinking Transaction Logs](regular-tasks.md#shrinking-transaction-logs) · [Disk space](regular-tasks.md#monitoring-disk-space)
Not here: the weekly consistency check → [weekly-tasks](weekly-tasks.md#checking-database-consistency); backup failures (disk, Event Viewer) → [backing-up-databases](backing-up-databases.md#troubleshooting-backups)

## [Backing Up Databases](backing-up-databases.md)
Use when: choosing a backup strategy or type; which SAP Business One folders to back up; allowed characters in a company database name; backup failures.
Terms: full backup, differential backup, transaction log backup, Full recovery, Simple recovery, remote support platform, `Attachments`, `Bitmaps`, `ExclDocs`, `WordDocs`, `SBO_DB`, tape, Event Viewer, disk space, Product Support accepts disk backups only
Sections: [Backup Strategies](backing-up-databases.md#backup-strategies) · [Backup Types](backing-up-databases.md#backup-types) · [Troubleshooting Backups](backing-up-databases.md#troubleshooting-backups)
Not here: checking that a backup ran → [regular-tasks](regular-tasks.md#verifying-backups); restoring → [restoring-databases](restoring-databases.md)

## [Restoring Databases](restoring-databases.md)
Use when: restoring after hardware failure, migration, logical errors or a virus; saving the active transaction log; restoring with or without msdb history; restoring transaction logs.
Terms: restore checklist, `BACKUP LOG <sid> TO <tape> WITH NO_TRUNCATE, FORMAT`, msdb, *Restore Database*, *Overwrite over existing database*, *Restore As*, *Leave database non-operational but able to restore additional transaction logs*, *Leave database operational*, `.bu` file, "Restore of Database <databasename> completed successfully", rollforward
Sections: [Restore Checklist](restoring-databases.md#restore-checklist) · [Saving transaction logs](restoring-databases.md#saving-current-transaction-logs) · [Backup files and application folders](restoring-databases.md#restoring-backup-files-and-application-folders) · [msdb available](restoring-databases.md#restoring-data-when-msdb-is-available) · [msdb unavailable](restoring-databases.md#restoring-data-when-msdb-is-unavailable) · [Troubleshooting Restore](restoring-databases.md#troubleshooting-restore)
Not here: restoring after a failed upgrade → [upgrading-databases-and-components](../upgrade-process/upgrading-databases-and-components.md#restoring-components-and-databases)

## [Data Transfer Workbench for SAP Business One](data-transfer-workbench.md)
Use when: migrating data from a legacy system; which steps the data migration process has.
Terms: Data Transfer Workbench, DTW, data file templates, legacy system, import wizard, map data
Not here: upgrading DTW with the server → [upgrading-databases-and-components](../upgrade-process/upgrading-databases-and-components.md)

## [Stored Procedures](stored-procedures.md)
Use when: checking whether a stored procedure belongs to SAP Business One; what must not be renamed or removed in `SBO-COMMON` or a company database.
Terms: `TmSp_`, `_TmSp_`, `SBO_SP_TransactionNotification`, `SBO_SP_PostTransactionNotice`, `OBSSp_`, `RGSp_`, `TmSp_AddSqlUser`, `TmSp_RestoreCompany`, `TmSp_CopyCompany`, `TmSp_Sales_An_`, `TmSp_Purch_An_`
Sections: [SBO-COMMON procedures](stored-procedures.md#sbo-common-database-procedures) · [Company database procedures](stored-procedures.md#company-database-procedures)
