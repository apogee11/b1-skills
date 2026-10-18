---
title: Configuration Logs and User Settings
source: pdf pp. 229-230, sec 12.5.4
summary: Where configuration changes, user settings and SLD logs are stored, which changes are logged and which are not.
---

# Configuration Logs and User Settings

In SAP Business One, configuration changes are logged in files formatted as xxx.pidxxxxx (xxx after pid can be the date, such as 20100325, so that you can find the latest log file) under `%ProgramData%\SAP\SAP Business One\Log\SAP Business One\%USERNAME%\BusinessOne`.

The configuration changes include:

- Adding/Removing users
- Changing a user to a superuser / non superuser
- Changing user passwords
- Changing user permissions
- Changing password policy
- Changing company details

> **Note**
>
> To find the logs containing changes to company details, do the following:
>
> 1. From the SAP Business One *Main Menu*, choose *Administration* > *System Initialization* > *Company Details*.
> 2. In the menu bar, choose *Tools* > *Change Logs*.

However, the following configurations cannot be logged:

- Changing data ownership authorizations
- Changing data ownership exceptions
- Changing license settings
- Setting Read-Only DB users

If you fail to log in to SAP Business One, the log is recorded in the Event Viewer.

As of SAP Business One 2007, any specific user settings are saved in a file named `b1-current-user.xml` under `C:\Documents and Settings\XXX(user id)\Local Settings\Application Data\SAP\SAP Business One`. In this situation, if a user changes his or her settings in SAP Business One, the changes are saved in this folder and do not affect other users' settings.

The System Landscape Directory (SLD) logs on the Windows machine: `C:\ProgramData\SAP\SAP Business One\Log\SAP Business One ServerTools\System Landscape Directory`.
