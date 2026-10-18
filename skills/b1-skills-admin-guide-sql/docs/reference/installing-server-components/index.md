# Installing server components

## [Installing Server Components](server-components-installation.md)
Use when: installing all server components with the setup wizard in a clean environment; overall install order (server then client); which components make up the server install; SQL Server prerequisites; ports and default values in the wizard; silent server install; users created by the install.
Terms: `setup.exe`, Perform Setup, New Configuration, Install Local System Landscape Directory, SLD, `B1SiteUser`, Certificate Verification Settings, `Config.XML`, `-upgrade`, silent mode, FQDN, `localhost`, `1433`, `SERVER_NAME,9033`, Component Selections, Port for Server Tools `40000`, Port for License Service `40002`, Port for Job Service `40004`, Port for Service Layer Controller and Mobile Service `40005`, Port for Microsoft 365 Integration `40006`, API Gateway Service `60010`, `60020`, PKCS12, self-signed certificate, `B1iadmin`, `IFSERV`, Scenario Packages, Restoration, `B1_Tech_User`, `b1scswworkingshare`, `SCSW_WORKING_SHARE`, `B1_SHR`, `SBOCOMMON`, `SBO-COMMON`, demo databases, `Packages.x64\ComponentsWizard`, `install.exe`, `B1 Integration Component\Technology`, Tomcat, `Procrun2.0`, SQL_Latin1_General_CP1_CI_AS, Mixed mode, TCP/IP, mobile service, job service, remote support platform, SAP Note 3520401
Sections: [Overall procedure](server-components-installation.md#installing-sap-business-one) · [Components to install](server-components-installation.md#server-components-to-install) · [Prerequisites](server-components-installation.md#prerequisites) · [Wizard steps](server-components-installation.md#procedure) · [Results and technical users](server-components-installation.md#results)
Not here: administering Service Layer, Web Client, Webhook Messenger → [service-layer-configuration](../configuring-services/service-layer-configuration.md), [default-browser-group-policy](../configuring-services/web-client/default-browser-group-policy.md), [webhook-messenger-configuration](../configuring-services/webhook-messenger-configuration.md); securing them → [service-layer](../network-storage-and-keys-security/secure-service-connections/service-layer.md), [web-client](../network-storage-and-keys-security/secure-service-connections/web-client.md); installing client components → [installing-client-components](../installing-client-components/index.md); OS, SQL Server and ODBC requirements → [prerequisites](../introduction-and-prerequisites/prerequisites.md)

## [Installing the Browser Access Service](browser-access-service.md)
Use when: enabling SAP Business One access in a Web browser; installing the browser access service on a server that has the client.
Terms: browser access service, `setup.exe`, Connect to Remote System Landscape Directory, `B1SiteUser`, Landscape Administrator Logon, Parameters for Browser Access Service, Service URL, port `8100`, PKCS12, Use Self-Signed Certificate, SAP Business One Browser Access Server Gatekeeper, `Local System`, SAP Notes 2194215, 2194233, 3520401
Not here: installing the client itself → [installing-client-components](../installing-client-components/index.md)

## [Installing the Service Layer](service-layer.md)
Use when: installing the Service Layer, its Apache load balancer and balancer members; choosing ports and node count; checking balancer status after install; upgrading the Service Layer patch level.
Terms: Service Layer, Components Setup Wizard, `install.exe`, `Packages.x64\ComponentsWizard`, Select Features, Service Port `40000`, load balancer port `50000`, Starting Port `50001`, Node Count `10`, Install Service Layer Load Balancer, load balancer members, Threads per Load Balancer Member, Apache, `127.0.0.1`, `balancer-manager`, `B1WinInstaller_xxxxxxxxxxxx.log`, remote installation, PowerShell 5, `B1SiteUser`, single sign-on
Not here: administering the Service Layer → [service-layer-configuration](../configuring-services/service-layer-configuration.md); securing it → [service-layer](../network-storage-and-keys-security/secure-service-connections/service-layer.md); upgrading components → [upgrading-databases-and-components](../upgrade-process/upgrading-databases-and-components.md)

## [Installing Web Client](web-client.md)
Use when: installing the SAP Business One Web client; Web client port; Web client not starting after a server restart.
Terms: Web Client, Web Client Port `443`, `install.exe`, Select Features, job service, reporting service, Microsoft 365 integration, `B1SiteUser`, `B1WinInstaller_xxxxxxxxxxxx.log`, SAP Note 2875511, PowerShell 5
Not here: administering the Web client → [default-browser-group-policy](../configuring-services/web-client/default-browser-group-policy.md); securing it → [web-client](../network-storage-and-keys-security/secure-service-connections/web-client.md)

## [Installing Webhook Messenger](webhook-messenger.md)
Use when: installing the Webhook Messenger and choosing its port.
Terms: Webhook Messenger, Port for Webhook Messenger `40008`, `install.exe`, Select Features, `B1SiteUser`, Landscape Server, PowerShell 5
Not here: administering Webhook Messenger → [webhook-messenger-configuration](../configuring-services/webhook-messenger-configuration.md); securing it → [web-client](../network-storage-and-keys-security/secure-service-connections/web-client.md)

## [Installing Electronic Document Service](electronic-document-service.md)
Use when: installing the Electronic Document Service; its prerequisites and port.
Terms: Electronic Document Service, Electronic Document Service Port `7299`, Service Layer registration in SLD, first registered instance, Service Unit, `install.exe`, Select Features, `B1SiteUser`, PowerShell 5
Not here: Electronic File Mapping Transformation Service, port `7297` → [electronic-file-mapping-transformation-service](electronic-file-mapping-transformation-service.md)

## [Installing Electronic File Mapping Transformation Service](electronic-file-mapping-transformation-service.md)
Use when: installing the Electronic File Mapping Transformation Service; it being mandatory for electronic documents and electronic reports.
Terms: Electronic File Mapping Transformation Service, port `7297`, electronic documents, electronic reports, `install.exe`, Select Features, `B1SiteUser`, PowerShell 5
Not here: Electronic Document Service, port `7299` → [electronic-document-service](electronic-document-service.md)
