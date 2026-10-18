---
title: Service Layer (post-installation)
source: pdf pp. 117-117, sec 9.2.5
summary: Prerequisites for starting to work with the Service Layer after installation, including the required SQL object privileges.
---

# Service Layer (post-installation)

After the installation, to start working with the Service Layer, ensure that the `SBO-COMMON` database and your company database are installed or upgraded to the same version. In addition, the SAP MSSQL database user used for connection must have the following SQL object privileges:

- `SBO-COMMON` database: `SELECT`, `INSERT`, `DELETE`, `UPDATE`, `EXECUTE` (all grantable)
- Company database: Full privileges
