---
title: Removing Transparent Data Encryption
source: pdf pp. 236-237, sec 12.7.1.2
summary: Prerequisites and the procedure to remove TDE from a SAP Business One database in Microsoft SQL Server (disable encryption, drop DEK, certificate and master key).
---

# Removing Transparent Data Encryption

**Prerequisites**

Once you decide to remove TDE from SQL Server databases, you must consider the following points as part of your pre-deletion plan.

- Make a backup of the master key and certificate and keep it in a safe place. If you need to restore the database in the future with its old backup files, you'll need these keys.
- If the certificate is shared by multiple databases and you only want to remove TDE from one database, don’t delete the certificate. If you want to clean up the full instance from TDE, you can proceed with the deletion.
- If you have a request to temporarily delete TDE, do not delete its master key and certificate. You can close TDE directly from the database and then open TDE by running an ALTER statement.
- If possible, reduce the size of database files by removing unwanted data to reduce TDE scanning time during removal.
- Before you do this, ensure to run a full database backup.
- Always perform this activity during off-hours because TDE deletion will start the scanning process on the back end, which will increase the load on the database system.

**Context**

The following example shows the decryption of the `SBODEMOUS` database using a certificate named `MyServerCert` that's installed on the server.

**Procedure**

1. Open the SQL Server Management Studio.
2. Select the *SBODEMOUS* database.
3. Disable TDE encryption for the `SBODEMOUS` database by executing the following statement:

   ```sql
   USE [SBODEMOUS]
   GO
   ALTER DATABASE [SBODEMOUS] SET ENCRYPTION OFF
   GO
   ```

4. Drop the DEK on the `SBODEMOUS` database by executing the following statement:

   ```sql
   USE [SBODEMOUS]
   GO
   DROP DATABASE ENCRYPTION KEY
   GO
   ```

5. Drop the certificate from the master database by executing the following statement:

   ```sql
   USE master
   GO
   DROP CERTIFICATE MyServerCert
   GO
   ```

6. Drop the master database key from the master database by executing the following statement:

   ```sql
   USE master
   GO
   DROP MASTER KEY
   GO
   ```

7. Restart the SQL Server service and check if the master database is unencrypted by executing the following statement:

   ```sql
   USE master
   GO
   SELECT name, is_master_key_encrypted_by_server FROM sys.databases;
   GO
   ```

   After executing the above statement, you can get the value `1` or `0`.

   `1` = Database has an encrypted master key,

   `0` = Database doesn't have an encrypted master key
