---
title: Upgrading SAP Business One Add-Ons
source: pdf pp. 80-82, sec 8.3.3
summary: How add-ons are registered and upgraded during an upgrade, fixing failed add-on upgrades caused by a "(local)" server name, and enabling silent upgrades for third-party add-ons.
---

# Upgrading SAP Business One Add-Ons

- [Troubleshooting Add-On Upgrades](#troubleshooting-add-on-upgrades)
- [Enabling Silent Upgrades for Third-Party Add-Ons](#enabling-silent-upgrades-for-third-party-add-ons)

When you select the *Add-On* checkbox in the *Component Selections* window of the setup wizard, the following occurs:

- New versions of all SAP add-ons are automatically registered on the SAP Business One server.
- New installers are uploaded to the server during the upgrade of the common database.

Add-ons that were already installed and assigned to a company are reregistered with new releases and assigned to the same company.

On a client computer, upon the next logon to a company assigned with add-ons, installers for the new add-on releases run automatically.

## Troubleshooting Add-On Upgrades

### Context

When upgrading add-ons in an upgraded company for which the server name was previously something like (`local`), you may encounter a message about installation failure.

SAP Business One has introduced a license security mechanism, and we do not recommend that you specify a server name such as (`local`). In this case, during an upgrade, the user defines the server name as an IP address or a computer name. The application does not find the previous, (`local`), name of the upgraded company, which prevents the previous add-ons from being upgraded.

To solve this problem, do the following:

### Procedure

1. Go to the `…\SAP Business One\` folder and locate the `AddonsLocalRegistration.sbo` file.
2. Change the server name of each related add-on to the new name specified in the license server.

> **Example**
>
> - Old name: `<Common ID="1" Name="(local)"/>`
> - New name: `<Common ID=”1” Name=”MyServerName”/>`

## Enabling Silent Upgrades for Third-Party Add-Ons

### Context

To enable the SAP Business One client agent to upgrade a third-party add-on in silent mode, do either of the following:

- If your add-on needs to be installed, you must recreate the add-on’s ARD file using the latest version of the Add-On Registration Data Generator to enable silent upgrades (and installations).

  > **Note**
  >
  > You may be required to rebuild the installation package of the add-on and redesign the installation and configuration process. For example, if the add-on uses an installation wizard that requires the user to specify some information, then you can perform the configuration steps in the SAP Business One client after installing the add-on instead. Alternatively, you can provide the required information as command line arguments in the ARD file.

- If your add-on does not need to be installed, you can use the Extension Manager to manage its upgrade. For more information, see the guide *How to Package and Deploy Lightweight Extensions for SAP Business One* on SAP Help Portal (https://help.sap.com/viewer/index).

The following procedure describes how to enable silent upgrades using the Add-On Registration Data Generator.

### Procedure

1. To start the Add-On Registration Data Generator, run the `AddOnRegDataGen.exe` file, which is typically located in the `...\SAP Business One SDK\Tools\AddOnRegDataGen` folder.
2. Load an existing file, or enter the mandatory information.

   For more information, see the *Create a Registration Data File* chapter in the SDK help file.

3. Select the *Silent Mode* checkbox.
4. If necessary, in the *Installer/Uninstaller/Upgrade Command Line* field, enter any required command line arguments.
5. Choose *Generate File*.
