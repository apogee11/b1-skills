---
title: User Authentication
source: pdf pp. 215-216, sec 12.2.4
summary: How SAP Business One authenticates users by account and password, and how the Identity and Authentication Management service provides SSO through identity providers.
---

# User Authentication

As standard practice, SAP Business One authenticates users based on their user accounts and passwords. You can change your password at any time. For more information about working with passwords in SAP Business One, see [Changing Passwords](user-and-company-user-management.md#changing-passwords) [page 212].

Simultaneously, SAP Business One supports single sign-on (SSO) functionality by using the Identity and Authentication Management (IAM) service.

## Identity and Authentication Management

As of 10.0 FP 2208, SAP Business One supports the identity and authentication management service. An identity provider is a trusted provider that lets you use single sign-on (SSO) to access other websites. SSO enhances usability by reducing password fatigue. It also provides better security by decreasing the potential attack surface.

You can configure the identity providers and user bindings from the SAP Business One System Landscape Directory (SLD) control center by using the following approaches:

- SAP Business One authentication service After activating the built-in identity provider SAP Business One Authentication Server and binding company users, you can use the landscape-level unified users to log in to SAP Business One.
- Microsoft Windows domain account authentication If you have enabled the domain user authentication during the installation of the System Landscape Directory, you can find this option when logging into the SLD.
- OpenID Connect (OIDC) You can add an external identity provider by choosing the protocol OpenID Connect (OIDC). OIDC allows clients to confirm an end user's identity using authentication by an authorization server. With OIDC, you can use a single and existing account (from identity providers such as Microsoft, Google, and Amazon) to sign into SAP Business One and further strengthen security by leveraging from IDP’s features, such as two-factor authentication (2FA), without ever needing to create another username and password.

When binding users in the SLD control center, you can perform the central user management actions, such as resetting user passwords, activating or deactivating user accounts, which effects all bound users across companies in SAP Business One.

For more information about the identity and authentication management service, see *Identity and Authentication Management in SAP Business One* on SAP Help Portal (https://help.sap.com/viewer/p/SAP_BUSINESS_ONE_PRODUCT_LINE).
