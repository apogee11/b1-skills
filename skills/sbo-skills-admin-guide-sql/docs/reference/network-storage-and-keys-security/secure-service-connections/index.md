# Secure Service Connections

## [Server Tools, CORBA License Server, Tomcat Components and SBO Mailer](server-tools.md)
Use when: default ports of the Tomcat-based server tools components; TLS versions and cipher suites; changing them in `server.xml`; CORBA license server port; SMTP encryption for the SBO Mailer.
Terms: `30000`, `30001`, CORBA, `40000`, `40002`, `40004`, `40005`, `40006`, `60000`, `B1ServerTools64`, `B1ServerTools64License`, `B1ServerTools64JobService`, `B1ServerTools64ServiceLayerController`, `B1Workflow`, `B1ServerTools64MS365Integration`, `tomcat-instances\<service name>\conf\server.xml`, `ciphers`, `sslEnabledProtocols`, PKCS 12, *Microsoft .Net* SMTP Client, SSL/TLS
Sections: [CORBA License Server](server-tools.md#corba-license-server) · [Tomcat components](server-tools.md#components-in-tomcat-instances) · [SBO Mailer](server-tools.md#sbo-mailer)
Not here: mailer SMTP configuration → [sbo-mailer](../../configuring-services/job-service/sbo-mailer.md); installing server tools → [server-components-installation](../../installing-server-components/server-components-installation.md)

## [Service Layer](service-layer.md)
Use when: Service Layer load balancer and member ports; TLS and cipher suites; replacing `server.crt` and `server.key`; changing `SSLProtocol` and `SSLCipherSuite` in the Apache configuration.
Terms: `50000`, `50001`, `50002`, `50003`, `server.crt`, `server.key`, `ServiceLayer/Conf`, `httpd-b1s-lb.conf`, `SSLProtocol`, `SSLCipherSuite`, X509, self-signed certificate, load balancer
Not here: installing the Service Layer and load balancer → [service-layer](../../installing-server-components/service-layer.md); post-installation privileges → [service-layer-configuration](../../configuring-services/service-layer-configuration.md)

## [Browser Access](browser-access.md)
Use when: Browser Access default port and exposing it to the Internet; TLS and cipher suites; changing them in Tomcat `server.xml`; PKCS 12 certificate.
Terms: `8100`, `<install folder>\common\tomcat\conf\server.xml`, `<connector>`, `ciphers`, `sslEnabledProtocols`, PKCS 12, self-signed certificate, TLS 1.2, TLS 1.3
Not here: installing the service → [browser-access-service](../../installing-server-components/browser-access-service.md); reconfiguring the certificate → [reconfiguring-browser-access-service](../../reconfiguring-the-system/reconfiguring-browser-access-service.md); Browser Access security recommendations → [browser-access-security](../../sbo-authentication-and-application-security/browser-access-security.md)

## [Reverse Proxy](reverse-proxy.md)
Use when: why use a reverse proxy instead of NAT/PAT; its default port and enforced TLS and cipher suites.
Terms: reverse proxy, NAT, PAT, `443`, external clients, TLS 1.2, TLS 1.3
Not here: setting up the reverse proxy → [reverse-proxy-mode](../../demo-databases-and-external-access/external-access/reverse-proxy-mode.md)

## [Integration Framework](integration-framework.md)
Use when: integration framework ports 8080 and 8443; disabling HTTP; replacing the self-signed JKS certificate; protocol or port changed.
Terms: `8080`, `8443`, JKS, `<Connector port="8080" protocol="HTTP/1.1" ...>`, Tomcat configuration file, SAP Note 2405043, `SLSPP`, `SBO-COMMON`, `SBOCOMMON`
Not here: changing integration framework ports → [changing-server-ports](../../integration-framework-post-install/changing-server-ports.md)

## [Web Client](web-client.md)
Use when: TLS versions and cipher suites the Web client enforces.
Terms: Web client, TLS 1.2, TLS 1.3, `TLS_AES_256_GCM_SHA384`, `ECDHE-RSA-AES128-GCM-SHA256`, Curve 25519
Not here: installing the Web client → [web-client](../../installing-server-components/web-client.md); Web client configuration → [web-client/](../../configuring-services/web-client/index.md)
