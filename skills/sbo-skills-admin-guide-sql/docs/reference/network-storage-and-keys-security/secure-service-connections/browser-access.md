---
title: "Secure Connections: Browser Access"
source: pdf pp. 221-222, sec 12.4.2.3
summary: Browser Access default port, TLS versions and cipher suites, how to change them in the Tomcat server.xml, and the PKCS 12 certificate requirement.
---

# Secure Connections: Browser Access

The default port for SAP Business One Browser Access is `8100`. If you need to access SAP Business One services via the Internet, you need to expose this port to the Internet.

Browser Access enforces secure connection via HTTPS encryption with TLS version 1.2 or 1.3; the corresponding TLS cipher suites are listed as follows:

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

You can change TLS versions or cipher suites (If you intend to **add** new TLS versions or cipher suites, make sure that they are supported by java and Tomcat) according to your security requirements by changing the Tomcat configuration file (`<install folder>\common\tomcat\conf\server.xml`). The configuration file will be overwritten when you reinstall or upgrade the component. Ensure that you change it back after the installation or upgrades.

You can perform the following steps to change TLS versions or cipher suites:

1. Open the configuration file `<install folder>\common\tomcat\conf\server.xml`.
2. Find all `<connector>` tags in the file.
3. Change the attribute `ciphers` to the preferred cipher suites.
4. Change the attribute `sslEnabledProtocols` to the preferred TLS versions.
5. Save the changes.
6. Restart the browser access service.

Browser Access needs a valid PKCS 12 certificate to function properly. The default certificate option is a self-signed certificate. However, for security reasons, we strongly recommend that you specify a valid certificate during the installation process.
