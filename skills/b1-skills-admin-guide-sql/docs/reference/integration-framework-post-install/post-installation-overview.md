---
title: Post-Installation Activities for the Integration Framework
source: pdf pp. 146-147, sec 9.7*, 9.7.1
summary: What to check after installing the integration framework (Windows service, no mandatory steps) and how to log on and maintain its technical settings in framework version 1 and 2.
---

# Post-Installation Activities for the Integration Framework

After installation is complete, you can begin using the integration framework. No mandatory post-installation activities are necessary.

However, for certain use cases, you need additional settings in the integration framework. The following sections provide information about additional configuration options and settings you can check to ensure a correct setup.

> **Note**
>
> The integration framework is implemented as a Microsoft Windows service with the *SAP Business One Integration Service* identifier. The service starts automatically after successful installation.
>
> If you cannot start the integration framework, stop, and restart the service.
>
> You can locate the service by choosing *Start* > *Control Panel* > *Administrative Tools* > .

## Maintaining Technical Settings in the Integration Framework

### Context

The integration framework is available as version 1 and version 2. When entering the IP address or host name and the port in the Web browser, a Web page opens and offers you to either call framework version 1 or 2.

The integration framework version 2 offers an *Integrated Development Environment* (IDE) for integration scenario design and enables you to deploy integration scenarios for more than one customer in cloud environments.

### Procedure

1. In the Web browser, enter the IP address or host name and the port of the integration framework on the Web page, click the integration framework version link.

   The *Logon* user interface opens.

2. In the *Username* field, enter `B1iadmin` and in the *Password* field, enter the password that has been provided during installation.

   Note that entries in the *Username* field are case-sensitive.

3. To add or change integration framework technical settings, in the integration framework, choose *Maintenance*.
   - To define proxy settings for your network and provide connection information for your email server, in framework version 1, choose *Cfg Connectivity*. In framework version 2, choose *Configuration*.
   - To get an overview about configuration information for message exchange between SAP Business One and the integration framework and about integration packages setup, choose *Tools* > *Troubleshooting*, and in the *Functional Group* field, choose *B1 Setup*.

### Next Steps

For more information about maintenance functions, in the integration framework choose *Help* > *Documents* > *Operations Part 2*, section *Framework Administration* and *Tools*.

In framework version 2, choose *Help* > *Documents* > *Operations*.
