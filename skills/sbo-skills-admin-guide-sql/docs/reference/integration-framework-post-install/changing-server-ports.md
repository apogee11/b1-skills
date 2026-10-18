---
title: Changing Integration Framework Server Ports
source: pdf pp. 150-151, sec 9.7.6
summary: How to change the default http (8080) and https (8443) ports of the integration framework server and keep the event sender in sync.
---

# Changing Integration Framework Server Ports

## Context

By default, the integration framework server uses port `8080` for http and `8443` for https. If another application is already using one of these ports, change the integration framework ports.

## Procedure

1. If *SAP Business One Event Sender Service* is already running, stop the service.
2. In the `…\Program Files (x86)\SAP\ Integration Framework for SAP Business One\IntegrationServer\Tomcat\conf` folder, double-click the `server.xml` Tomcat file and in the `connector port` tag, change the settings as necessary. Do not change any other settings in the file.
3. Log in to the integration framework.
4. For framework version 1, choose *Maintenance* > *Cfg Runtime* and change the port or ports.

   For framework version 2, choose *Maintenance* > *Configuration* and change the port or ports.

   The integration framework also updates the setting in the `SLSPP` table in SAP Business One.

5. Restart the *SAP Business One Integration Service*.
6. Choose *Start* > *All programs* > *Integration Framework for SAP Business One* > *Integration Framework* > *Tools* > *Event Sender*, click *Setup Wizard*, and follow the steps of the wizard. In the *Configure Integration Framework Parameters* section, change the *Framework Server Port* entry, and then test the connection.
7. Restart the *SAP Business One Event Sender Service*.
8. To change the properties for the menu entry of version 1, choose *Start* > *All programs* > *Integration Framework for SAP Business One* > *Integration Framework*. Be sure to use the correct port number.
