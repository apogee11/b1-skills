# Security Landscape, Users and Authorization

## [Technical Landscape](technical-landscape.md)
Use when: understanding why the SLD is the security server; where database credentials are kept; the security workflow figure; establishing a company-wide security policy.
Terms: security server, System Landscape Directory, SLD database, database credentials, common and company databases, security workflow, security policy
Not here: SLD control center tasks → [system-landscape-directory](../system-landscape-directory/index.md); which databases and folders store what → [data-storage](../network-storage-and-keys-security/data-storage.md)

## [User Types](user-types.md)
Use when: telling the four user notions apart (landscape administrator, SAP Business One user, company user, Windows domain user); which tool manages users; what `B1SiteUser` and the IDP user role can do.
Terms: landscape administrator, site user, `B1SiteUser`, SAP Business One User, IDP user, identity provider, company user, superuser, regular user, Microsoft Windows domain user, User Management Tools, bind, *Landscape Administrator*, 10.0 FP 2208
Not here: the predefined users and passwords → [standard-users](standard-users.md); SLD Users tab and binding steps → [managing-users](../system-landscape-directory/managing-users.md)

## [Standard Users](standard-users.md)
Use when: what `B1SiteUser`, `manager`, `B1i`, `Workflow` and `Support` are for; default passwords; the `Support` user licence, session timeout and log; substituting the `default standard` user.
Terms: `B1SiteUser`, `manager`, `B1i`, `Workflow`, `AlertSvc`, `Support`, company superuser, Landscape administrator, Hebrew password, *Support User Login*, *Support User Log*, System Status Report, SSR, Remote Support Platform, RSP, 4 hours, two sessions, Professional User license, `default standard`
Not here: activating the Support user in the SLD → [support-user](../system-landscape-directory/support-user.md); technical B1i user in the integration framework → [maintenance-monitoring-and-security](../integration-framework-post-install/maintenance-monitoring-and-security.md#technical-b1i-user)

## [Landscape Administrator Management](landscape-administrator-management.md)
Use when: changing the `B1SiteUser` password in the SLD; strong-password recommendation for the landscape administrator; forgotten landscape password; US-International keyboard and special characters; IDP users as landscape administrators.
Terms: `B1SiteUser`, landscape administrator password, *Users* tab, *Change Password*, `https://<Server Address>:<Port>/ControlCenter`, case sensitive, seven characters, twenty characters, US-International keyboard, 10.0 SP 2311, IAM, password encrypted, hashed
Sections: [Password Encryption](landscape-administrator-management.md#password-encryption)
Not here: managing SLD users in the control center → [managing-users](../system-landscape-directory/managing-users.md); company user passwords → [user-and-company-user-management](user-and-company-user-management.md#changing-passwords)

## [SAP Business One User and Company User Management](user-and-company-user-management.md)
Use when: defining, updating or deleting company users in the client; password policy and security level; why a removed user is only marked as Removed; user code cannot be reused; SHA256 hashing of company user passwords.
Terms: *Users - Setup*, *Find*, *Remove*, *Removed*, *Change Password*, *Password Administration*, security level, password policy, SHA256, last n passwords, logon attempts, SAP Note 978292, license removed, employee unbound
Sections: [Company user management](user-and-company-user-management.md#company-user-management) · [Defining](user-and-company-user-management.md#defining-users) · [Updating](user-and-company-user-management.md#updating-users) · [Deleting](user-and-company-user-management.md#deleting-users) · [Changing passwords](user-and-company-user-management.md#changing-passwords)
Not here: SLD user management and user mappings → [managing-users](../system-landscape-directory/managing-users.md); changing security levels → [changing-security-levels](../sbo-authentication-and-application-security/changing-security-levels.md)

## [Microsoft Windows Domain Account Authentication Enablement](windows-domain-account-authentication.md)
Use when: enabling single sign-on with Windows domain accounts; registering the SPN; copying user mappings between companies; SSO activates for all companies.
Terms: SSO, single sign-on, SPN, Service Principal Name, `setspn -U -A <SPN> <Domain User Name>`, `SLD/Domain.com`, Active Directory Domain Services, *Choose Company*, copy user mappings, user code, case sensitive domain user name, domain administrator
Sections: [Registering the SPN](windows-domain-account-authentication.md#registering-the-service-principal-name) · [Binding users](windows-domain-account-authentication.md#binding-sap-business-one-users-to-microsoft-windows-accounts) · [Copying user mappings](windows-domain-account-authentication.md#copying-user-mappings-between-companies) · [Enabling SSO](windows-domain-account-authentication.md#enabling-single-sign-on)
Not here: activating identity providers in the SLD → [identity-providers](../system-landscape-directory/identity-providers.md)

## [User Authentication](user-authentication.md)
Use when: how users authenticate (account and password versus SSO); the three identity provider approaches; what the IAM service adds.
Terms: Identity and Authentication Management, IAM, identity provider, SAP Business One Authentication Server, OpenID Connect, OIDC, 2FA, single sign-on, 10.0 FP 2208, bound users
Not here: configuring identity providers and bindings → [identity-providers](../system-landscape-directory/identity-providers.md); authentication service address → [authentication-service](../system-landscape-directory/authentication-service.md)

## [Authorization](authorization.md)
Use when: regular user versus superuser; why a new user has no authorizations; one manager per user.
Terms: authorizations, data ownership, regular user, superuser, manager, permissions
Not here: database-level restrictions → [restricting-database-access](../sbo-authentication-and-application-security/restricting-database-access.md)
