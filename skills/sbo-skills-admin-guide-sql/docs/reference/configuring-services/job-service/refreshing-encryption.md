---
title: Refreshing Encryption
source: pdf pp. 115-115, sec 9.2.2.3
summary: Manually triggering the refresh of all encryption keys from the Job Service Web page.
---

# Refreshing Encryption

**Context**

On the Job Service Web page, you can manually trigger the refresh of all encryption keys to proactively update all encryped fields within companies. This process applies not only to static keys but also to dynamic keys generated from the SLD control center.

**Procedure**

1. In a Web browser, navigate to the following URL:

   ```text
   https://<Server Address>:<Port>/job
   ```

   Alternatively, on the *Services* tab in the system landscape directory, you can click the *Job Service* link to access the settings.

   > **Note**
   >
   > - If you use a proxy for your internet connection, you must add the full hostname or IP address of any Web server (for example, SLD) to the proxy exception list of your Web browser; in other words, do not use a proxy for these addresses.
   > - The URL of the service is case-sensitive.
   > - On the *Services* tab in the System Landscape Directory, make sure that the job service is already bound to a database instance which is registered in the SLD control center.

2. If you have not logged in to the SLD service, in the login page, enter the landscape administrator name (`B1SiteUser`) and password, and then choose *Log In*.

   > **Note**
   >
   > The landscape administrator name is case-sensitive.

3. On the SAP Business One Job Service page, choose *Refresh Encryption*.

**Related Information**

[Enabling Dynamic Keys](../../system-landscape-directory/dynamic-keys.md#enabling-dynamic-keys) [page 89]
