---
title: Regular Tasks
source: pdf pp. 180-183, sec 11.1.3
summary: Regular database tasks, verifying the server is running, verifying backups, checking databases, shrinking transaction logs with BACKUP LOG and DBCC SHRINKFILE, and monitoring disk space.
---

# Regular Tasks

Performing scheduled tasks is essential for ensuring database availability and minimizing the risk of data loss. Perform the following tasks on a regular basis, as determined by your database size and transaction volumes:

- Verify that the database server is running
- Verify that the backups run successfully
- Check the database
- Shrink the transaction log
- Monitor disk space

## Verifying Database Servers Are Running

You must complete this task every morning. SAP Business One clients cannot work if the database server is not running.

### Procedure

Run the SAP Business One client and log in to your database server. If you can log in, the database server is running.

Alternatively, you can use the System Status Report of the remote support platform for SAP Business One to automate the database verification process.

## Verifying Backups

### Context

Backups of your database are essential for recovering the SAP Business One system in case of failure. Use this procedure to verify that previous backups ran successfully.

Alternatively, you can use the remote support platform for SAP Business One to automate the backup verification process as part of a defined backup strategy.

### Procedure

1. To open the SQL Server Management Studio, in Windows, choose *Start* > *All Programs* > *Microsoft SQL Server <Version>* > *SQL Server Management Studio*.
2. Select the *Management* folder and check the SQL server logs.
3. Search for the last backup message.
4. Verify that the backup ran successfully and that the date fits the scheduled settings.

   The following is an example of a successful backup message:

   ```text
   "Database backed up. Database: myDB, creation date(time): 2005/12/21(10:57:16),
   pages dumped: 502701, first LSN: 37211:18:108, last LSN: 37211:91:1, number of
   dump devices: 1, device information: (FILE=1, TYPE=DISK: {'E:\temp\bck\myDB'}).
   This is an informational message only. No user action is required."
   ```

## Checking Databases

The SQL Server database uses disk space to store the database data files and the daily transaction log files. If you do not establish a schedule for the backup of the transaction log, the log file can grow too large, causing a decline in system performance. Ultimately, this can stop the database system.

The transaction log should not occupy more than 60–70% of the total available disk size. If it regularly exceeds this level between subsequent backups, you must save the transaction log more frequently. In SQL Server Management Studio, you can determine whether the data file and transaction log file are set to grow automatically.

In addition, check the utilization of table space and the content of error logs on a regular basis.

### Procedure

- To check the size of the data file and the transaction log file, do the following:
  1. To open the SQL Server Management Studio, in Windows, choose *Start* > *All Programs* > *Microsoft SQL Server <Version>* > *SQL Server Management Studio*.
  2. Select the database for which you want to check the transaction log size.
  3. Right-click the selected database and choose *Reports* > *Standard Reports* > *Disk Usage*. In the right pane, you can see the report.
  4. Verify that there is enough free space, based on your organization’s needs, for both the data file and the transaction log.
- To set grow options for database files, do the following:
  1. Open the SQL Server Management Studio and select a database.
  2. Right-click the selected database and choose *Properties*.
  3. In the *Properties* window, from the menu on the left, choose *Files*. The database files appear in the right pane.
  4. In the *Autogrowth* field, set a value according to your organization’s needs.
- To check error logs, do the following:
  1. Open the SQL Server Management Studio.
  2. Select the *Management* folder and check the *SQL Server Logs* folder.
  3. Check for error messages and verify that no problems have occurred.

## Shrinking Transaction Logs

### Context

Shrinking the transaction log file frees up disk space and minimizes the risk of data loss. Shrinking the transaction log does not reduce the size of a physical log file. It removes enough inactive virtual logs to reduce the log file to the requested size. Use this procedure to shrink the transaction first virtually and then physically.

In addition, you can use the remote support platform for SAP Business One to shrink the transaction log manually or as part of a scheduled task. You can also configure the remote support platform to create a job in the Microsoft SQL Server Agent, which shrinks the transaction log according to schedule.

### Procedure

1. To open the SQL Server Management Studio, in Windows, choose *Start* > *All Programs* > *Microsoft SQL Server <Version>* > *SQL Server Management Studio*.
2. Select the required system database.
3. Right-click the selected database and choose *New Query*.

   The right pane displays the *Query* window.

4. In the *Query* window, enter the following command:

   ```sql
   BACKUP LOG <sid> WITH NO_LOG
   ```

   Where:

   `<sid>` is name of the database, for example, `sbodemo_us`.

   Right-click anywhere on the query tab and choose *Execute*.

   This statement reduces the size of the logical log. It removes the inactive part of the log, without making a backup copy, and truncates the log.

   Specifying a backup device is unnecessary because the log backup is not saved.

   After you back up the log using `NO_LOG`, the changes recorded in the log are not recoverable. For recovery purposes, execute a manual backup of your database. For more information, see SAP Note 557412.

5. To reduce the size of the physical log file, enter the following command:

   ```sql
   DBCC SHRINKFILE (<name_logfile>, <size>)
   ```

   `<name_logfile>` is the logical name of the shrunk file, for example, `sbodemo_us_log`.

   `<size>` is the required size for the file, in megabytes, expressed as an integer. If the size is not specified, `DBCC SHRINKFILE` reduces the size to the default file size, for example, 10 MB.

   Right-click anywhere on the query tab and choose *Execute*.

> **Note**
>
> In SQL Server, a `DBCC SHRINKDATABASE` or `DBCC SHRINKFILE` operation attempts to shrink the physical log file to the requested size (subject to rounding).

## Monitoring Disk Space

We recommend that you regularly check the amount of free space available on the disk. You can use the System Status Report of the remote support platform for SAP Business One to automate the process of monitoring the amount of free disk space.
