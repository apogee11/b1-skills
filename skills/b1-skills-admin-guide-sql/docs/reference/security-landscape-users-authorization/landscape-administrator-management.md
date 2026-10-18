---
title: Landscape Administrator Management
source: pdf pp. 208-210, sec 12.2.3*, 12.2.3.1
summary: How the landscape administrator (B1SiteUser) account works, the password recommendations, and how to change the landscape administrator password in the System Landscape Directory.
---

# Landscape Administrator Management

This section provides an overview of user administration within SAP Business One.

> **Note**
>
> As of SAP Business One 10.0 SP 2311, the passwords of landscape administrators (for example, `B1SiteUser`), database users and company users support all characters on the US-International keyboard. If you are using other language keyboards (non-US), you may encounter an error when specifying passwords with some special characters.

The landscape administrator account serves as site-level authentication for performing various administrative tasks. This section provides information about how to change the landscape administrator password.

**B1SiteUser**

The landscape super user, whose account information should be known only to a few selected system administrators, is `B1SiteUser`. You can update the password of `B1SiteUser` on the *Users* tab in the System Landscape Directory. You will need to provide the old password to make the change. For more information, see [Password Encryption](landscape-administrator-management.md#password-encryption) [page 209].

If you forget the password of the landscape user and want to reset it, you need to create a new user to log in to SAP Business One authentication service, and then reset the password. For more information, see *Identity and Authentication Management in SAP Business One* on SAP Help Portal (https://help.sap.com/viewer/p/SAP_BUSINESS_ONE_PRODUCT_LINE).

The `B1SiteUser` account cannot be removed.

**Identity Provider Users as Landscape Administrators**

You can assign appropriate identity provider users as landscape administrators to perform administrative tasks in the System Landscape Directory. For more information, see *Identity and Authentication Management in SAP Business One* on SAP Help Portal (https://help.sap.com/viewer/p/SAP_BUSINESS_ONE_PRODUCT_LINE).

## Password Encryption

In SAP Business One, a strong algorithm is used for data encryption and decryption. The landscape administrator ID and password are encrypted/hashed and saved in the System Landscape Directory.

For security reason, we recommend that the landscape administrator password be a strong password that has the following characteristics:

- Contains alphabetic, numeric, and special characters
- Is at least seven characters in length
- Is NOT a common word or name
- Does NOT contain a name or user name
- Is significantly different from previous passwords

> **Recommendation**
>
> If you have enabled single sign-on (SSO) functionality, we recommend that you bind the SAP Business One landscape administrator with a domain user. Then, when you start the SAP Business One System Landscape Directory control center, you can enter the control center without being prompted to enter the logon credentials.
>
> Alternatively, for security reasons, we recommend that you change the length of the landscape administrator password to a longer one (for example, twenty characters in length) since you do not need to use the landscape administrator password frequently.

You can change the landscape administrator password using the System Landscape Directory. To do so, proceed as follows:

1. To access the SLD service, in a Web browser, navigate to the following URL: `https://<Server Address>:<Port>/ControlCenter`
2. In the logon page, enter the landscape administrator name (`B1SiteUser`) and password, and then choose *Log In*.

> **Note**
>
> The landscape administrator name is case sensitive.

3. On the *Users* tab, select the row of `B1SiteUser` and choose *Edit*.
4. In the *Change Password* window, enter and confirm the new password you want to use.
5. To save the new password, choose *Confirm*.
6. The user will be required to change the password at the next login.

> **Note**
>
> If you have enabled the Identity and Authentication Management (IAM) service, you can follow the same steps above to change passwords for all SAP Business One authentication server users. If you intend to change passwords for external identity provider users (both landscape administrator and SAP Business One user), you must go to the relevant IDP sites to change IDP user passwords.
