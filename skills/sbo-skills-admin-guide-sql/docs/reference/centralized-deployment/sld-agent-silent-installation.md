---
title: Installing the SLD Agent Silently
source: pdf pp. 170-171, sec 10.2.1.2
summary: The command line, property file format and parameters for installing or upgrading the SLD Agent in silent mode.
---

# Installing the SLD Agent Silently

You can install (or upgrade) the SLD Agent in silent mode using command-line arguments and passing parameters from a pre-filled property file. To do so, enter the following command line:

```text
install-console.exe -i silent -f <property file path> [--debug]
```

**Property File Format**

The property file is a text file with a simple structure `[Parameter]=[Value]`. Each parameter is in a separate line.

For multiple values, you need separate parameter values separated by a comma. The format is as below:

- Single value: `Parameter=Value`
- Multiple values: `Parameter=Value1, Value2`

> **Example**
>
> ```text
> SELECTED_FEATURES=B1SLDAgent
> ```

**Parameters**

The table below lists all the parameters that are required for SLD Agent installation.

<!-- table: t171-01 -->
- **Parameter**: `INSTALLATION_FOLDER`
  - **Description**: Installation path for SLD Agent installation (Default path: `C:\Program Files\SAP\SAP Business One SLD Agent\`
- **Parameter**: `LOCAL_ADDRESS`
  - **Description**: The network address of the current machine. This address will be used for registration and identification of the logical machine in SLD.
- **Parameter**: `SELECTED_FEATURES`
  - **Description**: The only supported value is `B1SLDAgent`
- **Parameter**: `SLD_SERVER_ADDR`
  - **Description**: Landscape server address.
- **Parameter**: `SLD_SERVER_PORT`
  - **Description**: Landscape server port number.
- **Parameter**: `SITE_USER_ID`
  - **Description**: Landscape administrator name that will be used to access the System Landscape Directory (for example, `B1SiteUser`).
- **Parameter**: `SITE_USER_PASSWORD`
  - **Description**: Password for the specified landscape administrator.

**Result**

When the SLD Agent is locally installed on a logical machine, the machine is registered in the SLD control center. You can find the machine record in the *Logical Machines* area in the SLD control center.
