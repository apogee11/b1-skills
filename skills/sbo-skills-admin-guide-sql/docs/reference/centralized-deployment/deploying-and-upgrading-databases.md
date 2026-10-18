---
title: Deploying and Upgrading Databases
source: pdf pp. 175-177, sec 10.5
summary: Remotely deploying SBOCOMMON and demo databases and upgrading SBOCOMMON and company databases from the SLD control center, including locking companies.
---

# Deploying and Upgrading Databases

After registering database instances on the landscape server, you can use the System Landscape Directory to remotely deploy the system database `SBOCOMMON` and demo databases, and remotely upgrade the `SBOCOMMON` database and your company database.

## Deploying Databases

**Prerequisites**

- You have defined an SAP Business One CD repository folder and a central log repository folder during the installation process. If you have not defined the share folders, you can go to the *Global Settings* tab to configure them. For more information, see [Registering SAP Business One Installation CD](registering-installation-cd.md#registering-sap-business-one-installation-cd) [page 163].
- In the SLD control center, you have registered the logical machines on which you will deploy databases. For more information, see [Registering and Unregistering Logical Machines](sld-agent-wizard-installation.md#registering-and-unregistering-logical-machines) [page 165].

**Procedure**

1. Log in to the SLD control center.
2. On the *DB Instances and Companies* tab, in the *DB instances* area, select the DB instance on which you intend to deploy databases.
3. In the *Companies* area, choose *Deploy*.
4. In the *Selection of Databases* window, select the system database `SBOCOMMON` or demo databases that you want to deploy.

   > **Note**
   >
   > The *Landscape Administrator* and *Database Server Connection* windows may appear for SLD authentication and DB server connection in case of any connection error.

5. In the *Review* window, review your settings carefully before starting the databases deployment process. If you need to change your settings, choose *Previous*; otherwise, choose *Start* to start the deployment.
6. In the *Review* window, choose *Close* to close the window. The wizard continues running in the background and will close automatically after the deployment is finished.

## Upgrading Databases

**Prerequisites**

- You have ensured that all SAP Business One clients are closed.

  > **Recommendation**
  >
  > We recommend that you complete or terminate all workflow instances before closing SAP Business One client.

- You have defined an SAP Business One CD repository folder and a central log repository folder during the installation process. If you have not defined the share folders, you can go to the *Global Settings* tab to configure them. For more information, see [Registering SAP Business One Installation CD](registering-installation-cd.md#registering-sap-business-one-installation-cd) [page 163].
- In the SLD control center, you have registered the logical machines on which you will upgrade databases. For more information, see [Registering and Unregistering Logical Machines](sld-agent-wizard-installation.md#registering-and-unregistering-logical-machines) [page 165].
- You have manually upgraded the System Landscape Directory (SLD) to the new version.
- You have updated the SAP Business One product CD that is used for the CD repository shared folder to the new version.

**Procedure**

1. Log in to the SLD control center.
2. On the *DB Instances and Companies* tab, in the *DB instances* area, select the DB instance on which you intend to upgrade databases.
3. In the *Companies* area, select the database you intend to upgrade and choose *Upgrade*.

   > **Recommendation**
   >
   > Before starting upgrades, you should lock the company whose database you will upgrade. To do this, you can select the company and choose *Lock*. The company status then changes from *Unlocked* to *Locked*.
   >
   > When the company is locked, none of the SAP Business One users can log in to the company from the SAP Business One application. Now you can continue the next steps to perform the upgrades from SLD control center or start the setup wizard to upgrade the company databases on the logical machine.
   >
   > When the upgrades complete successfully, the company status is automatically changed to *Unlocked* and SAP Business One users can log in to the relevant company again.

   > **Note**
   >
   > - SAP Business One database users do not have the authorization to lock companies. Only SAP Business One landscape administrators can lock companies from SLD control center.
   > - You can revert the company status to *Unlocked* by clicking the same button.

4. In the *Setup Type* window, select *Perform Setup* and choose *Next*.
5. In the *Selection of Databases* window, select the system database `SBOCOMMON` or the company databases that you want to upgrade and choose *Next*.

   > **Note**
   >
   > For upgrades, you can select only databases whose status is *Ready*.

6. In the *Backup Settings* window, specify the folder in which you want to store the backup files.
7. In the *Review* window, review your settings carefully before starting the databases deployment process. If you need to change your settings, choose *Previous*; otherwise, choose *Start* to start the deployment.
8. Choose *Close* to close the window. The wizard continues running in the background until the upgrades complete.
