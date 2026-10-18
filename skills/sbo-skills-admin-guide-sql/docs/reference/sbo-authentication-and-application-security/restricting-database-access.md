---
title: Restricting Database Access
source: pdf pp. 247-247, sec 12.8*, 12.8.1
summary: How SAP Business One keeps database credentials in the SLD so end users cannot access company databases directly, and the resulting security workflow.
---

# Restricting Database Access

## SAP Business One Authentication and Authorization

SAP Business One has a mechanism to protect the database from easy changes through direct access.

The advantages of restricting access to the SAP Business One database are:

- End users are not exposed to database credentials and so cannot change the databases directly, which protects the databases from being changed or attacked.
- Database credentials are stored in the license server and end users can access the database only after the application performs a successful landscape administrator authentication through the System Landscape Directory.

## Restricting Database Access

SAP Business One has a mechanism to protect the database from easy changes through direct access.

The advantages of restricting access to the SAP Business One database are:

- End users are not exposed to database credentials and so cannot change the databases directly, which protects the databases from being changed or attacked.
- Database credentials are stored in the System Landscape Directory (SLD) database and end users can access the database only after the application performs a successful landscape administrator authentication through the System Landscape Directory.

The System Landscape Directory is the central repository for credentials information, including the database user ID and password (one for all SAP Business One users).

The database credentials are stored safely in the SLD database, with additional encryption.

The security workflow is as follows:

1. Database consumers, such as the SAP Business One client, DI-API, and Services, provide their SAP Business One credentials (SAP Business One user ID and password) to authenticate against the SLD.
2. Following successful authentication, the SLD supplies its credentials and SAP Business One uses them to connect.

For more information, see [Technical Landscape](../security-landscape-users-authorization/technical-landscape.md) [page 202].

> **Note**
>
> You can use the SLD service to create different database user accounts for each company database. After creating accounts, SAP Business One does not access company databases using the database administrator account. Instead, SAP Business One uses a different read-only account supplied by the SLD service to access each company database.
