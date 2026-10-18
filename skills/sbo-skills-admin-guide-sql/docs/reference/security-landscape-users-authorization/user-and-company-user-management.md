---
title: SAP Business One User and Company User Management
source: pdf pp. 210-213, sec 12.2.3.2, 12.2.3.3
summary: Managing SAP Business One users in the SLD and company users in the client: defining, updating, deleting users and changing passwords, including the password policy.
---

# SAP Business One User and Company User Management

- [SAP Business One User Management](#sap-business-one-user-management)
- [Company User Management](#company-user-management)
- [Defining Users](#defining-users)
- [Updating Users](#updating-users)
- [Deleting Users](#deleting-users)
- [Changing Passwords](#changing-passwords)

## SAP Business One User Management

In the System Landscape Directory control center, you can add, edit, or delete SAP Business One users or bind SAP Business One users to company users or copy user mappings. For more information, see [Managing Users](../system-landscape-directory/managing-users.md) [page 98].

## Company User Management

In SAP Business One, you can define, change, or delete company users or change passwords according to different business role requirements.

The company user ID and password are hashed with algorithm SHA256 and saved in the company database.

## Defining Users

To define users, start the SAP Business One client A and navigate to the *Users-Setup* window. For more information about defining users, see the online help of SAP Business One.

## Updating Users

**Context**

To update a defined user, do the following:

**Procedure**

1. Log in to the SAP Business One client.
2. From the SAP Business One *Main Menu*, choose *Administration* > *Setup* > *General* > *Users*.
3. In the *Users-Setup* window, click the *Find* button on the toolbar and switch to *Find* mode.
4. Navigate to the user you want to update.
5. Update the user’s information and click the *Update* button.

## Deleting Users

**Prerequisites**

- You have removed the licenses assigned to the user you want to delete. For more information, see the SAP Business One online help.
- You have unbound the employee associated to the user you want to delete. For more information, see the SAP Business One online help.

**Context**

To delete a defined user, do the following:

**Procedure**

1. Log in to the SAP Business One client.
2. From the SAP Business One *Main Menu*, choose *Administration* > *Setup* > *General* > *Users*.
3. In the *Users-Setup* window, click the *Find* button on the toolbar and switch to *Find* mode.
4. Navigate to the user you want to delete.
5. Right-click anywhere in the *Users-Setup* window and choose *Remove*.

**Results**

The user is deleted, and it is not possible to add a new user with the same user code.

> **Note**
>
> When you remove a company regular user in SAP Business One, the user is just marked as *Removed* but is not completely deleted from the database. If you have any requirement for data protection and privacy, see *How to Manage the Protection of Personal Data in SAP Business One* on SAP Help Portal (https://help.sap.com/viewer/p/SAP_BUSINESS_ONE_PRODUCT_LINE).

## Changing Passwords

As standard practice, SAP Business One authenticates users based on their user accounts and passwords.

You can change your password at any time. In addition, the application checks the password validity of each logon attempt according to the selected security level.

> **Note**
>
> To change your password, choose *Administration* > *Setup* > *General* > *Security* > *Change Password*.

If you are required to change your password, the application displays the *Change Password* window. You must change the password to log in.

The new password must comply with the settings of the selected security level, containing at least:

- x characters
- x lowercase
- x uppercase
- x digits
- x non-alphanumeric

The application saves passwords in the database in encrypted form. The last *n* passwords are also encrypted. When appraising a new password, the application first encrypts and then compares it with the saved ones.

The password policy defines global guidelines and rules for password settings, such as the following:

- Time interval between password changes
- Required and forbidden letters and characters
- Minimum required number of characters
- Number of logon attempts before the system locks the user account

The password policy improves the security of SAP Business One and enables administrators to apply the required security level for their organization.

> **Note**
>
> Only a superuser can change the security level. You can use the *Password Administration* window to change the security level. To open the window, choose *Administration* > *Setup* > *General* > *Security* > *Password Administration*.

SAP Business One supports the following approaches to raising the security level of user authentication:

- Increase the complexity of the password.
- Increase the frequency of password changes.

For more information about working with passwords in SAP Business One, see Password Administration (https://help.sap.com/docs/SAP_BUSINESS_ONE/68a2e87fb29941b5bf959a184d9c6727/4506b8947d720487e10000000a155369.html) and SAP Note 978292 (https://me.sap.com/notes/978292).
