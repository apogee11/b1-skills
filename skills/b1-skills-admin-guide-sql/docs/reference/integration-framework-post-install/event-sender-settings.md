---
title: Changing Event Sender Settings
source: pdf pp. 151-154, sec 9.7.7
summary: When and how to run the event sender setup wizard (database connection, polling, framework connection, include/exclude filters per company database) and where the settings are stored.
---

# Changing Event Sender Settings

## Context

SAP Business One writes events for new data, changes and deletions to the `SEVT` table. Based on filter settings, the event sender accesses the table, retrieves data and hands over the events to the integration framework for further processing.

The installation program installs and sets up the event sender on the SAP Business One server. TheSAP Business One Event Sender setup is available as an external tool and as of SAP Business One 9.2 PL10, also in the integration framework. If you run the event sender on the same machine as the integration framework, we recommend using the setup that is part of the integration framework.

The following section describes event sender settings, although usually no further changes are required.

> **Note**
>
> Only call the event sender setup in the following cases:
>
> - You must change the password for database access.
> - You have changed the B1iadmin password for the runtime user.
> - You have moved to another server.
> - To reduce the message load, you want to include or exclude some objects.
> - You want to exclude users.

To check the settings for the event sender, use the integration framework troubleshooting function. In the integration framework version 1, choose *Tools* > *Troubleshooting*, and in the *Functional Group* field, choose *Event Sender*.

## Procedure

1. To call the event sender setup, choose *Start* > *All programs* > *Integration Framework for SAP Business One* > *Integration Framework*.

   The *Logon* user interface opens.

2. In the *Username* field, enter `B1iadmin` and in the *Password* field, enter the password that was provided during installation.
3. To open the event sender setup, choose *Tools* > *Event Sender* and click the *Setup Wizard* button.
4. In step 1, in the *Choose Database Type* field, select the SAP Business One database type.
5. In the *DB Connection Settings* section, you can set the following:
   - In the *DB Server Name* field, enter the fully qualified domain name (FQDN) of the machine, where the database of the SAP Business One server is installed. Do not use `localhost`.

     > **Recommendation**
     >
     > Use the hostname of the server. Only if you have problems specifying the hostname, use the IP address instead.

     > **Caution**
     >
     > In the SAP Business One integration for SAP NetWeaver installation, this setting must be identical with the value in the *b1Server* field. If the values are not identical, they appear in the `Filtered` section.

   - In the *Port* field, enter the port number of the database server, where the SAP Business One server is installed.
   - In the *Setup DB Account* and *Password* fields, the installation has set the database user name and password for database access during setup. This user must have access rights to create tables and store procedures.
   - In the *Running DB Account* and *Password* fields the installation has set the database user name and password for database access at runtime. This user must have access rights to the event log and event lock tables.
   - Click *Test Connection* to test the connection to the SAP Business One database.
6. In step 2, the following settings are available in the *Monitor Settings* section.
   - In the *Idle Time (millisecond)* field, you can change the time period the event sender waits until it polls events from SAP Business One. The default is 3000 milliseconds.
   - In the *Batch Count* field, you can set the number of events the event sender polls each time. The default is 10.
7. In step 3, you can change general settings for the integration framework.

   By default, the installation program sets the *Sending Method* to `Distributed`.

   The event sender sends all events to the local server address and the event dispatcher takes over the task of distributing the events to other systems.

   For more information, see the *Operations Guide Part 2*, section *Configuring the B1 Event Subscriber*.

8. In the *General Integration Framework Settings*, you can configure the following:
   - In the *Protocol Type* field, select the protocol for the connection between the event sender and the integration framework. To enable https, make settings in the Tomcat administration.
   - In the *Authentication* field, always use the `Basic` option. This is the default.
   - If you selected the https protocol type, select *Server Authentication* to let the event sender verify the certificate. For the verification, do the following to make the `b1i.jks` file available in the `… \EventSender` folder:
     1. Copy the `\IntegrationServer\Tomcat\webapps\B1iXcellerator\.keystore` file.
     2. Rename the copied `.keystore` to `b1i.jks`.
     3. Copy `b1i.jks` to the `…\EventSender` folder.
   - In the *Framework Server Host* field, enter the name or IP address of your integration framework or the SAP Business One integration for SAP NetWeaver server.
   - In the *Framework Server Port* field, enter the port number of your integration framework or the SAP Business One integration for SAP NetWeaver server.
   - In the *User Name* field, enter the user name for accessing the integration framework or SAP Business One integration for SAP NetWeaver server. The default is `B1iadmin`.
   - In the *Password* field, enter the password for accessing the integration framework or SAP Business One integration for SAP NetWeaver server.
   - To test the connection, choose *Test Connection*.
9. In step 4, choose the company databases.

   The setup program displays the company databases in your SAP Business One system. For each company database, you can set up the following:

   1. Deselect the checkbox in front of the SAP Business One company database if the company does not use the integration framework. If you deselect the checkbox, SAP Business One does not create events for the company database in the `SEVT` table.
   2. To define the *Include List B1 Object(s)* settings based on active scenario packages, click *Generate*. The SAP Business One event filter generator opens.
      - Determine the objects for the include list and click *Apply*. The wizard displays the list of company databases.
      - Select the databases for which you want to set the include filter. Note that for databases with defined exclude filter settings, the checkbox is disabled.
      - Click *OK* and the wizard writes the include filter settings to the selected databases.
      - Alternatively: In the *Include List B1 Object(s)* field, enter the object identifier of the SAP Business One object or objects. Separate entries by comma. If you enter, for example, `22,17`, the event sender sends events for purchase orders and orders to the integration framework or the SAP Business One integration for SAP NetWeaver server. If you leave the field empty, the event sender sends events for all SAP Business One objects to the integration framework or the SAP Business One integration for SAP NetWeaver server. In the *Exclude List B1 Object(s)* field, enter the object identifier of the SAP Business One object or objects. Separate entries by comma. If you enter, for example, `85`, the event sender excludes events for special prices for groups. If you leave the field empty, the event sender sends events for all SAP Business One objects to the integration framework or the SAP Business One integration for SAP NetWeaver server.

        > **Note**
        >
        > Use either the *Include List B1 Object(s)* or the *Exclude List B1 Object(s)* function. Do not use the functions together.

      - In the *Exclude List B1 User* field, enter SAP Business One users for which the event sender does not send events to the integration framework. Enter the SAP Business One user name, not the user code. Separate entries by comma.
      - If you want the company database to create events based on indirect journal entries, select the *Create Complete Journal Entry Events* checkbox. Standard SAP Business One processing does not create events for indirect journal entries.
10. Step 5 gives you a summary of the event sender settings. To save the settings, choose *Deploy*.
11. Restart the *SAP Business One Event Sender* service and the SAP Business One client.

## Results

The setup program stores the settings in the `datasource.properties` and `eventsenderconfig.properties` configuration files.
