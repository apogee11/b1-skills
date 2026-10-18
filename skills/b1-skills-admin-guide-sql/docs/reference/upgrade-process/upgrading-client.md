---
title: Upgrading the SAP Business One Client
source: pdf pp. 79-80, sec 8.3.2
summary: Prerequisites and procedure for upgrading the SAP Business One client on workstations after the server upgrade, including the 64-bit-only rule.
---

# Upgrading the SAP Business One Client

## Prerequisites

1. You have closed the browser access service before upgrading the SAP Business One client.
2. For the SAP Business One client agent to upgrade third-party add-ons in a silent mode, you must recreate the ARD file of the add-on using the latest version of the Add-On Registration Data Generator. For more information, see [Enabling Silent Upgrades for Third-Party Add-Ons](upgrading-add-ons.md#enabling-silent-upgrades-for-third-party-add-ons) [page 81].

## Context

After the server upgrade, you must upgrade the SAP Business One client on all your workstations.

For an upgrade from a previous release family (for example, from the 9.3 release to the 10.0 release), run the setup wizard on each workstation to upgrade the SAP Business One client.

Alternatively, you can uninstall the old client and then install the new client using the client installation program. The client installation package is available in the entire product package as well as in the shared folder `B1_SHR`.

> **Note**
>
> SAP Business One 10.0 supports only the 64-bit SAP Business One client. So, if you have installed a 32-bit SAP Business One client on a client workstation, you must manually uninstall the 32-bit client first, and then install or upgrade to the 64-bit client.

## Procedure

1. Run the client as the administrator.
2. Log on to a company.

   A system message appears to inform you that the client is not updated.

3. In the system message window, choose *OK* to upgrade the client.
