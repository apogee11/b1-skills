# External Access

## [Enabling External Access and Choosing a Method](choosing-a-method.md)
Use when: what secure external access needs; deciding between a reverse proxy and NAT/PAT; the trust chain of certificates.
Terms: reverse proxy, NAT/PAT, Network Address Translation, external requests, Citrix, trusted root certificate, third-party CA, local enterprise CA, Validate SSL Certificate, external address of the SLD accessible from the internal network, DNS entry
Sections: [Choosing a method](choosing-a-method.md#choosing-a-method-to-handle-external-requests) · [Reverse proxy](choosing-a-method.md#reverse-proxy) · [NAT/PAT](choosing-a-method.md#natpat)
Not here: reverse proxy setup with nginx → [reverse-proxy-mode](reverse-proxy-mode.md)

## [Preparing Certificates for HTTPS Services](https-certificates.md)
Use when: certificate requirements (chain, key size, hash) for services reachable from outside; which certificates a reverse proxy or NAT/PAT needs.
Terms: PKCS12, `.pfx`, entire certificate chain, wildcard DNS `*.DomainName`, 2048-bit RSA, 4096-bit RSA not supported by Java, 256-bit ECDH, SHA-2, SHA256, *Subject Alternative Name*
Not here: certificate verification during SSL communication → [security-certificate-verification](../../network-storage-and-keys-security/security-certificate-verification.md); changing the Browser Access certificate → [reconfiguring-browser-access-service](../../reconfiguring-the-system/reconfiguring-browser-access-service.md)

## [Preparing External Addresses: Reverse Proxy Mode](reverse-proxy-mode.md)
Use when: preparing external addresses for each component; setting up and testing an nginx reverse proxy; limiting connections per IP.
Terms: external address, internal address, `abc.corp`, `def.com`, nginx 1.26.0, `nginx_conf OP.zip`, `b1c_extAddress.conf`, `server.cer`, `server.key`, `ssl_session_cache shared:WEB:10m;`, `${nginx}\html`, `ControlCenter` folder, `/sld/sld0100.svc`, `/auth`, `/dispatcher`, `/B1iService`, `/mobileservice`, `/ms365i`, port `8443`, `limit_conn perip`, `ngx_http_limit_conn_module`, 9.2 PL03 nginx on Linux, Service Layer not exposed
Sections: [External addresses](reverse-proxy-mode.md#preparing-external-addresses) · [Reverse proxy mode](reverse-proxy-mode.md#reverse-proxy-mode) · [nginx](reverse-proxy-mode.md#configure-nginx-reverse-proxy) · [Connection test](reverse-proxy-mode.md#connection-test) · [DoS protection](reverse-proxy-mode.md#set-up-dos-protection-optional)
Not here: NAT/PAT → [nat-pat](nat-pat.md); securing the reverse proxy connection (sec 12.4.2.4) → [reverse-proxy](../../network-storage-and-keys-security/secure-service-connections/reverse-proxy.md)

## [Preparing External Addresses: NAT/PAT](nat-pat.md)
Use when: preparing external addresses when NAT/PAT handles client requests; same domain name inside and outside; testing the SLD connection.
Terms: NAT/PAT, `abc.com`, one external address per component, external address and port combination unique, common name of the certificate, `/sld/sld0100.svc`, `/auth`, `/dispatcher`, `/B1iXcellerator`, `/mobileservice`, `/ms365i`
Sections: [Connection test](nat-pat.md#connection-test)
Not here: reverse proxy → [reverse-proxy-mode](reverse-proxy-mode.md)

## [Configuring Browser Access Service](browser-access-service.md)
Use when: editing the Browser Access service entry in the SLD; changing the service URL; sizing the number of client processes; applying the change.
Terms: `SAP Business One Browser Access Server Gatekeeper`, `https://<Hostname>:<Port+10>/ControlCenter`, *Services* tab, *Edit Service*, *Service URL*, *Initial Processes*, *Maximum Processes*, *Idle Processes*, *Description*, date and time synchronized with the database server
Not here: installing the service → [browser-access-service](../../installing-server-components/browser-access-service.md); changing its certificate → [reconfiguring-browser-access-service](../../reconfiguring-the-system/reconfiguring-browser-access-service.md)

## [Mapping External Addresses to Internal Addresses](mapping-external-addresses.md)
Use when: which components need an external-to-internal mapping in the SLD (not the integration framework); restarting services afterwards.
Terms: external address mapping, Authentication Server, Browser Access Service, Mobile Service, Web Client, Microsoft 365 Integration, restart SAP Business One Browser Access Server Gatekeeper, 5 to 10 minutes, SAP Note 2198134
Not here: the SLD control center tab where the mapping is entered (sec 9.1.6) → [external-address-mapping](../../system-landscape-directory/external-address-mapping.md)

## [Accessing SAP Business One in a Web Browser](accessing-in-web-browser.md)
Use when: opening SAP Business One in a browser through Browser Access; supported browsers; load balancing of several Browser Access servers.
Terms: `https://BASExternalAddress.abc.com:Port/dispatcher`, Mozilla Firefox, Google Chrome, Microsoft Edge, *Automatically Detect Intranet Network*, Apple Safari, Adobe Flash Player, Crystal dashboards, round robin
Not here: the Web client (sec 9.2.10) → [web-client](../../configuring-services/web-client/index.md)

## [Monitoring and Logging Browser Access](monitoring-and-logging.md)
Use when: watching Browser Access processes; finding Browser Access logs; raising the logging level to DEBUG.
Terms: `https://<dispatcherHostname>:<port>/serviceMonitor/`, `SAP Business One BAS GateKeeper\tomcat\logs`, `logback.xml`, `WARN`, `DEBUG`
Not here: other log locations → [log-file-locations](../../appendix/log-file-locations.md); securing Browser Access connections (sec 12.4.2.3) → [browser-access](../../network-storage-and-keys-security/secure-service-connections/browser-access.md)
