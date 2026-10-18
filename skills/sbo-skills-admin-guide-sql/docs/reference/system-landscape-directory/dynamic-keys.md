---
title: Managing Dynamic Keys for Company Databases
source: pdf pp. 89-93, sec 9.1.5
summary: Enabling, disabling, exporting and importing dynamic encryption keys for company databases in the SLD control center.
---

# Managing Dynamic Keys for Company Databases

- [Enabling Dynamic Keys](#enabling-dynamic-keys)
- [Disabling Dynamic Keys](#disabling-dynamic-keys)
- [Exporting Dynamic Keys](#exporting-dynamic-keys)
- [Importing Dynamic Keys](#importing-dynamic-keys)

SAP Business One supports configurable algorithms for company encryption. You can configure dynamic encryption settings from the SLD control center.

This section provides information about how to enable, disable, import and export dynamic keys.

## Enabling Dynamic Keys

**Prerequisites**

You have regularly backed up the `SLDDATA` database.

> **Note**
>
> Once a dynamic key is activated for a company, the action cannot be reversed. Disabling a dynamic key will only affect the encryption behavior from when the setting changes; some company data may still be encrypted by keys generated before the change.
>
> If a dynamic key is lost or becomes unavailable, the company database will no longer be accessible and data recovery may not be feasible.

**Context**

In the *Security* tab, you can globally enable dynamic key generation for companies registered in the SLD control center.

In the *DB Instances and Companies* tab, you can enable dynamic keys for selected companies.

**Procedure**

1. Log in to the SLD control center.
2. On the *Security* tab, in the *Dynamic Key Management* area, choose *Enable Dynamic Key Generation*.
3. In the pop-up window, choose *Continue* after reading and confirming the message. Now you can go to the *DB Instances and Companies* tab and enable dynimic keys for specific companies.
4. On the *DB Instances and Companies* tab, select one company and choose *Enable Dynamic Key*.
5. In the pop-up window, choose *Continue* after reading and confirming the message.

**Results**

- In the *Companies* table on the *DB Instances and Companies* tab, the *Dynamic Key Status* for the secleted companies is set to *Active*.
- In the *Dynamic Keys* table on the *Security* tab, the recently generated dynamic keys for the selected companies are listed. The status is *Active*.

> **Note**
>
> Every time you choose *Enable Dynamic Key* for a company, a new dynamic key is generated for that company. Previously generated dynamic keys remain listed in the table, but their statuses are changed to *Inactive* when the dynamic key is disabled..

**Next Steps**

If you would like to proactively update all encryped fields within companies, you can manually trigger the refresh of all encryption keys from the Job Service Web page. For more information, see [Refreshing Encryption](../configuring-services/job-service/refreshing-encryption.md) [page 115].

## Disabling Dynamic Keys

**Context**

You can disable the dynamic key for a selected company.

**Procedure**

1. Log in to the SLD control center.
2. On the *DB Instances and Companies* tab, select one company that has enabled dynamic keys.
3. Choose *Disable Dynamic Key*.

**Results**

- In the *Companies* table on the *DB Instances and Companies* tab, the value of *Dynamic Key Status* for the secleted company is blank.
- In the *Dynamic Keys* table on the *Security* tab, the dynamic key status for the selected company is *Inactive*.

> **Note**
>
> The dynamic keys previously generated for the companies still need to be retained and backed up as usual, as some company data has already been encrypted by them.
>
> If you intend to globally disable dynamic key generation for all companies registered in the SLD control center, you can go to the *Security* tab and choose *Disable Dynamic Key Generation*. After that, all active dynamic keys within this landscape will automatically be deactivated.

## Exporting Dynamic Keys

**Context**

If you plan to transfer a company schema to another SLD, you may opt to export the dynamic keys from the current SLD control center and import them into the new SLD control center.

You can perform the following steps to export dynamic keys.

**Procedure**

1. Log in to the SLD control center.
2. On the *Security* tab, in the *Dynamic Keys* table in the *Dynamic Key Management* area, choose *Export*.
3. In the *Export Dynamic Keys* window, specify the following information:
   - *Password*: specify a password. Make sure that your password complies with the following password policies:
     - It is at least 8 characters in length.
     - It contains at least 1 digit.
     - It contains at least 1 uppercase character.
     - It contains at least 1 lowercase character.
   - *Confirm Password*: confirm the defined password.
   - *Assigned To*: Select the company for which you want to export dynamic keys. Select *All* if you intend to export all dynamic keys.
4. Choose *OK*.

**Results**

The dynamic keys are exported to the path `<installation folder>\SAP Business One ServerTools\System Landscape Directory\incoming`

## Importing Dynamic Keys

**Context**

You can import dynamic keys by performing the following steps.

**Procedure**

1. Log in to the SLD control center.
2. On the *Security* tab, in the *Dynamic Keys* table in the *Dynamic Key Management* area, choose *Import*.
3. In the *Import Dynamic Keys* window, specify the following information:
   - *Path to Dynamic Key File*: choose the dynamic key file that you want to import.

     > **Note**
     >
     > - A p12 file is the only supported file.
     > - The imported file size cannot be greater than 128 KB.

   - *Password*: enter the password you defined when the dynamic key was exported.
4. Choose *Import*.

**Results**

The dynamic keys are listed in the table.

> **Note**
>
> If the corresponding company schema has not been imported, the company information will be missing from the table. Upon importing the company schema, the dynamic keys will automatically associate with the respective company information.
