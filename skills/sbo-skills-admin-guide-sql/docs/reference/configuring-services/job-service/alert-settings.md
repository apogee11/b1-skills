---
title: Alert Settings
source: pdf pp. 112-114, sec 9.2.2.2
summary: Starting the alert service in the job service Web page, enabling it per company, and monitoring alert task statuses and the execution timeout.
---

# Alert Settings

To use the alert function to have SAP Business One automatically notify selected users whenever certain system events occur, you must first start the alert service for the companies on the server side.

> **Note**
>
> If you are using the SAP Business One job service in version SAP Business One 10.0 PL02 or higher, make sure that you have installed the Service Layer.

**Procedure**

1. In a Web browser, navigate to the following URL: `https://<Server Address>:<Port>/job`

   Alternatively, on the *Services* tab in the system landscape directory, you can click the *Job Service* link to access the settings.

   > **Note**
   >
   > - If you use a proxy for your Internet connection, you must add the full hostname or IP address of any Web server (for example, SLD) to the proxy exception list of your Web browser; in other words, do not use a proxy for these addresses.
   > - The URL of the service is case-sensitive.
   > - On the *Services* tab in the system landscape directory, make sure that the job service is already bound to a database instance which is registered in the SLD control center.

2. If you have not logged on to the SLD service, in the logon page, enter the landscape administrator name (`B1SiteUser`) and password, and then choose *Log In*.

   > **Note**
   >
   > The landscape administrator name is case sensitive.

3. To start the alert service, choose *Start* on the *Alert Settings* tab. The status changes to `RUNNING` and the button changes to *Stop*.
4. Log in to the SAP Business One client as a superuser or a power user and do the following to enable the alert and scheduling services for databases.
   1. Select the database for which you want to enable the alert and scheduling service.
   2. On the *Service* tab of the *General Settings* window (*Main Menu* > *Administration* > *System Initialization* > *General Settings*), select the *Enable Alert Service* checkbox.

   Alternatively, you can also enable the alert service for databases from the System Landscape Directory control center as following:

   1. Log in to the SLD control center.
   2. On the *DB Instances and Companies* tab, in the *Companies* area, select the databases on which you intend to enable the alert and scheduling services and choose *Enable Alert*.

**Result**

You can now log in to each of your companies in the SAP Business One client and define the alert settings on the client side. For more information, see the online help.

## Monitoring Alert Task Statuses

You can monitor the alert task statuses and specify the maximum time allowed for a task to execute before it is automatically interrupted.

**Procedure**

1. In a Web browser, navigate to the following URL: `https://<Server Address>:<Port>/job` Alternatively, on the *Services* tab in the system landscape directory, you can click the *Job Service* link to access the settings.

   > **Note**
   >
   > - If you use a proxy for your Internet connection, you must add the full hostname or IP address of any Web server (for example, SLD) to the proxy exception list of your web browser; in other words, do not use a proxy for these addresses.
   > - The URL of the service is case-sensitive.
   > - On the *Services* tab in the system landscape directory, make sure that the job service is already bound to a database instance which is registered in the SLD control center.

2. If you have not logged in to the SLD service, on the login page, enter the landscape administrator name (`B1SiteUser`) and password, and choose *Log In*.

   > **Note**
   >
   > The landscape administrator name is case-sensitive.

3. Choose the *Task List* tab.
4. In the *Execution Timeout* field, specify the maximum time (in minutes) allowed for a task to execute before it is automatically interrupted, and choose *Update*. The default value is 1440 minutes.

   > **Note**
   >
   > You can only enter a positive whole number as the timeout value.

   > **Recommendation**
   >
   > We recommend that you specify the timeout value as 60 minutes or more.

5. In the table list, you can monitor the task statuses by checking the following information:
   - *Company Name*: Name and ID of the company in which you perform the task.
   - *Time of Adding to List*: The time when the task is added to the task list.
   - *Status*: There are 4 types of statuses.
     - *Waiting*: The task is waiting for the execution.
     - *Running*: The task is running.
     - *Interrupted*: When the execution time of a task exceeds the defined execution timout, the task is automatically interrupted.
     - *Error*: An unexpected error occurred.
   - *Status Change Time*: The time of the last change to the status.

   The table list refreshes every 3 seconds automatically .
