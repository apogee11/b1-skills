# Reconfiguring the System

## [Reconfiguring the System](reconfiguring-components.md)
Use when: changing addresses, ports, certificates, SLD address, license server node type or database connection after installation; enabling certificate verification; reconfiguring Server Tools, Service Layer, Web client, Webhook Messenger, Electronic Document Service or SLD Agent with the Components Wizard.
Terms: *SAP Business One Components Wizard*, `C:\Program Files\SAP\SAP Business One SetupFiles\`, `setup.exe`, *Reconfiguration*, *Certificate Verification Settings*, SAP Note 3520401, *Port for Server Tools*, *Port for License Service*, *Port for Job Service*, *Authentication Service Port*, `B1SiteUser`, *Specify Security Certificate*, *Use Self-Signed Certificate*, *Landscape Server*, *License Server Node Type*, *Database Server Specification*, *Web Client Port*, *Service Databases*, *System Landscape Directory Schema*, *Reconfiguration Status*
Sections: [Settings table](reconfiguring-components.md#context) · [Procedure](reconfiguring-components.md#procedure)
Not here: only the Browser Access certificate → [reconfiguring-browser-access-service](reconfiguring-browser-access-service.md); default ports (sec 15.1) → [default-ports](../appendix/default-ports.md)

## [Reconfiguring the Browser Access Service](reconfiguring-browser-access-service.md)
Use when: replacing the Browser Access certificate (10.0 SP 2605 and later), including silent mode.
Terms: *Reconfigure or Remove the Program*, *Parameters for Browser Access Service*, `IS_MAINT_MODIFY=1`, `CertFile`, `CertPass`, `GK_PARAMS`, `setup.exe /s`, PowerShell, self-signed certificate, SAP Business One Browser Access Server Gatekeeper
Not here: URL, process counts or service restart for Browser Access → [browser-access-service](../demo-databases-and-external-access/external-access/browser-access-service.md); the other components → [reconfiguring-components](reconfiguring-components.md)
