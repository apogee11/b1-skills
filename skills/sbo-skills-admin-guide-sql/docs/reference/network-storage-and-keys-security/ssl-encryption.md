---
title: SSL Encryption, Including Encrypting Communication with Databases
source: pdf pp. 224-225, sec 12.4.4
summary: Which channel can be secured with SSL, certificate sources and caveats, and how to encrypt communication between the database server and SAP Business One clients.
---

# SSL Encryption, Including Encrypting Communication with Databases

You can secure the following communication channel using SSL encryption:

SAP Business One server ⇔ SAP Business One clients

> **Note**
>
> Using SSL encryption may degrade network performance. SSL encryption requires certificates, which are time limited and require annual renewal. You can acquire the necessary certificates using either of the following methods:
>
> - Third-party Certificate Authority You can purchase certificates from a third-party global Certificate Authority that Microsoft Windows trusts by default.
> - Certificate Authority Server You can configure a Certificate Authority (CA) server to issue certificates. If you choose this method, you must configure all machines in your SAP Business One landscape to trust the CA’s root certificate.

## Encrypting Communication with Databases

To secure the TCP/IP communication channel between the database server and SAP Business One clients, you can implement SSL encryption. This prevents SAP Business One application data, including the database credentials, from being exposed.

SAP Business One fully supports SQL SSL. We recommend that you implement SSL in SAP Business One without making configuration changes in SAP Business One.

For information about Microsoft SSL encryption guidelines, see https://www.msdn.microsoft.com and search for the following topics:

- Net-Library Encryption
- Client Net-Libraries
