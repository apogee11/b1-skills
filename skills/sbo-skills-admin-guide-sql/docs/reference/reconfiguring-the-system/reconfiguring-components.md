---
title: Reconfiguring the System
source: pdf pp. 158-161, sec 9.8*
summary: Which settings the SAP Business One Components Wizard can change in reconfiguration mode, and the step-by-step reconfiguration procedure.
---

# Reconfiguring the System

## Context

After the installation, you can reconfigure the Server Tools, Service Layer, Web client, Webhook Messenger, Electronic Document Service and SLD Agent using the SAP Business One Components Wizard.

The reconfiguration mode allows you to update some external information with SAP Business One and change some settings, as summarized in the table below:

<!-- table: t158-01 -->
<!-- table: t159-01 -->
- **Setting**: Network address of the SAP Business One components
  - **Remarks**: You can select a new IP address or enter a new hostname for the selected components.
- **Setting**: Certificate verification settings
  - **Remarks**: You can enable or disable the certificate verification.
- **Setting**: Service ports
  - **Remarks**: You can specify new ports for SAP Business One services.
- **Setting**: Authentication service port
  - **Remarks**: You can specify a new port for the authentication service.
- **Setting**: Security certificate
  - **Remarks**: You can change the certificate used for authentication.
- **Setting**: Landscape server address and the port number
  - **Remarks**: You can select a new network address and port number as the SLD address that will be used by the selected components.
- **Setting**: License server node type
  - **Remarks**: You can change the node type for the license server.
- **Setting**: Database server address and database user password
  - **Remarks**:

    You can specify new database server connection properties.

    If you want to keep using the original database user for life cycle management but the password for the database user has changed, you must "tell" SAP Business One about this change.
- **Setting**: Installed component settings
  - **Remarks**:

    You can change the settings for installed SAP Business One components, including

    - changing the Service Layer settings
    - changing the port number used by Web Client.
    - changing the port number used by Electronic Document Service.
    - changing the port number used by Electronic File Mapping Transformation Service.
- **Setting**: Service databases
  - **Remarks**: You can choose to keep the current authentication service schema or connect to a different schema
- **Setting**: SLD schema
  - **Remarks**: You can specify a new schema for the SLD.

The following procedure describes how to perform the reconfiguration using the components wizard.

## Procedure

1. Navigate to the installation folder (default path: `C:\Program Files\SAP\SAP Business One SetupFiles\`).
2. Run the `setup.exe` file.

   You can also start the components wizard in the *Programs and Features* window (*Control Panel* > *Programs* > *Programs and Features*), select *SAP Business One Components Wizard*).
3. In the *Setup Wizard* window, select *Reconfiguration* and choose *Next*.
4. In the *Network Address* window, you can select a new IP address or enter the fully qualified domain name (FQDN) in *Hotstname* for SAP Business One components. Choose *Next* to continue.
5. The *Installed Components for Reconfiguration* window lists the installed components. Choose *Next* to continue.
6. In the *Certificate Verification Settings* window, you can enable or disable certificate verification.

   When you choose to enable certificate verification, make sure that you obtain a valid certificate and won't use a self-signed certificate. For more information about the necessary prerequisites, see SAP Note 3520401 (https://me.sap.com/notes/3520401).

   Figure: The Certificate Verification Settings window of the SAP Business One Components wizard.

   ![p160-01](../../assets/p160-01.png)

   > **Note**
   >
   > You cannot choose to generate a self-signed certificate if you enable certificate verification in this window.
7. In the *Port for Server Tools* window, you can specify a new port number for the server tools. Choose *Next* to continue.
8. In the *Port for License Service* window, you can specify a new port number for the license service. Choose *Next* to continue.
9. If you choose to reconfigure Job Service, the *Port for Job Service* window appears. In this window, you can specify a new port number for the job service. Choose *Next* to continue.
10. If you choose to reconfigure Service Layer or Mobile Service, the *Port for Service Layer Controller and Mobile Service* window appears. In this window, you can specify a new port number for the service layer controller and mobile service. Choose *Next* to continue.
11. If you choose to reconfigure Microsoft 365 Integration, the *Port for Microsoft 365 Integration* window appears. In this window, you can specify a new port number for the Microsoft 365 integration. Choose *Next* to continue.
12. In the *Authentication Service Port* window, you can specify a new port for the authentication service. Choose *Next* to continue.
13. In the *Site User Password* window, enter the password for the site super user `B1SiteUser`, and choose *Next* to continue.

    Note that you can change the landscape administrator password only in the SLD. For more information, see [Password Encryption](../security-landscape-users-authorization/landscape-administrator-management.md#password-encryption) [page 209].
14. In the *Specify Security Certificate* window, you can change the certificate used for authentication. Choose *Next* to continue.
    - Third-party certificate authority – You can purchase certificates from a third-party global Certificate Authority that Microsoft Windows trusts by default. If you use this method, select the *Specify PKCS12 Certificate Store and Password* radio button and enter the required information
    - Certificate authority server – You can configure a Certificate Authority (CA) server in the SAP Business One landscape to issue certificates. You must configure all servers in the landscape to trust the CA’s root certificate. If you use this method, select the *Specify PKCS12 Certificate Store and Password* radio button and enter the required information.
    - [Not recommended] Generate a self-signed certificate – You can let the installer generate a self-signed certificate; however, your browser will display a certificate exception when you access the SLD server, as the browser does not trust this certificate. To use this method, select the *Use Self-Signed Certificate* radio button.

    > **Note**
    >
    > If you enabled certificate verification in the previous step, you cannot choose to generate a self-signed certificate in this window.
15. In the *Landscape Server* window, you can specify a new network address and port number, and then choose *Next*.
16. In the *License Server Node Type* window, you can change the node type for the license server.
17. In the *Database Server Specification* window, you can update the database server connection properties.
18. In the *Service Layer* window, you can change the information for *Install Service Layer Load Balancer*,*Port* and *Threads per Load Balancer Member*, and add the information for *Service Layer Load Balances Members* .
19. In the *Web Client Port* window, you can change the port number used by the Web client.
20. In the *Port for Webhook Messenger* window, you can change the port number used by the webhook messenger.
21. In the *Electronic Document Service Port* window, you can change the port numbers used by the Electronic Document Service.
22. In the *Electronic File Mapping Transformation Service Port* window, you can change the port numbers used by the Electronic File Mapping Transformation Service.
23. In the *Service Databases* window, you can choose to keep the current authentication service schema or connect to a different schema.
24. In the *System Landscape Directory Schema* window, you can specify a new schema for the System Landscape Directory.
25. In the *Review Reconfigured Settings* window, review the changed and unchanged settings and then choose *Start* to begin the reconfiguration process.
26. In the *Reconfiguration Progress* window, wait for the reconfiguration to finish and then choose *Next* to continue.
27. In the *Reconfiguration Status* window, review the reconfiguration results, take note of the components that have failed (if any), and then choose *Next* to continue.
28. In the *Reconfiguration Completed* window, choose *Finish* to exit the wizard. You can check more details from the *Log File* and *Log Folder* in this window.
