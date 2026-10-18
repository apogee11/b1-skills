---
title: Other Security Recommendations
source: pdf pp. 263-266, sec 12.14
summary: Hardening recommendations for demo databases, the operating system, low-privileged service accounts, UI API connection string, Service Layer authentication, JVM upgrades and nginx DoS protection.
---

# Other Security Recommendations

- [Demo Database](#demo-database)
- [Post-Uninstallation Activities](#post-uninstallation-activities)
- [Operating System](#operating-system)
- [System Hardening](#system-hardening)
- [Configurating Services Running as Low-Privileged Operating System Users on Windows Servers](#configurating-services-running-as-low-privileged-operating-system-users-on-windows-servers)
- [Microsoft Windows Domain Account Authentication](#microsoft-windows-domain-account-authentication)
- [Log Configuration](#log-configuration)
- [Turning off the Default UI API Connection String](#turning-off-the-default-ui-api-connection-string)
- [Service Layer](#service-layer)
- [Shared Folder](#shared-folder)
- [Upgrading SAP JVM](#upgrading-sap-jvm)
- [Setting Up Dos Protection (Optional)](#setting-up-dos-protection-optional)

You can check the following information to identify if you securely operate the SAP Business One application.

## Demo Database

The demo databases (schemas) provided are not for productive use. Do not use the demo databases in a productive environment.

If you install the demo databases, log in with manager account and change the default password immediately for each demo database.

## Post-Uninstallation Activities

Immediately after uninstalling SAP Business One, you are required to manually delete the SAP Business One folders on Windows to avoid leaking any data.

## Operating System

- Keep the boundaries between client components. Restrict end user access to the operating system on servers.
- Protecting the high privileged accounts of the operating system is top priority.
- We highly recommend that you deploy terminal servers for accessing the SAP Business One client, and configure the database server explicitly to only accept connections from the necessary servers (including, but not limited to, terminal servers).
- If you use a terminal server to access SAP Business One, we recommend that you deploy tools (for example, AppLocker) to technically prevent users from running malicious applications in the landscape.

## System Hardening

We recommend that you implement system hardening in different layer of your system (for examples, operating system hardening, database hardening and network hardening) according to your security requirements.

## Configurating Services Running as Low-Privileged Operating System Users on Windows Servers

- **License Service**
  We recommend that you run the SAP Business One license service as a low-privileged operating system user.
- **Data Interface Server**
  We recommend that you run Data Interface Server (DI Server) as a low-privileged operating system user. You can perform the following steps:
  1. Configure the Windows service DI server to log in with local service users or network service users.
  2. Give permissions to the directory where the DI Server logs are located (Log path is defined in `<server tools install folder>\DI_Server\Config.xml`. The default log path is the current directory.)
  3. Restart the Windows service DI Server.
- **Workflow**
  The SAP Business One workflow service runs as a network service user by default.
- **SAP Business One Server Tools Service**
  We recommend that you run SAP Business One Server Tools Service as a low-privileged operating system user (`NetworkService`). You can perform the following steps:
  1. Configure the Windows service SAP Business One Server Tools Service to log in with network service users.
  2. Grant `Read` and `Write` permissions to the network service user for the following folders:
     - `C:\Program Files\SAP\SAP Business One ServerTools\License Service\webapps\lib`
     - `C:\Program Files\SAP\SAP Business One SetupFiles\tomcat`
     - `C:\Program Files\SAP\SAP Business One SetupFiles\tomcat\logs`
  3. Restart the SAP Business One Server Tools Service.

## Microsoft Windows Domain Account Authentication

When binding an SAP Business One user account to a Microsoft Windows domain account, it is important to note that other applications on the same Windows session may potentially access your SAP Business One System Landscape Directory (SLD). It is strongly advised not to run any other applications aside from SAP Business One in this scenario.

## Log Configuration

For troubleshooting purposes, sometimes you need to turn on the detailed log or debugging log in configuration. Once the troubleshooting is completed, ensure that you change back the settings and delete the debugging logs.

## Turning off the Default UI API Connection String

In a productive environment, we strongly recommend that you turn off the default UI API connection string on presentation servers (the terminal servers installed on the SAP Business One client). For more information, see SAP Note 2755830 (https://me.sap.com/notes/2755830).

## Service Layer

Service Layer provides basic authentication. However, for security reasons, we recommend that you do not use the basic authentication.

## Shared Folder

We recommend that you provide anti-virus protection for the shared folder, either at the server-level or at the company-level.

## Upgrading SAP JVM

The SAP Machine 21 used in SAP Business One is located in `<Server Tools Installation Folder>\Common\sapmachine_21 for server tools and <Installation Folder>\SAP Business One BAS GateKeeper\sapmachine for BA`. If you need to upgrade the SAP Machine 21 to the latest patch, you can download it from the SAP Website and replace the folders with the new patch.

## Setting Up Dos Protection (Optional)

The `ngx_http_limit_req_module` module is used to limit the processing rate of requests coming from a single IP address. The `ngx_http_limit_conn_module` module is used to limit the number of connections from a single IP address. There could be several `limit_req` and `limit_conn` directives.

For example, the following configuration in `b1c_sldCluster.conf` will limit:

- The processing rate of requests coming from a client IP per second (`rate=<number>r/s`)
- The number of connections to the server per client IP (`limit_conn perip <number>`)
- The total number of connections to the virtual server (`limit_conn perserver <number>`)

```text
limit_req_zone $binary_remote_addr zone=myRateLimit:10m rate=1r/s;
limit_conn_zone $binary_remote_addr zone=perip:10m;
limit_conn_zone $server_name zone=perserver:10m;
server {
...
limit_req zone=myRateLimit;
limit_conn perip 10;
limit_conn perserver 100;
...
}
```

For more information, see Module ngx_http_limit_req_module (https://nginx.org/en/docs/http/ngx_http_limit_req_module.html) and Module ngx_http_limit_conn_module (https://nginx.org/en/docs/http/ngx_http_limit_conn_module.html).
