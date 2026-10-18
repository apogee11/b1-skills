---
title: Installing Web Client
source: pdf pp. 47-49, sec 5.1.3
summary: Prerequisites, setup wizard steps (certificate, landscape server, port) and post-install notes for installing the Web client.
---

# Installing Web Client

## Prerequisites

- You have installed the Service Layer, and a valid Service Layer registration in the System Landscape Directory (SLD) is required.
- You have installed the job service if you want to use the reporting service and the Microsoft 365 integration features in the Web client.
- You have installed Windows PowerShell 5 or the higher version on the machine on which you are performing the installation.

## Procedure

1. Navigate to the installation folder (default path: `\Packages.x64\ComponentsWizard`).
2. Run the `install.exe` file.
3. In the *Setup Wizard* window, select *Installation and Upgrade* and choose *Next*.
4. In the *Select Features* window, select *Web Client* and choose *Next*.
5. In the *Certificate Verification Settings* window, enable or disable certificate verification. The checkbox *Enable certificate verification* is checked by default.

   When you choose to enable certificate verification, make sure that you obtain a valid certificate and won't use a self-signed certificate. For more information about the necessary prerequisites, see SAP Note [3520401](https://me.sap.com/notes/3520401).

   Figure: The Certificate Verification Settings window of the components setup wizard.

   ![p048-02](../../assets/p048-02.png)
6. In the *Network Address* window, select an IP address, or use the hostname, as the network address for the selected components and choose *Next*. The hostname is prefilled with the full qualified domain name (FQDN).
7. In the *Specify Security Certificate* window, specify a security certificate and choose *Next*. You can also choose to use a self-signed certificate.

   Communication between the SLD and SAP Business One clients or DI API is encrypted using the HTTPS protocol, so a certificate is required for authentication. You can obtain a certificate using the following methods:

   - Third-party certificate authority – You can purchase certificates from a third-party global Certificate Authority that Microsoft Windows trusts by default. If you use this method, select the *Specify PKCS12 Certificate Store and Password* radio button and enter the required information
   - Certificate authority server – You can configure a Certificate Authority (CA) server in the SAP Business One landscape to issue certificates. You must configure all servers in the landscape to trust the CA’s root certificate. If you use this method, select the *Specify PKCS12 Certificate Store and Password* radio button and enter the required information.
   - [Not recommended] Generate a self-signed certificate – You can let the installer generate a self-signed certificate; however, your browser will display a certificate exception when you access the SLD server, as the browser does not trust this certificate. To use this method, select the *Use Self-Signed Certificate* radio button.

   > **Note**
   >
   > If you enabled certificate verification in the previous step, you cannot choose to generate a self-signed certificate in this window.
8. In the *Landscape Server* window, enter the landscape server address and the landscape administrator password, and choose *Next*.

   > **Note**
   >
   > The installation process can only be continued by entering the credentials of the `B1SiteUser` account. Other landscape administrators do not have the permissions to perform this operation.
9. If only one database instance is registered in the SLD, the Web client is automatically bound to the database instance; if multiple database instances are registered in the SLD, you need to choose one database instance from the dropdown list in the *Database Instances* window.
10. In the *Web Client Port* window, specify a port number that is to be used by Web client and choose *Next*. The default number is `443`.

    > **Note**
    >
    > The port number must be within the `0`-`65536` range.
11. In the *Review Settings* window, review your settings and then choose *Install* to start the installation.
12. In the *Setup Progress* window, when the progress bar displays 100%, choose *Next* to finish the installation.
13. In the *Setup Process Completed* window, review the installation results, and then choose *Finish* to exit the wizard.

## Results

After installing the Web client, you can see the log file under `%ProgramData%\SAP\SAP Business One\Log\SAP Business One\%USERNAME%\B1WinInstaller_xxxxxxxxxxxx.log`.

> **Note**
>
> The Web client does not start automatically after a Microsoft Windows server restarts. You need to manually restart the Web client. For more information, see SAP Note [2875511](https://me.sap.com/notes/2875511).
