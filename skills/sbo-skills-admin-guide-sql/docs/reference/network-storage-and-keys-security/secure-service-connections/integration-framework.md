---
title: "Secure Connections: Integration Framework"
source: pdf pp. 223-223, sec 12.4.2.5
summary: Integration framework HTTP and HTTPS ports, TLS cipher suites, the JKS certificate requirement, and the steps to disable HTTP and replace the self-signed certificate.
---

# Secure Connections: Integration Framework

By default, the integration framework server uses port `8080` for HTTP and `8443` for HTTPS. You do not need to expose the port to the Internet.

If you choose the HTTPS connection, use TLS version 1.2 or 1.3; the corresponding TLS cipher suites are listed as follows:

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

The integration framework service needs a valid JKS format certificate. The default certificate option is a self-signed certificate. However, for security reasons, we strongly recommend that you perform the following steps:

1. Disable the HTTP protocol by removing the following parameters from the Tomcat configuration file: `<Connector port="8080" protocol="HTTP/1.1" connectionTimeout="20000" redirectPort="8443" enableLookups="false" server=" "/>`
2. Restart the integration framework service
3. Change the self-signed certificate to a valid one. For more information, see SAP Note [2405043](https://me.sap.com/notes/2405043).

> **Note**
>
> If you already have disabled the HTTP protocol or changed the port, check the protocol and port value in the table `SLSPP` of database `SBO-COMMON (SBOCOMMON)`.
