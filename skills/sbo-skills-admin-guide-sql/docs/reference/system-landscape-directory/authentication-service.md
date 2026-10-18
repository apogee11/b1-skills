---
title: Configuring the Authentication Service
source: pdf pp. 88-89, sec 9.1.4
summary: How to update the SLD and authentication server address and port on the Security tab, and what to do afterwards.
---

# Configuring the Authentication Service

As of 10.0 FP 2208, the internal and external addresses for the System Landscape Directory are unified. If you intend to update the SLD address, you just need to change it from the *Security* tab. In addition, you can also edit the address of the authentication address.

> **Note**
>
> If you upgrade SAP Business One from a lower version to 10.0 FP 2208 or higher, you must reconfigure the SLD and authentication server address on the *Security* tab.
>
> If you have configured a nginx reverse proxy, you need to download the updated nginx file which contains the authentication server.

**Procedure**

1. Log in to the SLD control center.
2. On the *Security* tab, in the *SAP Business One Authentication Service* area, choose *Edit*.
3. In the *Update Address* window, update the address and port number for the authentication server or SLD.

   > **Note**
   >
   > Make sure that you define a correct address for the SLD and authentication server. The whole SAP Business One landscape does not work if the address is incorrect.
   >
   > Make sure that the address is accessible to both internal and external networks. You can add a record in the DNS to make the address is accessible for the internal networks.

4. After updating the address of the authentication service, restart all component services and log in to the SLD control center again with the new network address.
