---
title: Security Information for Integration Solutions (DATEV-HR, Mobile, SAP Customer Checkout, RFQ)
source: pdf pp. 251-253, sec 12.9.6, 12.9.6.1, 12.9.6.2, 12.9.6.3, 12.9.6.4
summary: Security aspects of the DATEV-HR, Mobile, SAP Customer Checkout and RFQ integration solutions, including HTTPS, license control and firewall restrictions.
---

# Security Information for Integration Solutions

- [DATEV-HR Solution](#security-aspects-related-to-the-datev-hr-solution)
- [Mobile Solution](#security-aspects-related-to-the-mobile-solution)
- [SAP Customer Checkout](#security-aspects-related-to-the-integration-with-sap-customer-checkout)
- [RFQ Scenario with Online Quotation](#security-aspects-related-to-the-rfq-scenario-with-online-quotation)

The following subsections outline the security aspects related to the following solutions:

- DATEV-HR solution
- Mobile solution
- Request for quotation (RFQ)

## Security Aspects Related to the DATEV-HR Solution

This scenario requires maximum levels of data security and sensitivity because it exports personal data. The DATEV-HR scenario generates employee data for DATEV eG using SAP Business One data. The integration framework writes the data to a specified directory in the file system. Make sure that only authorized persons have access to the folder.

Ensure that only authorized persons have access to the integration framework administration user interfaces. Alternatively, collect confirmations from all users who have access that they are aware that this data is sensitive, and that they may not distribute any data to third parties or make data accessible to non-authorized persons.

## Security Aspects Related to the Mobile Solution

After the mobile user enters the correct user name and password, the front-end application passes the mobile phone number and mobile device ID (MAC address), together with the user name and password, to the integration framework.

After receiving the information, the integration framework verifies the following:

- Whether the user is enabled as a mobile user
- Whether the necessary license is assigned to the user
- Whether it can find the telephone number and device ID pair in the SAP Business One user administration
- Whether the user name matches the telephone number and the device ID
- Whether the user has been blocked by the SAP Business One system
- Whether the provided password is correct

Only then is the user allowed to access the system.

The password is encrypted while it is transmitted to the integration framework, which decrypts the password after receiving it.

### Using HTTPS

To make communication safer, you have the option to use HTTPS for the sessions in the integration framework. On the server side you can configure the communication protocol (HTTP or HTTPS). On the client side, you have the option to switch to the HTTPS protocol. By default, the solution runs with HTTPS, and the integration framework allows incoming calls through HTTPS only.

SAP Business One mobile apps require a valid SSL certificate. For more information about obtaining and installing valid certificates, see SAP Note 2019275 (https://me.sap.com/notes/2019275).

### License Control

All mobile users have to be licensed before being allowed to access the SAP Business One system through the mobile channel. License administration is integrated with the SAP Business One user and license.

The mobile user also needs the assignment of the B1i license. Authorization within the SAP Business One application depends on the user’s SAP Business One application license.

## Security Aspects Related to the Integration with SAP Customer Checkout

All connections between SAP Customer Checkout and the integration framework are http connections that can be secured. The system landscape directory entries related to SAP Customer Checkout are 001sap0011 and 001sap0013, configured using basic authentication with user name and password.

The technical connection to the SAP Customer Checkout monitor (001sap0013) is an http connection using basic authentication.

## Security Aspects Related to the RFQ Scenario with Online Quotation

> **Note**
>
> The configuration information for the RFQ integration solution is available in the integration framework. To access the documentation, log in to the integration framework, choose *Scenarios* > *Control*, and for the `sap.B1RFQ` scenario package, choose *Docu*.

You must provide vendors included in the RFQ process access to the online purchasing document on the integration framework server.

You can accomplish this by restricting access to the server to a minimum. To restrict access to the server, configure the network (NAT) firewall as shown below:

- Only allow external access to the particular hostname / IP-address
- Only allow external access to the configured server port. Default: port `8080` for HTTP, or port `8443` for HTTPS
- If applicable and available for the particular firewall, configure the restricting URL: `http://<hostname>:<portnumber>/ B1iXcellerator/exec/ipo/vP.0010000100.in_HCSX/com.sap.b1i.vplatform.runtime/ INB_HT_CALL_SYNC_XPT/INB_HT_CALL_SYNC_XPT.ipo/proc?`
