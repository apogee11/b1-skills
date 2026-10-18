---
title: Securing the Database Administrator (sa) Account
source: pdf pp. 231-232, sec 12.7*
summary: Database authentication basics for Microsoft SQL Server and how to set a strong password for the sa login in SQL Server Management Studio.
---

# Securing the Database Administrator (sa) Account

During the SAP Business One installation, only the secure connection between the Microsoft SQL Server database and the SAP Business One server, and client components using the Transport Layer Security (TLS) protocol is supported. For more information about configuring TLS for Microsoft SQL Server, please refer to the official Microsoft documentation.

The default user name of the database administrator is `sa` and it has full authorization. Therefore, you must assign a strong `sa` password, even on servers that are configured to require Microsoft Windows Authentication. This ensures that a blank or weak `sa` password is not exposed.

A strong password is the first step to securing your system. A password that can be easily guessed or compromised using a simple dictionary attack makes your system vulnerable. A strong password has the following characteristics:

- Contains alphabetic, numeric, and special characters
- Is at least seven characters in length
- Is NOT a common word or name
- Does NOT contain a name or user name
- Is significantly different from previous passwords

**Procedure**

To set the password for the `sa` logon, do the following:

1. Log in to the server as a domain or local Windows Administrator.
2. In Windows, choose *Start* > *All Programs* > *Microsoft SQL Server <Version>* > *SQL Server Management Studio*. Upon first logon, in the *Connect to Server* window, enter the server name (if required) and under *Authentication*, select *Windows Authentication*.

   > **Note**
   >
   > We recommend that you create another superuser account with the same authorization as the `sa` user.

3. In the *Object Explorer* window, under the SQL Server instance, expand *Security* > *Logins*. Right-click *sa* and choose *Properties*.
4. On the *General* page, enter and confirm the new password for the `sa` login.
5. Choose *OK* and close the *SQL Server Management Studio* window.

> **Caution**
>
> To prevent dictionary attacks, create a substitute user for `sa` that can take daily responsibility for the SQL Server database assessment. For more information, see [Setting Up an Alternative Admin User](../sql-server-security/sql-server-security.md#setting-up-an-alternative-admin-user) [page 258].
