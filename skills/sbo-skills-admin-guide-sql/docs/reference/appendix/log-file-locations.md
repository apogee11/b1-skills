---
title: Log File Locations for SAP Business One Components
source: pdf pp. 274-278, sec 15.2
summary: Installation and runtime log file paths for each SAP Business One server tool, server component, add-on, client component and integration component.
---

# Log File Locations for SAP Business One Components

- [Server Tools](#server-tools)
- [Server Components](#server-components)
- [Add-ons](#add-ons)
- [Client Components](#client-components)
- [Integration Solution](#integration-solution)
- [Others](#others)

The following table lists the paths to Installation and runtime log files for various SAP Business One components and services.

<!-- table: t274-02 -->
## Server Tools

- **Component**: System Landscape Directory (SLD)
  - **Installation Log Path**: `C:\Users\<user>\AppData\Local\SAP\SAP Business One\Log\B1WinInstaller_xxxxxx.txt`
  - **Runtime Log Path**: `%programdata%\sap\SAP Business One\Log\SAP Business One ServerTools\System Landscape Directory\`
- **Component**: Extension Manager
  - **Installation Log Path**: `C:\Users\<user>\AppData\Local\SAP\SAP Business One\Log\B1WinInstaller_xxxxxx.txt`
  - **Runtime Log Path**: `%programdata%\sap\SAP Business One\Log\SAP Business One ServerTools\System Landscape Directory\`
- **Component**: License Service
  - **Installation Log Path**: `C:\Users\<user>\AppData\Local\SAP\SAP Business One\Log\B1WinInstaller_xxxxxx.txt`
  - **Runtime Log Path**: `%programdata%\sap\SAP Business One\Log\SAP Business One ServerTools\License\`
- **Component**: Data Interface Server (DI Server)
  - **Installation Log Path**: `C:\Users\<user>\AppData\Local\SAP\SAP Business One\Log\B1WinInstaller_xxxxxx.txt`
  - **Runtime Log Path**: `%programdata%\sap\SAP Business One\Log\SAP Business One ServerTools\DI_Server\`
- **Component**: Workflow Service
  - **Installation Log Path**: `C:\Users\<user>\AppData\Local\SAP\SAP Business One\Log\B1WinInstaller_xxxxxx.txt`
  - **Runtime Log Path**: `%programdata%\sap\SAP Business One\Log\SAP Business One ServerTools\Workflow\`
- **Component**: Job Service
  - **Installation Log Path**: `C:\Users\<user>\AppData\Local\SAP\SAP Business One\Log\B1WinInstaller_xxxxxx.txt`
  - **Runtime Log Path**:

    - `%programdata%\SAP\SAP Business One\Log\SAP Business One ServerTools\Job Service` (9.3)
    - `C:\Program Files\SAP\SAP Business One ServerTools\Common\tomcat\logs b1servertools-stdout.yyyy-mm-dd.log` (9.2)

- **Component**: Microsoft 365 Integration
  - **Installation Log Path**: `: C:\Users\<user>\AppData\Local\SAP\SAP Business One\Log\B1WinInstaller_xxxxxx.txt`
  - **Runtime Log Path**: `%programdata%\SAP\SAP Business One\Log\SAP Business One ServerTools\B1ServerTools64MS365Integration\ms365i`
- **Component**: SLD Agent
  - **Installation Log Path**: `C:\Users\<user>\AppData\Local\SAP\SAP Business One\Log\B1WinInstaller_xxxxxx.txt`
  - **Runtime Log Path**: `%LOCALAPPDATA%\SAP\SAP Business One\Log\SLDAgent`

## Server Components

- **Component**: Repository
  - **Installation Log Path**: `C:\Windows\SAP Business One Server.log`
- **Component**: Outlook Integration Server
  - **Installation Log Path**: `C:\Windows\Add-On Server Installer (32*-bit).log`
- **Component**: Remote Support Platform (RSP)
  - **Installation Log Path**: `C:\ProgramData\SAP\SAP Business One\Log\Remote Support Platform\Installer\RSP.Install.YYYYMMDD_XXXXXX.log`
  - **Runtime Log Path**: `%programdata%\sap\SAP Business One\Log\Remote support platform for SAP Business One\`
- **Component**: Service Layer
  - **Installation Log Path**: `C:\Users\<user>\AppData\Local\SAP\SAP Business One\Log\B1WinInstaller_xxxxxx.txt`
  - **Runtime Log Path**: `C:\Program Files\SAP\SAP Business One ServerTools\ServiceLayer\logs`
- **Component**: Web Client
  - **Installation Log Path**: `C:\Users\<user>\AppData\Local\SAP\SAP Business One\Log\B1WinInstaller_xxxxxx.txt`
  - **Runtime Log Path**: `C:\Program Files\SAP\SAP Business One Web Client\logs`
- **Component**: Webhook Messenger
  - **Installation Log Path**: `C:\Users\<user>\AppData\Local\SAP\SAP Business One\Log\B1WinInstaller_xxxxxx.txt`
  - **Runtime Log Path**: `C:\Program Files\\SAP\SAP Business One\Log\SAP Business One Webhook Messenger`
- **Component**: Electronic Document Service (EDS)
  - **Installation Log Path**: `C:\Users\<user>\AppData\Local\SAP\SAP Business One\Log\B1WinInstaller_xxxxxx.txt`
  - **Runtime Log Path**:

    `%programdata%\SAP\SAP Business One\Log\SAP Business One EDS\`

    > **Note**
    >
    > As of 10.0 FP 2305, only the operating system administrator can access EDS runtime logs.

<!-- table: t276-01 -->
- **Component**: Electronic File Mapping Transformation Service
  - **Installation Log Path**: `C:\Users\<user>\AppData\Local\SAP\SAP Business One\Log\B1WinInstaller_xxxxxx.txt`
  - **Runtime Log Path**:

    `%programdata%\SAP\SAP Business One\Log\SAP Business One EDS\`

    > **Note**
    >
    > As of 10.0 FP 2608 only the operating system administrator can access Electronic File Mapping Transformation Service runtime logs.

## Add-ons

**Filename format:** `Addon_XX_YY` **(XX-Addon designation, YY-Severity Level (01-Error, 02-Warning, 03-Information))**

> **Note**
>
> Add-ons are installed in two steps. In the first step, the setup wizard only uploads add-ons to the `SBO-Common` database. In the second step, the SAP Business One client installs add-ons in the system.

- **Component**: DATEV
  - **Installation Log Path**: `C:\Windows\Add-on_Datev.log`
  - **Runtime Log Path**: `%USERPROFILE%\AppData\Local\SAP\SAP Business One\Log\Addon\Datev\`
- **Component**: Datev2LW
  - **Runtime Log Path**: `%USERPROFILE%\AppData\Local\SAP\SAP Business One\Log\Addon\Datev\`
- **Component**: EFM Format Definition
  - **Installation Log Path**: `C:\Windows\Add-on_FormatDefinition.log`
  - **Runtime Log Path**:

    `%USERPROFILE%\AppData\Local\SAP\SAP Business One\Log\Addon\Addon_EFMFD_<Sequence No.>.txt`

    As of SAP Business One 10.0 FP 2305, only administrators can read EFM Format Definition log files. Maximum limits are set on both the number and size of the log files.

    The directory folder can only contain a maximum number of 5 log files: 1 active file and 4 archived files. The maximum size for each file is 80MB. If the data in the currently active log file exceeds the maximum size, the active file is closed, renamed, and archived in the repository. Meanwhile, a new file is created and acts as the new active log file. If a new file is created when the directory folder contains 5 files, the oldest file in the folder is overwritten.

- **Component**: Fixed Assets
  - **Installation Log Path**: `C:\Windows\Add-on_FixedAssets.log`
- **Component**: Outlook Integration
  - **Installation Log Path**: `C:\Windows\Add-on_OutlookIntegration.log`
  - **Runtime Log Path**: `%USERPROFILE%\AppData\Local\SAP\SAP Business One\Log\Addon\`
- **Component**: Payment Engine
  - **Installation Log Path**: `C:\Windows\Add-on_Payment.log`
  - **Runtime Log Path**: `%USERPROFILE%\AppData\Local\SAP\SAP Business One\Log\Addon\`
- **Component**: Elster
  - **Runtime Log Path**: `%USERPROFILE%\AppData\Local\SAP\SAP Business One\Log\Addon\`
- **Component**: Screen Painter
  - **Installation Log Path**: `C:\Windows\SAP Business One Screen Painter.log`
  - **Runtime Log Path**: `%programdata%\sap\SAP Business One\Log\SAP Business One\<User>\Addon\`

## Client Components

- **Component**: SAP Business One Client
  - **Installation Log Path**: `C:\Windows\SAP Business One Client (32*-bit).log`
  - **Runtime Log Path**: `%LOCALAPPDATA%\SAP\SAP Business One\Log\BusinessOne`
- **Component**: SAP Business One Client Agent
  - **Installation Log Path**: `C:\Windows\SAP Business One Client Agent.log`
- **Component**: SAP Business One Client for Browser Access
- **Component**: Data Interface API (DI API)
  - **Installation Log Path**: `C:\Windows\SAP Business One DI API (32*-bit).log`
  - **Runtime Log Path**: `%LOCALAPPDATA%\SAP\SAP Business One\Log\DIAPI`
- **Component**: Browser Access Service (BAS)
  - **Installation Log Path**: `C:\Windows\SAP Business One Browser Access Server Gatekeeper.log`
  - **Runtime Log Path**: `%programdata%\sap\SAP Business One\Log\SAP BusinessOne BAS GateKeeper`
- **Component**: Software Development Kit
  - **Installation Log Path**: `C:\Windows\ SAP Business One Software Development Kit.log`
- **Component**: Solution Packager
  - **Installation Log Path**: `C:\Windows\SolutionPackager.log`
  - **Runtime Log Path**: `%LOCALAPPDATA%\SAP\SAP Business One\Log\Addon\`
- **Component**: Data Transfer Workbench (DTW)
  - **Installation Log Path**: `C:\Windows\Add-On Data Transfer Workbench for SAP Business One (32*-bit).log`
  - **Runtime Log Path**:

    `%USERPROFILE%\AppData\Local\SAP\SAP Business One\Log\Data Transfer Workbench\DTW.b1logger.xxx_xxx.pidxxx.log`

    > **Note**
    >
    > By default, the log entries are retained for 90 days and then deleted when DTW is closed.

- **Component**: SAP Business One Studio
  - **Installation Log Path**: `C:\Windows\SAP Business One Studio (32* bit).log`
  - **Runtime Log Path**: `%programdata%\sap\SAP Business One\Log\SAP Business One\SAP Business One Studio\`
- **Component**: User Interface API (UI API)
  - **Runtime Log Path**: `%USERPROFILE%\AppData\Local\SAP\SAP Business One\Log\UIAPI\`

## Integration Solution

- **Component**: Outlook Integration Solution
  - **Installation Log Path**: `C:\Windows\Add-On OI Standalone (32-bit).log`
  - **Runtime Log Path**:

    - OI addin: `%ProgramData%\SAP\SAP Business One\Log\Outlook Integration Log`
    - SAP Business One OI: `%ProgramData%\SAP\SAP Business One\Log\SAP Business One\<User>\Addon\`

- **Component**: Integration Framework for SAP Business One (Components)
  - **Installation Log Path**: `C:\Program Files\SAP\SAP Business One Integration\_SAP Business One Integration_installation\Logs`
  - **Runtime Log Path**:

    Troubleshooting is mostly performed using the integration framework UI (Message Log, and so on); only exceptionally done using the following log files:

    - `%programfiles%\sap\SAP Business One Integration\Tomcat\logs` (plain Tomcat logs)
    - `%programfiles%\sap\SAP Business One Integration\Tomcat\temp` (integration framework low-level logs)

    Other: DI Proxies and Event Sender also have their own logs

## Others

- **Component**: Migration Wizard
  - **Installation Log Path**: `%LOCALAPPDATA%\SAP\SAP Business One\Log\MigrationWizard`
  - **Runtime Log Path**: `%LOCALAPPDATA%\SAP\SAP Business One\Log\MigrationWizard`
- **Component**: Prerequisites
  - **Installation Log Path**: `C:\Windows\SAP Business One Prereq.log`

*: Alternatively the text is (64-bit).
