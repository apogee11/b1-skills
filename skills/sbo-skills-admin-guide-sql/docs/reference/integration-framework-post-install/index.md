# Integration Framework (Post-Installation)

## [Post-Installation Activities for the Integration Framework](post-installation-overview.md)
Use when: what to check after installing the integration framework; the Windows service; logging on as B1iadmin; framework version 1 vs 2 technical settings.
Terms: `SAP Business One Integration Service`, `B1iadmin`, *Maintenance*, *Cfg Connectivity*, *Configuration*, *Tools*, *Troubleshooting*, *Functional Group*, *B1 Setup*, Integrated Development Environment, *Operations Part 2*
Sections: [Technical settings](post-installation-overview.md#maintaining-technical-settings-in-the-integration-framework)

## [Maintenance, Monitoring and Security, Technical B1i User, Licensing](maintenance-monitoring-and-security.md)
Use when: monitoring the framework; the framework SLD entries; connecting to SAP Business One integration for SAP NetWeaver; the `B1i` technical user and its licenses.
Terms: *Monitoring*, message log, error inbox, transaction monitor, service monitor, `b1Server`, `associatedSrvIP`, `WSforMobile`, *Cfg B1 Event Subscriber*, `B1i` user, `B1iINDIRECT_MSS`, mobile users license
Sections: [Monitoring and security](maintenance-monitoring-and-security.md#maintenance-monitoring-and-security) · [Technical B1i user](maintenance-monitoring-and-security.md#technical-b1i-user) · [Licensing](maintenance-monitoring-and-security.md#licensing)
Not here: security of integration solutions → [integration-solutions-security](../sbo-authentication-and-application-security/integration-solutions-security.md)

## [Assigning More Random-Access Memory (RAM)](assigning-more-ram.md)
Use when: raising the maximum memory pool of the integration framework Tomcat for high message load.
Terms: `tomcat<version>.exe`, *Java* tab, maximum memory pool, `2048` MB, *Run as Administrator*, `IntegrationServer\tomcat\bin`

## [Changing Integration Framework Server Ports](changing-server-ports.md)
Use when: port 8080 or 8443 is already in use; changing the framework http/https ports and keeping the event sender in sync.
Terms: `8080`, `8443`, `server.xml`, `connector port`, *Cfg Runtime*, *Configuration*, `SLSPP` table, *Framework Server Port*, SAP Business One Event Sender Service, SAP Business One Integration Service
Not here: all default ports (sec 15.1) → [default-ports](../appendix/default-ports.md)

## [Changing Event Sender Settings](event-sender-settings.md)
Use when: changing the database password, B1iadmin password or server for the event sender; including or excluding objects and users; event sender setup wizard.
Terms: event sender, `SEVT` table, *Setup Wizard*, *DB Server Name*, *Setup DB Account*, *Running DB Account*, *Idle Time (millisecond)* `3000`, *Batch Count*, *Sending Method* `Distributed`, *Protocol Type*, *Server Authentication*, `b1i.jks`, `.keystore`, *Include List B1 Object(s)*, *Exclude List B1 Object(s)*, *Exclude List B1 User*, *Create Complete Journal Entry Events*, *Deploy*, `datasource.properties`, `eventsenderconfig.properties`
Sections: [Procedure](event-sender-settings.md#procedure) · [Results](event-sender-settings.md#results)

## [Changing SAP Business One DI Proxy Settings](di-proxy-settings.md)
Use when: tuning the DI Proxy through `diproxyserver.properties`: ports, restart on errors, orphaned transactions, JCo path.
Terms: `diproxyserver.properties`, `RMI_PORT`, `HTTPS_PORT`, `MAXDIERRORS`, `RESTARTPERIOD`, `ORPHANED`, `JCOPATH`, `JCOVERSION`, `restartAttemptDelay`, `restartAttemptCap`, DI Proxy version 30002211, SAP Business One DI Proxy Service
Not here: several proxies and groups → [proxy-groups](proxy-groups.md)

## [Using Proxy Groups](proxy-groups.md)
Use when: load-balancing DI requests across several DI proxies; installing a second DI proxy service; defining groups in the B1DI adapter; referencing a group in SLD.
Terms: proxy group, `DIProxy2`, `service.ini`, `ServiceName = SAPB1iDIProxy2`, `service.exe -install`, `HTTPS_PORT=2098`, *Global Adapter Config*, *B1DI*, `diProxyGroupList`, `diProxyhost`, `diProxyport`, `[alpha abc:2099 def:3701]`
Sections: [Further proxies](proxy-groups.md#providing-further-proxies) · [Global configuration](proxy-groups.md#adding-proxy-groups-to-the-di-adapter-global-configuration) · [SLD](proxy-groups.md#using-proxy-groups-in-sld)
Not here: single proxy settings → [di-proxy-settings](di-proxy-settings.md)

## [Integration Framework-Related Information About Dashboard Widgets for the Cockpit](dashboard-widgets-information.md)
Use when: Cockpit dashboard widgets show errors (framework version 1).
Terms: `401 not authorized`, `404 file not found`, `DASHBOARD`, B1i user password, Adobe Flash Player 10.0, Dashboard widgets
Not here: B1i user licenses → [maintenance-monitoring-and-security](maintenance-monitoring-and-security.md#licensing)
