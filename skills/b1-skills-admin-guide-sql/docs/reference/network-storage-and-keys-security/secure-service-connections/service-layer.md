---
title: "Secure Connections: Service Layer"
source: pdf pp. 220-221, sec 12.4.2.2
summary: Service Layer load balancer ports, TLS versions and cipher suites, certificate and key locations, and how to change TLS settings in the Apache HTTP Server configuration.
---

# Secure Connections: Service Layer

The default port for SAP Business One System Service Layer load balancer is `50000`. According to the node number, the Service Layer opens the corresponding ports for load balancer members as follows:

- `50001`
- `50002`
- `50003`
- `…`

The Service Layer is for internal component calls only and you do not need to expose it to the Internet.

The service layer enforces secure connection via HTTPS encryption with TLS version 1.2 or 1.3, and the corresponding TLS cipher suites are listed as follows:

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

The Service Layer needs a valid X509 format certificate. The certificate is stored at: `<Installation Folder>/ServiceLayer/Conf/server.crt` and the private key is stored at: `<Installation Folder>/ServiceLayer/Conf/server.key`.

By default, the Service Layer uses a self-signed certificate. However, for security reasons, we strongly recommend that you specify a valid certificate during the installation process. Alternatively, you can manually change the certificate and private key, and then restart the Service Layer.

You can change TLS versions or cipher suites (If you intend to **add** new TLS versions or cipher suites, make sure that they are supported by java and Tomcat) according to your security requirements by changing the Apache HTTP Server configuration file (`<install folder>\ServiceLayer\Conf\httpd-b1s-lb.conf`). The configuration file will be overwritten when you reinstall or upgrade the component. Ensure that you change it back after the installation or upgrades.

You can perform the following steps to change TLS versions or cipher suites:

1. Open the configuration file `<install folder>\ServiceLayer\Conf\httpd-b1s-lb.conf`.
2. Follow the Apache HTTP Server configuration process to change the following configurations:
   - `SSLProtocol`
   - `SSLCipherSuite`
3. Save the changes.
4. Restart the service layer.
