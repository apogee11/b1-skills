---
title: Centralized Deployment Overview and Registering the Installation CD
source: pdf pp. 163-165, sec 10*, 10.1
summary: What centralized deployment from the SLD control center covers, and how to define the CD repository, the central log directory and the SLD Agent timeouts.
---

# Centralized Deployment Overview and Registering the Installation CD

SAP Business One supports the central management of the SAP Business One landscape from the System Landscape Directory (SLD) control center. You can perform the following operations remotely through the SLD control center:

- Register logical machines.
- Install the SAP Business One components.
- Deploy and upgrade the system database `SBOCOMMON` and demo databases.
- Register the database instances.
- Check the installed SAP Business One components across the whole SAP Business One landscape.

To implement central management, you should access the SLD control center in a Web browser and follow the steps below:

1. Configure global settings.
2. Register logical machines on the SLD control center.
3. Register database instances on the landscape server.
4. Deploy or upgrading databases.
5. Install client components.

**Prerequisite**

You have copied an SAP Business One product CD on some machine within the SAP Business One landscape.

## Registering SAP Business One Installation CD

**Context**

If you intend to perform remote administrative tasks from the SLD control center, you should have previously created the CD repository folder and the central log directory. The CD repository folder is the folder that contains SAP Business One product or upgrade CDs; the central log directory can be any folder within the landscape. These two folders are SLD related, and you should have shared them previously. You need to define the shared folders or reconfigure them from the SLD control center.

> **Note**
>
> The CD repository folder and the central log directory are the prerequisites to all operations for landscape central management. You must create both shared folders before performing the other operations.

To define or reconfigure the shared folders of SAP Business One CD repository and the central log directory, perform the following steps:

**Procedure**

1. Log in to the SLD control center.
2. On the *Global Settings* tab, in the *Central Deployment* area, click ... (*browse*) behind *CD Repository*.
3. In the *Share Settings* window, enter the following information to define or reconfigure the CD repository shared folder and choose *Save*.
   - *Share Type*: The default type is *CD Repository*.
   - *Network Path*: Enter the network path of the shared SAP Business One product CD repository. The product CD repository could be either the exact shared folder or a subfolder of a shared folder.

     > **Example**
     >
     > If `B1_SHR` is a shared folder and `B1_DEFAULT_REPO` is a subfolder of the shared folder, you can specify either `\\<IP address>\B1_SHR` or `\\<IP address>\B1_SHR\B1_DEFAULT_REPO` as the CD repository shared folder.

   - *Access User Name*: Enter the name of a user who can access the product CD.
   - *Access User Password*
4. On the *Global Settings* tab, in the *Central Deployment* area, click ... (*browse*) behind *Central Log Directory*.
5. In the *Share Settings* window, enter the following information to define or reconfigure the central log directory and choose *Save*.
   - *Share Type*: The default type is *Central Log Directory*.
   - *Network Path*: Enter the network path of the shared central log directory. The shared central log directory could be either the exact shared folder or a subfolder of a shared folder.

     > **Example**
     >
     > If `B1_CEN` is a shared folder and `B1_LOG_DIRO` is a subfolder of the shared folder, you can specify either `\\<IP address>\B1_CEN` or `\\<IP address>\B1_CEN\B1_LOG_DIRO` as the central log directory.

   - *Access User Name*: Enter the name of a user who can access the central log directory.
   - *Access Password*
6. In the *Central Deployment* area, define the SLD Agent timeouts.
   - *SLD Agent Heartbeat Timeout*: configure the time interval of the SLD Agent response to the SLD.

     > **Example**
     >
     > When you define the SLD Agent heartbeat timeout to 3 minutes, the SLD Agent will report the hardware utilization of the logical machine to the SLD every 3 minutes and will report the installed SAP Business One software components on the logical machine to the SLD every 30 minutes.

   - *SLD Agent Operation Timeout*: configure the maximum time period for a SLD operation task, such as logical machines registration, client components installation.

     > **Note**
     >
     > The SLD Agent operation timeout does not apply to the database operation tasks, such as database updates.

7. In the *Verbose Logging* area, you can choose to enable verbose logging and download log files.
