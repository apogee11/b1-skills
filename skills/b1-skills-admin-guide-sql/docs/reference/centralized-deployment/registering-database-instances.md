---
title: Registering Database Instances on the Landscape Server
source: pdf pp. 174-175, sec 10.4
summary: Registering database servers in the SLD control center so that companies appear on the application's logon screen.
---

# Registering Database Instances on the Landscape Server

**Context**

For companies to appear on the application's logon screen, you must register the database instances on the landscape server using the System Landscape Directory.

**Procedure**

1. To access the SLD service, in a Web browser, navigate to the following URL:

   ```text
   https://<Server Address>:<Port>/ControlCenter
   ```

2. On the logon page, enter the landscape administrator name and password, and then choose *Log In*.

   > **Note**
   >
   > The landscape administrator name is case sensitive.

3. On the *DB Instances and Companies* tab, in the *DB Instances* area, choose *Add*.
4. In the *Add Server* window, specify the following:
   - *Server Name* — Enter the fully qualified domain name (FQDN) of the database server that you want to add.

     > **Caution**
     >
     > Ensure that the name of the server on which you installed Microsoft SQL Server does not contain any special characters, such as: &, <, >, ”, or ’.

   - *Database User Name*: Enter the user name of the administrator account for the database.
   - *Database User Password*: Enter the password of the administrator account for the database.
5. To add the database server, choose *OK*.
