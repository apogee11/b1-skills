---
title: Starting and Stopping Database Services
source: pdf pp. 178-179, sec 11*, 11.1*, 11.1.1
summary: Chapter introduction to database maintenance, the topics of database server administration, and how to stop and start the SQL Server database services in SQL Server Management Studio.
---

# Starting and Stopping Database Services

## Maintaining Databases

This section provides information about checking and maintaining your database system. Database activities depend on the nature of your organization's day-to-day work. There are many factors influencing system performance, such as disk space availability, the number of transactions occurring each day, and so on. It is essential to perform daily and regular checks to ensure the efficient operation of SAP Business One. System performance depends on the correct administration of the database.

This section also lists all the stored procedures quoted in the SAP Business One application.

## Database Server Administration

This section provides basic information about the SQL Server environment, the way a database management system stores and accesses the data, and the database administration tool. The information comprises the following topics:

- Starting and stopping database services
- Performing weekly tasks
- Performing regular tasks
- Performing backups
- Performing restoration

## Starting and Stopping Database Services

Occasionally, it is necessary to stop and start database services manually, for example, when you perform a complete backup of the database.

### Procedure

To stop database services:

1. Verify that no clients are logged on to SAP Business One.
2. To open the SQL Server Management Studio, in Windows, choose *Start* > *All Programs* > *Microsoft SQL Server <Version>* > *SQL Server Management Studio*.
3. In the *Object Explorer* window, right-click the database server on which your SAP Business One database is installed and choose *Stop*.

To start database services:

1. To open the SQL Server Management Studio, in Windows, choose *Start* > *All Programs* > *Microsoft SQL Server <Version>* > *SQL Server Management Studio*.
2. In the *Object Explorer* window, right-click the database server on which your SAP Business One database is installed and choose *Start*.

> **Note**
>
> If you are not able to log in to SAP Business One, and the dialog box for choosing a company contains an empty list, check whether Microsoft SQL Server is running.
>
> If you log off the Microsoft SQL Server services, all user processes are terminated, but the database services keep running.
