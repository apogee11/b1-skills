---
title: Restoring Databases
source: pdf pp. 187-194, sec 11.1.5
summary: Restore strategy and checklist, saving the current transaction log, and restoring backups, application folders and transaction logs with or without the msdb history.
---

# Restoring Databases

- [Restore Checklist](#restore-checklist)
- [Saving Current Transaction Logs](#saving-current-transaction-logs)
- [Restoring Backup Files and Application Folders](#restoring-backup-files-and-application-folders)
- [Restoring Data When msdb Is Available](#restoring-data-when-msdb-is-available)
- [Restoring Data When msdb Is Unavailable](#restoring-data-when-msdb-is-unavailable)
- [Troubleshooting Restore](#troubleshooting-restore)

If a failure damages the system, restoring the database restores the integrity of the data in most cases. Ideally, the downtime of the system will be minimal, and no data should be lost. Develop a restore strategy that considers the maximum downtime allowed for your system, and estimate how much time you need to react to a system failure. Analyze the problem and take appropriate measures.

You may be required to change hardware or reinstall the operating system before restoring your database.

Ensure that an employee familiar with the restore procedures is available at all times. Testing of the restore procedures improves the chances of a successful and fast recovery of your data. We recommend doing test backups and test restores at regular intervals.

Restore the database in the following situations:

- Hardware failure
- Migration to a new hardware
- Logical errors
- Virus
- Testing

## Restore Checklist

The steps below comprise a general procedure for restoring data. You may find that you do not need to perform each step for your particular case.

1. Analyze the problem.
2. If possible, save the current active transaction log.

> **Note**
>
> If the database fails, but Microsoft SQL Server is still available, the transaction log contains data that has not been saved yet. You can save it only if the following are not damaged:
>
> - Hard disk on which the transaction log is saved
> - Hard disk on which the executable files are located

If you cannot save the transaction log, you can only restore the changes that occurred after the backup of the last transaction log.

3. Use the necessary hardware.
4. Configure your database server.
5. Restore your last full backup.
6. Restore the transaction log.
7. Test all executed measures.
8. Release to productive operation.

## Saving Current Transaction Logs

### Context

> **Caution**
>
> Before you start the restore process, verify that the installed service pack has not changed since the time of the backup.

### Procedure

1. Insert a new tape and, to open the SQL Server Management Studio, in Windows, choose *Start* > *All Programs* > *Microsoft SQL Server <Version>* > *SQL Server Management Studio*.
2. Select the relevant database, right-click it, and choose the *New Query* menu.
3. In the *Query* window, run the following command:

```sql
BACKUP LOG <sid> TO <tape> WITH NO_TRUNCATE, FORMAT
```

   Where:

   `<sid>` is name of the database, for example, `sbodemo_us`.

   `<tape>` is your backup tape name (case sensitive).

4. After saving the transaction log file, you can change any damaged hardware and, if necessary, reinstall your operating system and your Microsoft SQL Server database, as described in [Installing SAP Business One](../installing-server-components/server-components-installation.md#installing-sap-business-one) [page 32].
5. Restore your last full database backup.

   The database is now in the same condition as it was when the backup was carried out. After you restore the transaction logs, finished transactions are applied to the database again.

6. Perform a rollforward until the end of the transaction log.

   The database is now in the same condition as it was at the time of the last transaction log backup. Since this condition is not consistent, perform a rollback for all unfinished transactions.

   The <msdb> database stores the history of backups and of restore operations in the backup set and backup file of the tables. If the msdb database is available, the recovery is based on the saved history in msdb. For more information, see [Restoring Data When msdb Is Available](#restoring-data-when-msdb-is-available) [page 190].

   If the system database msdb is not available, you have to restore it and reconstruct the history. For more information, see [Restoring Data When msdb Is Unavailable](#restoring-data-when-msdb-is-unavailable) [page 191].

> **Recommendation**
>
> To ensure a successful restore operation, you can test the restore process against a test database. If you use the transaction log file, we recommend testing all procedures thoroughly.

## Restoring Backup Files and Application Folders

### Context

To restore backup files and application folders, perform the following procedures:

### Procedure

1. Extract the files from the backup archive, including:
   - Database backup .zip file
   - Application folder backup archive files
2. Extract the application folder backup archive files to separate folders.
3. Manually copy the extracted files back to the original shared folders.

## Restoring Data When msdb Is Available

### Context

This procedure provides instructions for restoring your database when the database msdb is available. When you use the history function, the last backups are selected automatically.

### Procedure

1. To enable the system to restore the database, close SAP Business One.
2. To open the SQL Server Management Studio, in Windows, choose *Start* > *All Programs* > *Microsoft SQL Server <Version>* > *SQL Server Management Studio*.
3. Right-click the required database and choose *Tasks* > *Restore* > *Database*.

   A list of performed backups appears. The last full backup and the subsequent transaction log backups are selected automatically.

4. In the *Restore Database* window, on the *Options* tab, select the following options:
   - *Overwrite over existing database* — To overwrite the existing database, select this option.
   - *Preserve the replication settings*
   - *Prompt before restoring each backup* — Prompt the user before restoring each backup to prevent a user from inadvertently restoring a backup.
   - *Restrict access to the restored database*
   - *Restore database file as* — In the *Restore As* column, change the path name if you are restoring the database on a different server.

> **Note**
>
> To specify the .bu file, do the following:
>
> 1. In the *Microsoft SQL Server Management Studio* window, on the *General* tab, select the *From Device* radio button and choose *Browse*.
> 2. In the *Specify Backup* window, choose *Add*.
> 3. In the *Locate Backup File <computer_name>* window, from the *Files of Type* dropdown list, select *All Files*.
> 4. In the hierarchy tree, specify the .bu file that you want to restore.
> 5. Choose *OK*.

5. To confirm, choose *OK*.

   The system starts the database restore process.

6. Wait until the following message is displayed:

```text
Restore of Database <databasename> completed successfully.
```

### Results

SQL Server copies the data from the backups, restoring the database and creating all dependent files.

## Restoring Data When msdb Is Unavailable

### Context

This section provides instructions for restoring your database when the history in the database <msdb> is not available, for example, after you reinstall SQL Server. For this procedure, you need your last full backup and all subsequent backups of the transaction log.

### Procedure

1. To enable the system to restore the database, close SAP Business One.
2. To open the SQL Server Management Studio, in Windows, choose *Start* > *All Programs* > *Microsoft SQL Server <Version>* > *SQL Server Management Studio*.
3. Create a new database as follows:
   1. Right-click the *Databases* folder and choose *Tasks* > *Restore* > *Database*. The *Restore Database* window appears.
   2. Specify a name for your new database (the name of your company in SAP Business One).
4. Right-click the new database and choose *Tasks* > *Restore* > *Database*.
5. Select the *Restore: From Device* option and choose *Browse*.
6. In the *Specify Backup* window, choose *Add*.
7. In the *Locate Backup File* window, locate and select the file containing your last full backup.

   Choose *OK*.

8. In the *Specify Backup* window that opens, locate, and select the file containing your last full backup.

   Choose *OK*.

9. In the *Restore Database* window, select the required back sets and on the *Options* tab make the following settings:
   - Select the *Overwrite the existing database* checkbox.
   - Under the *Restore As* column, change the path, if necessary, for example, if you are restoring the database on a different server where the path name does not exist.
   - In the *Recovery completion state* area, select the *Leave database non-operational but able to restore additional transaction logs* option. Choose *OK*. The system starts restoring the database.

10. Wait for the following message:

```text
Restore of Database <sid> completed successfully.
```

### Next Steps

Continue to the procedure for restoring transaction logs.

### Restoring Transaction Logs

#### Procedure

1. Right-click the database you want to restore and choose *Task* > *Restore* > *Transaction Log*.
2. Select the *Restore: From Device* option and choose *Browse*.
3. In the *Specify Backup* window, choose *Add*.
4. In the *Locate Backup File* window that appears, locate, and select the file containing your last full backup.

   Choose *OK*, and do the same in the *Specify Backup* window that appears.

5. In the *Restore Database* window, on the *Options* tab, make the following settings:
   - Select *Overwrite the existing database*.
   - Under the *Restore As* column, change the path, if necessary, for example, if you are restoring the database on a different server where the path name does not exist.
   - In the *Recovery completion state* area, select the *Leave database not operational but able to restore additional transaction logs* option.
   - Choose *OK*.

   The system starts to restore the database.

6. Repeat this procedure for all transaction logs.

#### Next Steps

When you reach the last transaction log, in the *Recovery Completion State* pane, select the *Leave database operational option*. No additional transaction logs can be restored.

## Troubleshooting Restore

The only way to verify that you can do so is to regularly restore backups using the same medium that you would use in disaster recovery.

> **Recommendation**
>
> At regular intervals, perform the procedures that would take place in case of a disaster, including the restore process of full and transaction log backups.
