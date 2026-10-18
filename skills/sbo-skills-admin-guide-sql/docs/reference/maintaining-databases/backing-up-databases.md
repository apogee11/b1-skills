---
title: Backing Up Databases
source: pdf pp. 184-187, sec 11.1.4
summary: Why and how to back up SAP Business One databases and subdirectories, backup strategies and types, and how to troubleshoot backups.
---

# Backing Up Databases

This section introduces backups and information about the necessity of a backup strategy. Databases are always at risk of damage, and it is vital to implement a security strategy.

To keep the risk of data loss low, ensure that you develop a backup strategy that suits your business and the requirements of your customers. An important factor to consider is the volume of data that you process each day. In case of data loss, you are required to retrieve this data manually, back to the time of your last backup.

With SAP Business One, we recommend backing up your application database regularly.

> **Caution**
>
> SAP Business One can save the configuration data only when you have written and read access to the user profile folder.

You can use the following characters for a company database name:

- A-Z
- a-z
- 0-9
- Underscore (_)

Note that spaces are not allowed. In addition, the database name must start with A-Z or a-z.

## Backup Strategies

To choose the appropriate backup-and-restore strategy, you need to identify the requirements for the availability of your data. Your overall backup strategy should define the type and frequency of backups and the nature and speed of the hardware.

Consider the complexity of each strategy. Full backups are easy to implement. If you are considering backing up your transaction log as well, test all backup-and-restore procedures intensively.

When choosing your backup strategy, you can use the following methods:

- Full Backup
  In Microsoft SQL Server, a full backup is a consistent copy of your database at a certain time. Since only used objects are saved, normally the copy is smaller than the original database. Full backups should be scheduled for a time when there is a low load on the database server.
- Differential Backup
  A differential backup is a backup of all data that has changed since the last full backup was performed. Compared with full backups, differential backups consume less time and disk space, but can result in a longer amount of time required to restore data.
- Transaction Log Backup
  The Transaction Log is a serial record of all the transactions that have been performed on the database since the transaction log was last backed up. With transaction log backups, you can recover the database to a specific point in time or to the point of failure.
  The transaction log grows over time. If the transaction log exceeds a certain size, it can cause problems in Microsoft SQL Server. To prevent those problems, we recommend doing regular backups of the transaction log, which truncates the transaction log.
- Backup of SAP Business One Subdirectories
  To avoid data loss, you must back up regularly the following subdirectories of SAP Business One:
  - `...\Program Files\SAP\SAP Business One\Attachments\`
  - `...\Program Files\SAP\SAP Business One\Bitmaps\`
  - `...\Program Files\SAP\SAP Business One\ExclDocs\`
  - `...\Program Files\SAP\SAP Business One\WordDocs\`

  These directories contain Microsoft Word and Microsoft Excel documents and bitmaps. To store the backed-up directories, you can use a file archiving application.

> **Recommendation**
>
> Test your backup and recovery procedures thoroughly. Testing helps to ensure that you have the required backups to recover from various failures, and that your procedures can be executed smoothly and quickly if a failure occurs.
>
> The frequency of the backups depends on the following factors:
>
> - Processed data volume
> - Customer requirements
> - Number of users
>
> Consider how much time you would need to invest in retrieving your data manually after a data loss. After installing or upgrading SAP Business One, perform a full backup of the `SBO_DB` database.

## Backup Types

You can back up your data using the backup functionality of remote support platform for SAP Business One or SQL Server Management Studio, using one of the backup types described below:

- Full Backup and Differential Backup and/or Transaction Log Backup Using the Remote Support Platform for SAP Business One
  This backup type saves backup data to a network folder. The setup is relatively simple, and you can configure the remote support platform to automatically perform scheduled backups according to a defined strategy. The remote support platform can also backup SAP Business One subdirectories.
- Full Backup Using Microsoft SQL Server Management Studio
  This backup type can save the backup data directly to tape. If you save the backups on disk, ensure the backup is copied to another medium, such as another hard disc, DVD, or tape.
  Do a manual backup of the files and directories of your hard disk.
- Full Backup and Transaction Log Backup Using Microsoft SQL Server Management Studio

> **Note**
>
> To use SQL Server Management Studio to perform transaction log backups, you should have already selected the Full recovery model option.

The advantage of this type of backup is that the monitoring is partly automated, and you can save the backups directly to a tape. You can also add alerts. Disadvantages include a relatively complicated setup and the need to manually back up the subdirectories of SAP Business One. However, SAP Business One does not fully support all the features available with SQL Server Management Studio; therefore, if you require support from SAP in the future, your database backup may not be fully compatible.

> **Note**
>
> - Full Recovery — You can perform accumulated backups and move back to a specific point in time.
> - Simple Recovery — You can back up only the whole database; after the restoration, the database goes back to exactly the same point at which it was backed up.

> **Example**
>
> The following table summarizes the main options for each backup type:

<!-- table: t186-01 -->
| Backup Type | Full Backup and Differential Backup and/or Transaction Log Backup | Full Backup | Full Backup and Transaction Log Backup |
|---|---|---|---|
| Tool | Remote support platform for SAP Business One | Microsoft SQL Server Management Studio | Microsoft SQL Server Management Studio |
| Recovery model | Full | Simple | Full |
| Installation effort | Low | Medium | High |
| Monitoring effort | Low | Medium | Medium |
| Backup destination | Disk or network share | Disk or tape | Disk or tape |
| Automatic file backup | Yes | Yes | No |
| Complexity | Low | Medium | High |

> **Note**
>
> SAP Business One Product Support only accepts backups on destination disks. If you back up on tape, you must first restore it from there, and back it up again, using a destination disk, prior to sending it to SAP Support.

## Troubleshooting Backups

**Context**

To ensure that your database backups are successful, check your server at regular intervals. Ensure that you have enough disk space on the server on which your database is stored. If you store your backup on another server, check that there is enough free space.

The basic checks include:

- Drive space
- Disk subsystem errors
- Tape drive errors
- Event Viewer
- Regular evaluation of your recovery and restore process

**Procedure**

1. To check the disk space, do the following:
   1. In the Microsoft Windows *My Computer* window, right-click *Hard Disk Drives* and choose *Properties*. The *Properties* window appears.
   2. Check the free space on your hard disk.
      The free space you need on your hard disk depends on the volume of data you process each day. Depending on the disk system and the tape drive, scan for disk errors at regular intervals. For more information, see your tape drive documentation.
2. To check whether errors occurred in the operating system or on the database server, do the following:
   1. In Windows, choose *Start* > *Control Panel* > *Administrative Tools* > *Event Viewer*.
      - Events that occur in the system are stored in three different logs. Within these logs, events are classified as Information, Warning, or Error.
      - Events that occur within the database server are stored in the *Application* folder. In the *Source* column of the application log, you can see the source application for a specific event.
   2. Double-click an event to display more information.
   3. In the Application Log, look for error events that may indicate backup failures.
      If you perform network backups, look for network errors in the System and Application logs.
