---
title: Change Log for Earlier Versions
source: pdf pp. 15-20, sec 2.13
summary: Version history of the Administrator's Guide from version 1.0 (2019-10-30) to 2.2 (2023-09-15), with the changes made in each version.
---

# Change Log for Earlier Versions

<!-- table: t015-03 -->
- **Version**: 1.0
  - **Date**: 2019-10-30
  - **Change**: First version.
- **Version**: 1.1
  - **Date**: 2020-01-06
  - **Change**:

    - Section 2: SAP Business One supports Microsoft Office 2019.
    - Section 3.1.1: Browser access service is supported.
    - Section 3.2: A new section about installing the Service Layer.
    - Section 3.3: A new section about installing SAP Business One, Web client.
    - Section 7.2.8: A new section about configuring the Web client.

<!-- table: t016-01 -->
- **Version**: 1.2
  - **Date**: 2020-04-13
  - **Change**:

    - Section 1.2.1: A new server component Electronic Document Service is added.
    - Section 2: SAP Business One also supports Microsoft SQL Server 2016 and 2019.
    - Section 3.1: You can install the Service Layer, Web client and Electronic Document Service using either SAP Business One Setup Wizard or SAP Business One Components Wizard.
    - Section 3.1.4: A new section about installing Electronic Document Service.
    - Section 3.1.2, Section 3.1.3, and Section 8.2.1.1: Installing Windows PowerShell 5 or the higher version is a prerequisite for the Component Setup Wizard.
    - Section 4: As of 10.0 PL02, SAP Business One supports SAP Crystal Reports 2016 SP7, version for the SAP Business One application.
    - Section 7.1.6: The Service Layer can be added in the SLD.
    - Section 7.2.2.2: Ensure that you have installed the Service Layer before you install the job service in version SAP Business One 10.0 PL02 or higher.
    - Section 7.3.6: You can access SAP Business One in the following Web browsers:
      - Microsoft Edge
      - Apple Safari (Mac and iPad)
    - Section 10.4.3: Three new sections (10.4.3.1, 10.4.3.2 and 10,4.3.3) about security certificate verifications for the client components, Service Layer and Web client.
    - Section 10.5.2: A new section about data encryption.
    - Section 10.8.5: A new section about the security of Browser Access.
    - Appendix 1: The default port for Electronic Document Service is `7299`.

- **Version**: 1.2.1
  - **Date**: 2020-07-01
  - **Change**:

    - Section 7.1.6: You can add the Web client in the System Landscape Directory.
    - Section 7.3:
      - You can enable external access to SAP Business One, Web client.
      - Section 7.3.3.1: You can configure a nginx reverse proxy.

- **Version**: 1.3
  - **Date**: 2020-08-24
  - **Change**:

    - Section 7.7: A new section about reconfiguring the Service Layer, Web client, Electronic Document Service (EDS) and SLD Agent.
    - Section 10.4.2: You can change TLS version or cipher suites according to your security requirements for the following components:
      - Components in Shared Tomcat
      - Service Layer
      - Workflow
      - Browser Access
    - Section 10.11: A new section about security-relevant logging and tracing.

- **Version**: 1.4
  - **Date**: 2020-11-09
  - **Change**:

    - Section 2: Windows Server 2012 R2 is added as one of the operating system versions, which is only applicable for upgrading SAP Business One.
    - Section 7.1.6: When adding License Manager in the SLD, if you have enabled high availability, you need to specify the URL as `https://<Virtual IP Address>:<port>/LicenseControlCenter`.
    - Section 10.11: The logging information about the System Landscape Directory (SLD), Job Service and Mobile Service is added.

- **Version**: 1.5
  - **Date**: 2021-03-16
  - **Change**:

    - Section 1.3: As of 10.0 FP 2102, the installation package and upgrade package are unified into a single product setup package.
    - Section 3.1: When a new demo database is required, you need to navigate to the SAP Help Portal to download the demo database and import it into SAP Business One manually.
    - Section 6.2: The following major or minor releases are currently supported for upgrade to SAP Business One 10.0 FP 2102:
      - SAP Business One 9.2 PL00-PL11
      - SAP Business One 9.3 PL00-PL14
      - SAP Business One 10.0 PL00-FP 2011
    - Section 7.1.8: A new section about working with audit logs.
    - Section 7.3: A new section about deploying demo databases.
    - Section 10.12:
      - A new section about configurating services running as low-privileged operating system users on Windows servers.
      - A new section about upgrading SAP JVM.
    - Appendix 2: A new appendix about a list of log file locations for SAP Business One components.

- **Version**: 1.6
  - **Date**: 2021-06-07
  - **Change**:

    - Section 1.2.1: Two new server components, Mobile Service and API Gateway Service, are added.
    - Section 3.1:
      - You can install Mobile Service using SAP Business One Setup Wizard. Mobile Service depends on the existence of the Service Layer.
      - You can install API Gateway Service using SAP Business One Setup Wizard. The default port number for Authentication Service is `60010` and the default port number for Gateway Service is `60020`.
      - During the SAP Business One server components installation, the hostname is prefilled with the full qualified domain name (FQDN) in the *Network Address* window.
      - When you install the Service Layer, Web Client, Mobile Service and Electronic Document Service using the SAP Business One Components Wizard (default path: `\Packages.x64\ComponentsWizard`), you do not need to enter the database credentials. If only one database instance is registered in the SLD, the components are automatically bound to database instance; if multiple database instances are registered in the SLD, you need to choose one database instance from the dropdown list.
    - Appendix 1: The default ports for Authentication Service and API Gateway Service are added.

