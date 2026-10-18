---
title: Reconfiguring the Browser Access Service
source: pdf pp. 162-162, sec 9.8.1
summary: How to change the security certificate of the Browser Access Service through reconfiguration, including the silent PowerShell variant.
---

# Reconfiguring the Browser Access Service

## Context

As of SAP Business One 10.0 SP 2605, you can update security certificates for the Browser Access Service by performing a reconfiguration using the InstallShield Wizard.

> **Note**
>
> In the Browser Access Service reconfiguration mode, you can only change the security certificate.

## Procedure

1. On your Windows server, in the *Programs and Features* (*Control Panel* > *Programs* > *Programs and Features*), select *SAP Business One Browser Access Server Gatekeeper* and choose *Uninstall*.
2. In the *Reconfigure or Remove the Program* window, select *Reconfigure* and choose *Next*.
3. In the *Parameters for Browser Access Service* window, import a valid PKCS12 certificate and enter the password.
4. In the *Ready to Apply Changes* window, choose *Install*.

## Results

The security certificate is changed.

> **Note**
>
> To perform a **silent** reconfiguration of the certificate in the Browser Access Service, run PowerShell as Administrator and execute the following command in the folder where the `setup.exe` installation file is located:
>
> ```powershell
> $env:GK_PARAMS =
> "IS_MAINT_MODIFY=1`nCertFile=<CertificateFilePath>`nCertPass=<CertificatePassword
> >"; ./setup.exe /s
> ```
>
> If the value of `CertFile` is not specified and left blank, the installer will automatically generate a new self-signed certificate and replace the existing one.
