---
title: Electronic File Mapping Transformation Service: Encryption and Key Rotation
source: pdf pp. 255-257, sec 12.9.8, 12.9.8.1, 12.9.8.2, 12.9.8.3, 12.9.8.4
summary: How the Electronic File Mapping Transformation Service encrypts sensitive data, and how to schedule, run manually and verify key rotation.
---

# Electronic File Mapping Transformation Service: Encryption and Key Rotation

- [Encryption](#encryption)
- [Scheduled Periodic Key Rotation](#scheduled-periodic-key-rotation)
- [Manual Key Rotation](#manual-key-rotation)
- [Verification of Key Rotation Results](#verification-of-key-rotation-results)

The following subsections describe security details for the management of information in Electronic File Mapping Transformation Service, the protection of sensitive data used in it, and relevant administration activities.

## Encryption

Sensitive data in Electronic File Mapping Transformation Service, which persist on storage medium like disks, are encrypted for scenarios like:

- certificates used for electronic communication
- specific electronic communication secrets
- sensitive Electronic File Mapping Transformation Service settings

Symmetric encryption is applied to protect sensitive data that are in local storage. Encryption keys, which are used during encryption, are generated automatically and are not accessible to users or administrators. Encryption keys **must be** changed periodically (through key rotation), to limit any damage or exposure of encrypted data if the key becomes compromised or computable. During a new installation, sensitive content is encrypted. During upgrades, sensitive content is re-encrypted automatically. If encryption tasks fail, installations fail. During all Electronic File Mapping Transformation Service installation scenarios, automatic key rotation tasks are scheduled to regularly re-encrypt sensitive content. **Periodic key rotation is mandatory**. Administrators can start key rotations manually, using tools that are described in Manual Key Rotation (https://help.sap.com/viewer/1a2fc202f7f64336abf9fbc957d9b9ba/10.0_SP_2608/en-US/d201f46fd9fe43fdb70a2f48238a55e5.html).

## Scheduled Periodic Key Rotation

Regular and periodic re-encryption of sensitive data in Electronic File Mapping Transformation Service is implemented through scheduled task. Operating system administrators can verify `EFMRotateKeyTask` scheduled task either in Task Scheduler or in PowerShell console.

Figure: The EFMRotateKeyTask scheduled task in the Task Scheduler Library.

![p256-01](../../assets/p256-01.png)

Figure: The EFMRotateKeyTask scheduled task listed by Get-ScheduledTask in a PowerShell console.

![p256-02](../../assets/p256-02.png)

Scheduled tasks are executed every thirty days at 03:00 (3 am) server time. The scheduled time interval may differ in different releases.

## Manual Key Rotation

Operating system administrators can start the re-encryption of sensitive data manually. This is strongly recommended when there is a suspicion that Electronic File Mapping Transformation Service data were compromised by an attack or for any other reason. As the first action, Electronic File Mapping Transformation Service must be stopped before the key rotation can start. After the key rotation has finished, Electronic File Mapping Transformation Service can be started again. The following three commands need to be executed in the following specific sequence:

```text
net stop SAPB1EFMTService

“C:\Program Files\SAP\SAP Business One EFM Transformation
Service\tools\EFMDeploymentTool\EFMDeploymentTool RotateKey”

net start SAPB1EFMTService
```

After all commands and the execution have finished successfully, sensitive data are re-encrypted.

## Verification of Key Rotation Results

The results of sensitive data re-encryption in Electronic File Mapping Transformation Service can be verified by operating system administrators in Electronic File Mapping Transformation Service logs.

The relevant logs are in the following files:

- for scheduled periodic key rotation: `C:\ProgramData\SAP\SAP Business One\Log\SAP Business One EFM Transformation Service\RotateKeyScheduler\RotateKey.log`
- for manual key rotation: `C:\ProgramData\SAP\SAP Business One\Log\SAP Business One EFM Transformation Service\EFMDeploymentTool\Common.log.#`

where “`#`” is a sequence number of the recent log files in the folder. Inside the files, the start of the key rotation operation is denoted by the text “`Executing encryption key rotation`”, for example:

```json
{date-and-time} INFO [ 1] [EDFBackend.EDSToolBase.DataEncryption.RotateKeyAction]:
Executing encryption key rotation
```

Various technical details follow that are specific to the re-encrypted data (including PKI, database, and settings). A successful and complete key rotation operation finishes with the text “`Encryption key rotation successfully executed`”, for example:

```json
{date-and-time} INFO [.NET TP Worker]
[EDFBackend.EDSToolBase.DataEncryption.RotateKeyAction]: Encryption key rotation
successfully executed
```

If a key rotation fails, then a corresponding error is listed in the log files.
