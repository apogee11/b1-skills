---
title: Configuring Browser Access Service
source: pdf pp. 140-141, sec 9.4.4
summary: Editing the Browser Access service entry in the SLD (service URL, initial, maximum and idle processes) and applying the changes.
---

# Configuring Browser Access Service

**Prerequisites**

Ensure that the date and time on the Browser Access server is synchronized with the database server.

**Context**

The Browser Access service enables remote access to the SAP Business One client in a Web browser. The Windows service name is `SAP Business One Browser Access Server Gatekeeper`.

**Procedure**

1. In a Web browser, log in to the system landscape directory using this URL: `https:// <Hostname>:<Port+10>/ControlCenter`.
2. On the *Services* tab, select the *Browser Access* entry for the particular Browser Access server and click *Edit*.
3. In the *Edit Service* window, edit the following information:
   - *Service URL*: Edit the URL used to access the service. For example, you may want to use the IP address instead of the hostname. Or the hostname, IP address, or port has changed, and you must update the service URL to reflect the changes.
   - *Initial Processes*: Specify the initial number of SAP Business One client processes that the Browser Access service hosts.
   - *Maximum Processes*: Specify the maximum number of SAP Business One client processes that the Browser Access service can host.
   - *Idle Processes*: Specify the number of standby SAP Business One client processes. When a new SAP Business One user attempts to log in, an idle process is ready for use.
   - *Description*: Enter a description for this Browser Access server.

   > **Example**
   >
   > Specify the following:
   >
   > - Initial processes: 20
   > - Maximum processes: 100
   > - Idle processes: 2
   >
   > Twenty (20) SAP Business One client processes are constantly running on the Browser Access server and allow 20 SAP Business One users to access the SAP Business One client in a Web browser at the same time.
   >
   > When the 19th SAP Business One user logs on, one (1) more SAP Business One process is started to ensure that two (2) idle processes are always running in the background.
   >
   > If more SAP Business One users attempt to access the SAP Business One client in a Web browser, more idle processes are started, but at most, 100 users are allowed for concurrent access.

4. To save the changes, choose *OK*.
5. To apply the changes immediately, on the Browser Access server, restart the SAP Business One Browser Access Server Gatekeeper service.