- **Version**: 1.7
  - **Date**: 2021-09-03
  - **Change**:

    - Section 1: This Administrator's Guide applies to the latest release of SAP Business One. For more information about the previous versions of the Administrator's Guide delivered in SAP Business One 10.0, see the SAP Help Portal (https://help.sap.com/viewer/p/SAP_BUSINESS_ONE_PRODUCT_LINE).
    - Section 10.4.2: The procedures for changing TLS versions and cipher suites for the components in shared Tomcat, Service Layer and Browser Access are added.
    - Section 11: Troubleshooting the Web client starting issue.

<!-- table: t018-01 -->
- **Version**: 1.8
  - **Date**: 2021-12-30
  - **Change**:

    - Section 1.2: The server tools including components System Landscape Directory, License Service, Job Service, Workflow, DI Server, and Service Manager are migrated from 32-bit to 64-bit.
    - Section 3.1.2: The default port number that is to be used by the Service Layer for single single-on (SSO) is `40000`.
    - Section 6.3.1: You can upgrade the SAP Business One Server Tools by running the `setup.exe` file in the path `…\Packages.x64\ComponentsWizard\setup.exe` from the upgrade package.
    - Section 7.8: The database user password and the security certificate can be changed in the reconfiguration mode.
    - Section 10.4.2.1.2: The components in the shared Tomcat enforce secure connections via HTTPS encryption with only TLS version 1.2.
    - Section 10.4.2.1.3: The workflow enforces secure connections via HTTPS encryption with only TLS version 1.2.
    - Section 10.4.2.3: Browser Access enforces secure connection via HTTPS encryption with only TLS version 1.2.
    - Section 11: The subsections “Cannot change database password for System Landscape Directory” and “Cannot change security certificate for System Landscape Directory” are removed.

- **Version**: 1.9
  - **Date**: 2022-04-12
  - **Change**:

    - Section 2:
      - Windows Server 2202 is added as one of the operating system versions.
      - The version of Microsoft .NET Framework is changed to 4.8.
    - Section 3.1: The introduction to the internal technical user `b1scswworkingshare` is added.
    - Section 10.4.2: The default TLS versions supported by SAP Business One services are changed to 1.2 and 1.3. The corresponding TLS cipher suites are updated.

<!-- table: t019-01 -->
- **Version**: 2.0
  - **Date**: 2022-12-09
  - **Change**:

    - Section 3.1.3: The dependencies of the Web client are updated.
    - Section 3.1.4: A prerequisite is added for Electronic Document Service.
    - Section 7.1.3: A new section about configuring the authentication service is added.
    - Section 7.1.4: The section about enabling the Single Sign-on function is removed.
    - Section 7.1.6: The SLD is moved from the component list of the *External Address Mapping* tab to the *Security* tab.
    - Section 7.1.8: A new section about managing identity providers is added.
    - Section 7.1.9: A new section about managing users is added.
    - Section 7.4: External address mapping for SLD and Authentication Server is added and the nginx configuration is updated.
    - Section 7.5.3.1:
      - The `nginx conf OP 2208.zip` file is updated.
      - The second and fourth screenshots are replaced with new ones.
    - The external addresses of SLD and other components in the example are changed.
    - Section 7.8: A step about the new window *Authentication Service Ports* is added.
    - Section 8.2: The procedures for remotely registering and unregistering local machines from the SLD control center are removed.
    - Section 10.2.1:
      - Site User is renamed to Landscape Administrator.
      - A new user type SAP Business One User is added.
    - Section 10.2.2:
      - The description for the `Support` user is updated.
      - The `AlertSvc` user is removed from the standard user table. The `Workflow` user is used for the alert service instead of the `AlertSvc` user.
    - Section 10.2.3:
      - A new section about SAP Business One user management is added.
      - The sections about landscape administrator management and MS Windows domain account authentication enablement are updated.
    - Section 10.2.4: A new section about Identity and Authentication Management is added.
    - Appendix 1: The default port for authentication service in the SLD is added.

<!-- table: t020-01 -->
- **Version**: 2.1
  - **Date**: 2023-08-07
  - **Change**:

    - Section 1.2.2: A note describing that the SAP Business One client agent does not move SAP Business One log files to the central log folder in the shared folder is added.
    - Section 2.1: SAP Business One newly supports Microsoft Windows 11.
    - Section 3.1: The description of the *Site User Password* window is updated.
    - Section 6.2: A note describing the method of upgrading SAP Business One from 9.2 or 9.3 to SAP Business One 10.0 FP 2305 is added.
    - Section 6.3.1: Before the Setup Summary window appears, a warning message window about the behavior change for the shared folder is added.
    - Section 7.1.9: The description of the new button *Enable Two-Factor Authentication* is added.
    - Section 10.6:
      - A new section about managing data encryption in Microsoft SQL Server is added.
      - A new section about preventing audit log tampering in database is added.
      - A new section about database access control for audit logs is added.
      - A new section about retention period of audit logs in database is added.
    - Section 10.11: The information about how to view and configure the authentication service audit logs is added.
    - Section 11: A new case about how to troubleshoot license server connectivity issues is added.
    - Appendix 2: Maximum limits on the number and size of log files of the EFM Format Definition are added.

- **Version**: 2.2
  - **Date**: 2023-09-15
  - **Change**:

    - Section 2:
      - A note about Microsoft .NET Framework 4.8 is added.
      - Windows Server 2012 R2 is removed from the supported operating system versions.
    - Section7.4.3.2: A new subsection Connection Test is added.
    - Section 10.12:
      - A new recommendation about deploying tools in the operation system is added.
      - A new section System Hardening is added.
