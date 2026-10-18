---
title: Changing Security Levels
source: pdf pp. 248-249, sec 12.8.2
summary: Setting the database access security level per company in the SLD, the automatically created database users, and scheduled password changes.
---

# Changing Security Levels

You can apply different security levels to database access through the SLD:

1. To access the SLD service, in a Web browser, navigate to the following URL:

   ```text
   https://<Server Address>:<Port>/ControlCenter
   ```

2. In the logon page, enter the landscape administrator name (`B1SiteUser`) and password, and then choose *Log In*.

   > **Note**
   >
   > The landscape administrator name is case sensitive.

3. On the *DB Instances and Companies* tab, select the appropriate server.
4. The companies that are registered on the server are displayed in the *Companies* area.
5. In the *Companies* area, select the company for which you want to define the security level and choose *Edit*.
6. In the *Edit Company* window, select one of the following options and choose *OK*:
   - *Use Specified Database User*: The system automatically generates a set of database users without administrator privileges. SAP Business One accesses the database using one of the database users, depending on the specific database transaction.
   - *Use Specified Database User for Each Business One User*: Most secure and recommended. The system automatically generates a set of database users without administrator privileges for each SAP Business One user. SAP Business One accesses the database using one of the database users, depending on the login SAP Business One user and the specific database transaction.
   - Whenever a new SAP Business One user is added, a set of corresponding database users is added.

   You do not have to manually create a read-only database user for queries.

   > **Note**
   >
   > The System Landscape Directory automatically creates the relevant database users for each company and system database `SBOCOMMON`.
   >
   > - These database users have the read-only or read-write authorizations only for the relevant company databases or the system database.
   > - The company database users do not have the authorization for the system database `SBOCOMMON`.
   >
   > But if you have selected one of the options in a lower version and you upgrade SAP Business One to version 10.0, the specific privileges for `SBOCOMMON` cannot be revoked automatically. For security reasons, we recommend that you delete the database user manually. Thus, the System Landscape Directory will create a new read-only database user.

   > **Caution**
   >
   > We do not recommend that you change the names or system privileges of the automatically created database users. However, if you have used some extensibilities (for example, user-defined query, DIAPI and transaction notification) to do queries across the databases in a lower version, you can manually grant additional privileges to the automatically created database users after upgrading SAP Business One to version 10.0. Make sure that only necessary privileges are assigned to the database users.

7. If you selected *Use Specified Database User* or *Use Specified Database User for Each Business One User*, you can configure the SLD service to automatically change the password of the automatically created database users on a regular basis, as follows:
   1. On the *Security Settings* tab, in the *Authentication* area, select the checkbox *Change Database User Password Every <Number> Days*.
   2. Enter the number of days between password resets.
   3. Choose *Update*.
