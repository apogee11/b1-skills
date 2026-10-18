---
title: Security Certificate Verification During SSL Communication
source: pdf pp. 224-224, sec 12.4.3
summary: Enabling security certificate verification between SAP Business One services (as of 10.0 SP 2411) and the hostname requirements for certificates.
---

# Security Certificate Verification During SSL Communication

SAP Business One supports security certificate verification during SSL communication between its services.

As of 10.0 SP 2411, you can enable certificate verification during the installation process. This ensures that components verify SAP Business One security certificates by default for new installations. Additionally, you can choose to change the certificate verification settings during reconfiguration for the supported components. For more information about how to enable or change the certificate verification settings, see [Installing SAP Business One](../installing-server-components/server-components-installation.md#installing-sap-business-one) [page 32] and [Reconfiguring the System](../reconfiguring-the-system/reconfiguring-components.md) [page 158].For more information about how to obtain and maintain a valid certificate, see SAP Note [3537539](https://me.sap.com/notes/3537539).

For versions prior to 10.0 SP 2411, you need to manually configure the security certificate verification between SAP Business One services. For more information, see the section *Security Certificate Verification During SSL Communication* in the admin guide version for 10.0 SP 2408 or lower.

> **Note**
>
> In SAP Business One components, the hostname or FQDN must match the Common Name of the security certificate and exist in the Subject Alternative Name (SAN) of the security certificate.
