---
title: "Secure Connections: Server Tools, CORBA License Server, Tomcat Components and SBO Mailer"
source: pdf pp. 218-220, sec 12.4.2*, 12.4.2.1
summary: Default ports, TLS versions and cipher suites, Tomcat server.xml changes and certificates for the Server Tools components, plus the CORBA license server and SBO Mailer SMTP encryption.
---

# Secure Connections: Server Tools, CORBA License Server, Tomcat Components and SBO Mailer

## Configuring Services with Secure Network Connections

To make communication safer, we recommend that you configure the SAP Business One services with secure network connections.

## Server Tools

### CORBA License Server

The default port for the CORBA license server is `30000` or `30001`. The CORBA license server enforces secure connection via CORBA.

The CORBA license server now is the proxy of the HTTPS license server only for compatibility purposes and may be removed in future patches. We do not recommend you use SAP Business One Service Manager to configure the license service.

### Components in Tomcat Instances

In SAP Business One, the following components operate in separate Tomcat instances

- System Landscape Directory, Extension Manager
- License Service (HTTPS)
- Job Service
- Mobile Service and Service Layer Configuration Manager
- Workflow
- Microsoft 365 Integration

You can configure the components with the same network security settings as follows:

- The default port for Server Tools (64-bit) (`B1ServerTools64`) is `40000`
- The default port for License Service (64-bit) (`B1ServerTools64License`) is `40002`
- The default port for Job Service (64-bit) (`B1ServerTools64JobService`) is `40004`
- The default port for Service Layer Controller (64-bit) (`B1ServerTools64ServiceLayerController`) is `40005`
- The default port for Workflow Engine (`B1Workflow`) is `60000`
- The default port for Microsoft 365 Integration (64-bit) (`B1ServerTools64MS365Integration`) is `40006`

The relevant ports should be exposed to the Internet if you need to use some SAP Business One components on Internet

The components enforce secure connections via HTTPS encryption.

By default, the supported TLS version is 1.2 or 1.3. The default TLS cipher suites are listed as follows:

- `TLS13-AES-256-GCM-SHA384`
- `TLS13-CHACHA20-POLY1305-SHA256`
- `TLS13-AES-128-GCM-SHA256`
- `TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256`
- `TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA384`
- `TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA`
- `TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256`
- `TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA384`
- `TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`
- `TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA256`
- `TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384`
- `TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA`
- `TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA256`
- `TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384`
- `TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`

You can change TLS versions or cipher suites (If you intend to **add** new TLS versions or cipher suites, make sure that they are supported by java and Tomcat) according to your security requirements by changing the Tomcat configuration file `<installation folder>\SAP Business One SetupFiles\tomcat-instances\<service name>\conf\server.xml`. The configuration file will be overwritten when you reinstall or upgrade the component. Ensure that you change it back after the installation or upgrades.

You can perform the following steps to change TLS versions or cipher suites:

1. Open the Tomcat configuration file `<installation folder>\SAP Business One SetupFiles\tomcat-instances\<service name>\conf\server.xml`
2. Find all `<connector>` tags in the file.
3. Change the attribute `ciphers` to the preferred cipher suites.
4. Change the attribute `sslEnabledProtocols` to the preferred TLS versions.
5. Save the changes.
6. Restart the server tools.

The components need a valid PKCS 12 certificate to function properly. However, for security reasons, we strongly recommend that you specify a valid certificate during the installation process or change the certificate to a valid one after the installation.

### SBO Mailer

The SBO Mailer is connected to the SMTP server. We recommend that you use SSL/TLS encryption for the SMTP server connection.

If you use SSL/TLS encryption, you must select *Microsoft .Net* for *SMTP Client* during the SBO Mailer configuration. The version of the SSL/TLS protocol depends on your operating system and the version of the installed Microsoft .Net Framework. For more information about securely configuring the SSL/TLS protocol, see [Transport Layer Security (TLS) best practices with the .Net Framework](https://learn.microsoft.com/en-us/dotnet/framework/network-programming/tls).
