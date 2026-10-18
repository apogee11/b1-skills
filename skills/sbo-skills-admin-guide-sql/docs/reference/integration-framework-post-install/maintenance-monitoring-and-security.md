---
title: Maintenance, Monitoring and Security, Technical B1i User, Licensing
source: pdf pp. 148-149, sec 9.7.2, 9.7.3, 9.7.4
summary: Monitoring the integration framework, SLD entries, the event subscriber for NetWeaver integration, security guide pointers, the technical B1i user and its required licenses.
---

# Maintenance, Monitoring and Security, Technical B1i User, Licensing

- [Maintenance, Monitoring and Security](#maintenance-monitoring-and-security)
- [Technical B1i User](#technical-b1i-user)
- [Licensing](#licensing)

## Maintenance, Monitoring and Security

### Monitoring

For technical monitoring purposes in framework version 1, enter the IP address or host name and the port, choose the framework version link.

- For framework version 1, choose *Monitoring*. You can use the message log, access the error inbox, display SAP Business One (B1) events and use other monitoring functions. By default, the message log is active after installation. We recommend deactivating the message log in a productive environment. For additional documentation, choose *Help* > *Documents* > *Operations Part 1* and *Operations Part 2*.
- For framework version 2, choose *Monitoring*. You can use the transaction monitor, access the error inbox, the service monitor, scenario queue monitor, and so on. For additional documentation, choose *Help* > *Documents* > *Operations*.

### System Landscape Directory (SLD)

> **Note**
>
> Do not confuse the SLD for the integration framework with the SLD for the SAP Business One landscape, which you access from a Web browser.

Integration framework version 1 and 2 share the SLD. To maintain systems connecting to the integration framework, choose *Start* > *All programs* > *Integration Framework for SAP Business One* > *Integration Framework*, and then choose *SLD*.

For all integration packages, SAP delivers the necessary system entries in SLD.

In SLD, make sure that you keep the entry in the *b1Server* field for the SAP Business One system in sync with the entry in the *associatedSrvIP* field for the *WSforMobile* system.

### Integration with SAP Business One integration for SAP NetWeaver

If your SAP Business One is connected as a subsidiary to the SAP Business One integration for SAP NetWeaver server, it is necessary to add entries to the event subscriber manually.

To configure the SAP Business One event subscriber to send events to a remote integration framework server, choose *Start* > *All programs* > *Integration Framework for SAP Business One* > *Integration Framework*, and then choose *Maintenance* > *Cfg B1 Event Subscriber*.

For more information, click the documentation (Book) icon in the function.

### Security Information

The integration framework security guide gives you information that explains how to implement a security policy and provides recommendations for meeting security demands for the integration framework.

For more information in framework version 1, enter the IP address or host name and the port, choose the framework version link, and choose *Help* > *Documents* > *Operations: Performance, Security, Sizing* section *Security*.

For framework version 2, choose *Help* > *Documents* > *Operations: Performance and Security*.

## Technical B1i User

SAP Business One creates a user with the `B1i` user code for each company database. The default process requires that you set the same password for each company database. The integration framework uses the `B1i` user to connect toSAP Business One (for example, to check authentication when using the mobile solution). Ensure that the password that you provided during installation of the integration framework is the same you set in SAP Business One.

## Licensing

Ensure that the SAP Business One `B1i` user has been assigned with the following two free licenses:

- B1iINDIRECT_MSS
- B1i

No additional licenses are required for the `B1i` user.

Mobile users must be licensed to access the SAP Business One system through the mobile channel. License administration is integrated with the SAP Business One user and license.
