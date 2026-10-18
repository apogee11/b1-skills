---
title: Weekly Tasks
source: pdf pp. 179-180, sec 11.1.2
summary: The weekly database tasks, checking database consistency (DBCC CHECKDB) and running UPDATE STATISTICS.
---

# Weekly Tasks

Perform the following tasks on at least a weekly basis:

- Checking database consistency
- Running the Update Statistics command

If the size of the SAP Business One database is large or your company has a large volume of daily or weekly transactions in SAP Business One, perform the previous tasks more often.

## Checking Database Consistency

A database consistency check performs a thorough check of the entire database. It examines all tables in the database to ensure that index and data pages are linked correctly and that indexes are in the correctly sorted order. A database consistency check also ensures that all pointers are consistent and that the data information on each page and page offset is reasonable.

Performing database consistency checks enables you to recognize problems early and prevent escalations and the possible loss of data.

When performing database consistency checks, ensure the following:

- Schedule consistency checks with the planning calendar.
- Run consistency checks outside of normal business hours, for example on the weekends.
- Do not schedule any other tasks at the same time as you run the consistency check.

> **Note**
>
> On the Microsoft SQL Server level, the SAP Business One database consistency check executes the `DBCC CHECKDB` command, which locks user tables, indexes, and system tables throughout the run.
>
> In addition, a database consistency check is an I/O intensive process. Therefore, you should not run checks during normal business operations, but at times when the system load is low.

You can use the remote support platform for SAP Business One to automatically perform database consistency checks as part of a defined backup strategy. For more information, see the online help for the remote support platform.

## Running the UPDATE STATISTICS Statement

The `UPDATE STATISTICS` statement defines the storage requirements of tables and indexes as well as the value distribution of columns, and stores this information in the database catalog.

The optimizer uses these values to determine the best strategy for executing SQL statements. Use the sp_updatestats procedure on all user-defined tables in the required database.

When the `UPDATE STATISTICS` statement is executed, the following information about the table is stored in the database catalog:

- Number of rows
- Number of pages used
- Size of indexes
- Value distribution within columns or indexes

You can use the remote support platform for SAP Business One to execute the `UPDATE STATISTICS` statement manually or as part of a scheduled task. You can also configure the remote support platform to create a job in the Microsoft SQL Server Agent, which updates statistics according to schedule.
