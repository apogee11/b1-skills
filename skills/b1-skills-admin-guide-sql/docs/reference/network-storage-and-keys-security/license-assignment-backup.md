---
title: Backing Up and Restoring the License Assignment
source: pdf pp. 229-229, sec 12.5.3
summary: How to back up and restore the license assignment file and license files of the license service.
---

# Backing Up and Restoring the License Assignment

To secure your data, we recommend that you back up your license assignment after you finish installing the server tools and the SAP Business One server.

If the server on which you install the server tools crashes or is corrupted, you must restore the license assignment after the new license server is started.

**Procedure**

**Backing up the License Assignment**

1. Stop the server tools.
2. Copy the license assignment file `B1Upf.xml` in the path `C:\Program Files\SAP\SAP Business One ServerTools\License Service\webapps\lib` to the backup storage.
3. Copy the license files, such as `B1LicenseFile-<installation number>.txt` in the path `C:\Program Files\SAP\SAP Business One ServerTools\License Service\webapps\lib` to the backup storage.
4. Start the server tools.

**Restoring the License Assignment**

1. Stop the server tools.
2. Copy the license assignment file `B1Upf.xml` from the backup storage to the installation folder `C:\Program Files\SAP\SAP Business One ServerTools\License Service\webapps\lib`.
3. Copy the license files, such as `B1LicenseFile-<installation number>.txt` from the backup storage to the installation folder `C:\Program Files\SAP\SAP Business One ServerTools\License Service\webapps\lib`.
4. Start the server tools.
