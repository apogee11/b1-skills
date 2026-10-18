---
title: Managing Keys, Passwords, and Secrets
source: pdf pp. 230-231, sec 12.6
summary: Where the keys, certificates and database passwords of SLD, authentication service, companies and the integration framework are managed.
---

# Managing Keys, Passwords, and Secrets

This section provides an overview of the management of keys, passwords, and secrets for different components of SAP Business One.

## Managing SLD Data Encryption Keys

You can encrypt data in your System Landscape Directory using a dynamic key. For more information, see [Enabling Dynamic Keys](data-encryption.md#enabling-dynamic-keys) [page 227].

## Managing Encryption Keys for Company Data

The encryption keys for the data stored in company databases are managed in the SLD. For more information, see [Managing Dynamic Keys for the Data in Company Databases](../system-landscape-directory/dynamic-keys.md) [page 89].

## Managing Certificates and Private Keys Used in HTTPS Connection

You can update the certificates through reconfiguration using the SAP Business One *Components Wizard*. For more information, see [Reconfiguring the System](../reconfiguring-the-system/reconfiguring-components.md) [page 158]

> **Note**
>
> - To secure data, we recommend you update these certificates regularly through reconfiguration.
> - The reconfiguration action also updates the certificate of the authentication service.

## Managing Database Passwords for SLD and Authentication Service

The database passwords for the SLD and the authentication service are specified during installation. You can update the passwords by reconfiguring the SLD.

## Managing Database Passwords for Companies

The passwords of SAP Business One company databases are maintained in the SLD control center. You can go to the *DB Instances and Companies* tab of the SLD control center to manage the database passwords registered in the SLD.

## Managing Database Password for SAP Business One Integration Framework

The parameter `bpc.jdbc_encpassword` in the `xcellerator.cfg` file defines the password for the JDBC-based database access. You can find the `xcellerator.cfg` file in the directory `..\SAP\SAP Business One Integration\IntegrationServer\Tomcat\webapps\B1iXcellerator\xcellerator.cfg`. The installation sets this parameter. For more information, see the guide *Operations Guide Part Two* in the online help of the SAP Business One Integration Framework.
