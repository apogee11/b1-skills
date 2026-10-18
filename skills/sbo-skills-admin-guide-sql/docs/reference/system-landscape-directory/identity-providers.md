---
title: Managing Identity Providers
source: pdf pp. 97-98, sec 9.1.9
summary: The identity providers SAP Business One supports (authentication server, Active Directory Domain Services, external OIDC providers) and how their registration and activation work in the SLD control center.
---

# Managing Identity Providers

As of 10.0 FP 2208, SAP Business One supports the Identity and Authentication Management (IAM) service. This service allows you to authenticate with your identity provider's user when logging into SAP Business One. Connecting SAP Business One with an identity provider can help you manage user access in a secured manner without compromising on user experience during login to SAP Business One.

You typically use only one identity provider in SAP Business One, but you have the option to add more. This section shows you how to add, delete and activate identity provider to your SLD control center.

The *Identity Providers* tab of the SLD control center displays all registered identity providers in SAP Business One, including SAP Business One authentication server, Active Directory Domain Services, and other external identity providers.

**SAP Business One Authentication Server**

It is a default identity provider. After installing SAP Business One, you can find this option when logging into the SLD.

You cannot delete the registration of SAP Business One authentication server.

**Active Directory Domain Services**

If you have enabled the domain user authentication during the installation of the System Landscape Directory, you can find this option when logging into the SLD.

You cannot delete the registration of Active Directory Domain Services.

Prior to 10.0 FP 2208, SAP Business One supports Microsoft Windows domain single sign-on (SSO) functionality. You can bind an SAP Business One user account to a Microsoft Windows domain account.

If you upgrade SAP Business One from a lower version to 10.0 FP 2208 or higher, after the upgrade, you may find the different status based on the different scenarios. For more information, see *Identity and Authentication Management in SAP Business One* on SAP Help Portal (https://help.sap.com/viewer/p/SAP_BUSINESS_ONE_PRODUCT_LINE).

**External Identity Providers**

You can register external identity providers by choosing the protocol OpenID Connect (OIDC) in the SLD control center.

You can delete the registered external IDPs.

The default status for a default or registered identity provider is *Inactive*. To enable the identity provider authentication service, you need to change the status of the identity provider to *Active* by choosing *Activate*.

> **Note**
>
> Before activating identity providers, make sure that you have created and bound IDP users to SAP Business One company users across all companies. You cannot log in to SAP Business One with company users after activating the identity provider.

You can add, delete, activate or deactivate one or more identity providers from the SLD control center. For more information, see Managing Identity Providers (https://help.sap.com/viewer/548d6202b2b6491b824a488cfc447343/10.0_SP_2608/en-US/13c565324759468490589d60e6c75a92.html) in *Identity and Authentication Management in SAP Business One*.
