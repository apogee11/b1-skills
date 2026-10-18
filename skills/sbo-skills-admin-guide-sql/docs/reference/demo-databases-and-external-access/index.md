# Demo Databases and External Access

## [Deploying Demo Databases](demo-databases.md)
Use when: restoring the SAP Business One demo databases from the downloaded zip files with SQL Server Management Studio; demo databases missing after installing FP 2102 or higher.
Terms: demo databases, `*.zip`, SAP Help Portal, SQL Server Management Studio, *Restore Database*, *Restore: From Device*, *Overwrite the existing database*, *Leave database non-operational but able to restore additional transaction logs*, `Restore of Database <sid> completed successfully`, SAP Note 928839, 10.0 FP 2102
Not here: restoring your own company backups → [restoring-databases](../maintaining-databases/restoring-databases.md)

## [external-access/](external-access/index.md)
Use when: exposing Browser Access, the Web client, the SLD, the authentication server, Mobile Service or Microsoft 365 Integration to external networks; choosing a reverse proxy or NAT/PAT; preparing certificates and external addresses; configuring the Browser Access service and opening it in a browser.
Terms: external access, external address, reverse proxy, NAT/PAT, nginx, `b1c_extAddress.conf`, PKCS12, `.pfx`, `/dispatcher`, `/serviceMonitor/`, SAP Business One Browser Access Server Gatekeeper, *Initial Processes*, *Maximum Processes*, *Idle Processes*, `logback.xml`
Sections: [Choosing a method](external-access/choosing-a-method.md) · [Certificates](external-access/https-certificates.md) · [Reverse proxy](external-access/reverse-proxy-mode.md) · [NAT/PAT](external-access/nat-pat.md) · [Browser Access service](external-access/browser-access-service.md) · [Address mapping](external-access/mapping-external-addresses.md) · [Opening in a browser](external-access/accessing-in-web-browser.md) · [Monitoring and logging](external-access/monitoring-and-logging.md)
Not here: installing the Browser Access service → [browser-access-service](../installing-server-components/browser-access-service.md); the SLD external address mapping tab → [external-address-mapping](../system-landscape-directory/external-address-mapping.md)
