---
title: Updates and Patches for SAP Crystal Reports
source: pdf pp. 64-65, sec 6.3
summary: Why standard Crystal Reports updates must not be applied to the OEM version used with SAP Business One, how updates are delivered, and how to tell whether you use an OEM version.
---

# Updates and Patches for SAP Crystal Reports

> **Caution**
>
> Since you are using SAP Business One together with an Original Equipment Manufacturer (OEM) version of SAP Crystal Reports, do not apply standard SAP Crystal Reports file or product updates (including Hot Fixes and Service Packs) as they are not designed to work with OEM versions of SAP Crystal Reports.

File or product updates are provided in the following ways:

- Integrated runtime version: distributed together with SAP Business One
- Designer: provided separately via a dedicated folder location in the SAP Business One Software Download Center on SAP Support Portal at https://support.sap.com/b1software.

> **Note**
>
> If you are using both the integrated runtime version and the designer, make sure that they are either on the same patch or Service Pack level or that the Report Designer is on an earlier patch or Service Pack level than the Runtime version. If not, inconsistencies may occur.

To find out if you are using an OEM version of SAP Crystal Reports, start the designer and look for either of these two indicators:

- The title bar of the designer indicates SAP Crystal Reports for a certain product (such as *SAP Crystal Reports for SAP Business One*).
- In the *Help* menu, choose *About* (for example, *About Crystal Reports*). The technical support phone number in the *About Crystal Reports* box is not listed as *(604) 669 8379*.

If either of these indicators exists in your product, you are using an OEM version of SAP Crystal Reports.
