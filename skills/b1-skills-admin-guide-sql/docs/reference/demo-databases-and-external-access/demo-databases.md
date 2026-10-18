---
title: Deploying Demo Databases
source: pdf pp. 128-129, sec 9.3
summary: Prerequisites and the SQL Server Management Studio procedure for restoring the SAP Business One demo databases from the downloaded zip files.
---

# Deploying Demo Databases

Demonstration (Demo) databases include transactional data for your testing.

As of release 10.0 FP 2102, if you want to install demo databases, you need to download the demo database zip files from the SAP Help Portal and then manually import them to SAP Business One.

This section provides information about how to restore the demo databases in SAP Business One.

**Prerequisites**

- You have installed SAP Business One FP 2102 or higher.
- You have installed Microsoft SQL with a required revision. For more information about required MS SQL revisions, see SAP Note 928839 (https://me.sap.com/notes/928839).
- You have installed Microsoft SQL Management Studio.
- You have downloaded the demo databases as *.zip files from the SAP Help Portal at https://help.sap.com/doc/1660bf9ea40a46e1916736665d024dc6/10.0/en-US/B1_Demo_Databases_Overview.pdf and stored them in a local folder.
- On your PC, you have extracted the *.zip file.

**Procedure**

1. To enable the system to restore the database, close SAP Business One.
2. To open the SQL Server Management Studio, in Windows, choose *Start* > *All Programs* > *Microsoft SQL Server <Version>* > *SQL Management Studio*.
3. Create a new database as follows:
   1. Right-click the *Databases* folder and choose *Tasks* > *Restore* > *Database*. The *Restore Database* window appears.
   2. Specify a name for your new database (the name of your company in SAP Business One).
4. Right-click the new database and choose *Tasks* > *Restore* > *Database*.
5. Select the *Restore: From Device* option and choose *Browse*.
6. In the *Specify Backup* window, choose *Add*.
7. In the *Locate Backup File* window, locate and select the file containing the demo database. Choose *OK*.
8. In the *Specify Backup* window that opens, locate, and select the file containing your last full backup. Choose *OK*.
9. In the *Restore Database* window, select the required back sets and on the *Options* tab make the following settings:
   - Select the *Overwrite the existing database* checkbox.
   - Under the *Restore As* column, change the path, if necessary, for example, if you are restoring the database on a different server where the path name does not exist.
   - In the *Recovery completion state* area, select the *Leave database non-operational but able to restore additional transaction logs* option. Choose *OK*. The system starts restoring the database.
10. Wait for the following message: `Restore of Database <sid> completed successfully`.
