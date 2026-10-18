# Centralized Deployment

## [Centralized Deployment Overview and Registering the Installation CD](registering-installation-cd.md)
Use when: what can be done remotely from the SLD control center; defining the CD repository and the central log directory; setting the SLD Agent heartbeat and operation timeouts; enabling verbose logging.
Terms: centralized deployment, central management, *Global Settings* tab, *Central Deployment* area, *CD Repository*, *Central Log Directory*, *Share Settings*, *Share Type*, *Network Path*, `\\<IP address>\B1_SHR`, *Access User Name*, *SLD Agent Heartbeat Timeout*, *SLD Agent Operation Timeout*, *Verbose Logging*, shared folders
Sections: [Registering the installation CD](registering-installation-cd.md#registering-sap-business-one-installation-cd)
Not here: SLD control center login and the other SLD tabs → [system-landscape-directory](../system-landscape-directory/index.md)

## [Registering Logical Machines and Installing the SLD Agent with the Wizard](sld-agent-wizard-installation.md)
Use when: registering a machine in the SLD as a logical machine; installing the SLD Agent manually with the Components Setup Wizard; prerequisites for the SLD Agent; why only `B1SiteUser` can continue the installation.
Terms: logical machine, SLD Agent, Components Setup Wizard, `Install.exe`, `Install-console.exe`, `\Packages.x64\ComponentsWizard`, *Installation and Upgrade*, *Select Features*, *Network Address*, *Landscape Server* window, `B1SiteUser`, Windows PowerShell 5, *Save Settings*, SAP Note 1492196, UAC
Sections: [Registering and unregistering logical machines](sld-agent-wizard-installation.md#registering-and-unregistering-logical-machines) · [Prerequisites](sld-agent-wizard-installation.md#manually-installing-sld-agent-service) · [Wizard procedure](sld-agent-wizard-installation.md#wizard-installation)
Not here: installing the SLD itself and the server components → [server-components-installation](../installing-server-components/server-components-installation.md); upgrading the SLD Agent → [upgrade-process-overview](../upgrade-process/upgrade-process-overview.md)

## [Installing the SLD Agent Silently](sld-agent-silent-installation.md)
Use when: installing or upgrading the SLD Agent from the command line with a property file.
Terms: `install-console.exe -i silent -f <property file path> [--debug]`, property file, `INSTALLATION_FOLDER`, `LOCAL_ADDRESS`, `SELECTED_FEATURES`, `B1SLDAgent`, `SLD_SERVER_ADDR`, `SLD_SERVER_PORT`, `SITE_USER_ID`, `SITE_USER_PASSWORD`, `C:\Program Files\SAP\SAP Business One SLD Agent\`
Not here: silent installation of the client → [installing-client-components](../installing-client-components/index.md); silent upgrade of server components → [silent-upgrade](../upgrade-process/silent-upgrade.md)

## [Uninstalling the SLD Agent Service](uninstalling-sld-agent-service.md)
Use when: removing the SLD Agent from a logical machine, which unregisters the machine in the SLD control center.
Terms: *Programs and Features*, *SAP Business One SLD Agent*, `setup.exe`, `C:\Program Files\SAP\SAP Business One SetupFiles\setup.exe`, unregistered
Not here: uninstalling SAP Business One client and DI API from the SLD control center → [client-components](client-components.md#uninstalling-client-components); uninstalling SAP Business One and its add-ons → [crystal-reports-and-uninstalling](../crystal-reports-and-uninstalling/index.md)

## [Installing and Uninstalling Client Components](client-components.md)
Use when: remotely deploying the SAP Business One client and Data Interface API on registered logical machines; removing them from the SLD control center; reading the deployment status.
Terms: *Logical Machines* tab, *SAP Business One Components* area, *Deploy*, *Remove*, *Select Components*, *Remove and Uninstall Components*, *Deployment Status*, *To be deployed*, *Deploying*, *Deployed*, *Deployed Externally*, *Components* tab, DI API
Sections: [Installing](client-components.md#installing-client-components) · [Uninstalling](client-components.md#uninstalling-client-components)
Not here: installing the client locally on a workstation → [installing-client-components](../installing-client-components/index.md)

## [Registering Database Instances on the Landscape Server](registering-database-instances.md)
Use when: companies do not appear on the logon screen; adding a database server to the SLD control center.
Terms: `https://<Server Address>:<Port>/ControlCenter`, *DB Instances and Companies* tab, *DB Instances* area, *Add Server*, *Server Name*, FQDN, *Database User Name*, *Database User Password*, special characters in server name, landscape administrator name is case sensitive
Not here: adding services (Job Service, License Control Center) to the SLD → [adding-services](../system-landscape-directory/adding-services.md)

## [Deploying and Upgrading Databases](deploying-and-upgrading-databases.md)
Use when: remotely deploying `SBOCOMMON` and demo databases from the SLD control center; upgrading `SBOCOMMON` and company databases remotely; locking a company before an upgrade.
Terms: *Deploy*, *Upgrade*, *Selection of Databases*, *Setup Type*, *Perform Setup*, *Backup Settings*, *Lock*, *Unlocked*, *Locked*, *Ready* status, *Review* window, `SBOCOMMON`, CD repository, landscape administrators lock companies
Sections: [Deploying](deploying-and-upgrading-databases.md#deploying-databases) · [Upgrading](deploying-and-upgrading-databases.md#upgrading-databases)
Not here: the upgrade procedure run with the setup wizard on the server → [upgrading-databases-and-components](../upgrade-process/upgrading-databases-and-components.md); restoring and maintaining databases → [maintaining-databases](../maintaining-databases/index.md)
