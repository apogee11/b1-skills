---
title: "Data Encryption: SLD Dynamic Keys and Company Data"
source: pdf pp. 226-228, sec 12.5.2
summary: How SLD data is encrypted, how to create, enable and disable SLD dynamic keys, and the recommendations for encrypting company data.
---

# Data Encryption: SLD Dynamic Keys and Company Data

- [System Landscape Directory Data Encryption](#system-landscape-directory-data-encryption)
- [Creating Dynamic Keys](#creating-dynamic-keys)
- [Enabling Dynamic Keys](#enabling-dynamic-keys)
- [Disabling Dynamic Keys](#disabling-dynamic-keys)
- [Company Data Encryption](#company-data-encryption)

## System Landscape Directory Data Encryption

The sensitive data in the System Landscape Directory is encrypted. By default, encryption is performed using static keys.

We strongly recommend that you follow the instructions as follows:

- After installing the System Landscape Directory, you create and enable the dynamic keys of the sensitive data in the SLD.
- You regularly update the encryption keys and safeguard the encryption keys.

This section provides information about how to create, enable and disable dynamic keys for SLD database.

## Creating Dynamic Keys

**Procedure**

1. On a Windows computer, run the command prompt as the administrator.
2. Run the following command:

   ```text
   "<Installation Folder>\SAP\SAP Business One SetupFiles\sapmachine_17\bin\java"
   -jar "C:\Program Files\SAP\SAP Business One
   SetupFiles\support\bin\SLDInstallerTool.jar" -generateKey -keyStorePath <Path>
   -keyPassword <Password>
   ```

   For example:

   ```text
   "C:\Program Files\SAP\SAP Business One
   SetupFiles\sapmachine_17\bin\java" -jar "C:\Program Files\SAP\SAP Business
   One SetupFiles\support\bin\SLDInstallerTool.jar" -generateKey -keyStorePath
   c:\keystore.p12 -keyPassword Hello123
   ```

## Enabling Dynamic Keys

**Prerequisites**

You have regularly backed up the `SLDDATA` database and exported the dynamic keys to external storage devices.

**Procedure**

1. Stop the SAP Business One server tools.
2. On your Windows computer, navigate to the file under the folder `<Installation Folder>\SAP\SAP Business One ServerTools\System Landscape Directory\tools` (for example, `C:\Program Files\SAP\SAP Business One ServerTools\System Landscape Directory\tools`).
3. Run the following command:

   ```text
   dynamic_key_control.bat -action on
   ```
4. Specify the path of the keystore backup directory (for example, `c:\keystore.p12`).
5. Specify the keystore password and confirm the password (for example, `Hello123`).

> **Caution**
>
> Ensure that you safeguard the keystore generated in the directory (for example, you can copy the keystore to other hardware storage devices) and remember the keystore password. Otherwise, if the SLD server machine is damaged, the encrypted data cannot be restored.

6. Restart the server tools.

## Disabling Dynamic Keys

**Prerequisites**

You have backed up the `SLDDATA` database and the dynamic keys.

**Procedure**

1. On a Windows computer, run the command prompt.
2. Run the following command:

   ```text
   "<Installation Folder>\SAP\SAP Business One ServerTools\System Landscape
   Directory\tools\dynamic_key_control.bat" -action off
   ```

   For example:

   ```text
   "C:\Program Files\SAP\SAP Business One ServerTools\System Landscape
   Directory\tools\dynamic_key_control.bat" -action off
   ```

3. Restart the SLD and the authentication service.

**Results**

The encyption of the `SLDDATA` database is performed by using static keys. If you intend to use dynimic keys again, you may enable the previous keys or generate new ones.

## Company Data Encryption

The sensitive company data is encrypted. We strongly recommend that you follow the instructions as follows:

- You use the dynamic key to encrypt your company database. For more information, see [Managing Dynamic Keys for the Data in Company Databases](../system-landscape-directory/dynamic-keys.md) [page 89].
- You regularly update the dynamic key.
- When you enable or update the dynamic key, ensure that you keep the System Landscape Directory database safe.

> **Caution**
>
> Ensure you safeguard the SLD database. If the SLD database is damaged (for example, the database is lost or the hardware is broken), the encryption key of the company database will be lost.
