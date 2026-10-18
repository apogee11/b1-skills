---
title: Security-Relevant Logging and Tracing
source: pdf pp. 261-263, sec 12.13
summary: Where each backend service writes its security event log, the file name and event format, and how to view Keycloak login and admin events.
---

# Security-Relevant Logging and Tracing

SAP Business One keeps the security-relevant logs for recording and analyzing security-related events for the backend services.

## Service Layer

- Path to the log folder: `<servertools install folder>\ServiceLayer\logs`
- Format of the file name: `Securityevent.YYYYMMDD.b1s.log`
- Format of the recorded event in the log: `<Date Time> <User ID> <Source IP> <Event Type> <Event Description>`

## Services in Server Tools

- Path to the log folder: `%ProgramData%\sap\SAP Business One\Log\Security\`
- Format of the file name: `securityevent_saml2.log`
- Format of the recorded event in the log: `<Date Time> <User ID> <Source IP> <Event Type> <Event Description>`

## Browser Access

- Path to the log folder: `%ProgramData%\sap\SAP Business One\Log\Security\`
- Format of the file name: `securityevent_saml2.log`
- Format of the recorded event in the log: `<Date Time> <User ID> <Source IP> <Event Type> <Event Description>`

## System Landscape Directory (SLD)

- Path to the log folder: `${ProgramData}\sap\SAP Business One\Log\SAP Business One ServerTools\System Landscape Directory\`
- Format of the file name: `Securityevent_%d{yyyy-MM-dd}_sld.log`
- Format of the recorded event in the log: `<Date Time> <User ID> <Source IP> <Event Type> <Event Description>`

## Job Service

- Path to the log folder: `${ProgramData}\sap\SAP Business One\Log\SAP Business One ServerTools\Job Service\`
- Format of the file name: `Securityevent_%d{yyyy-MM-dd}_jobService.log`
- Format of the recorded event in the log: `<Date Time> <User ID> <Source IP> <Event Type> <Event Description>`

## Mobile Service

- Path to the log folder: `$ProgramData$\sap\SAP Business One\Log\Security\`
- Format of the file name: `Securityevent_sam12.log`
- Format of the recorded event in the log: `<Date Time> <User ID> <Source IP> <Event Type> <Event Description>`

## Authentication Service

In the Keycloak Admin Console, you can record every login and administrator action and view those actions for the SAP Business One authentication service.

To view the login and admin events, perform the following steps:

1. In a Web browser, navigate to the following URL: `https://<Server Address>:<Port>/auth/admin/sapb1/console` The default port number is `40020`.
2. Log in with the `B1SiteUser` account.
3. In the left menu, choose *Events*.
4. In the right panel, choose the relevant tabs to view the events or event settings.
   - Choose the *Login Events* tab to view the login events for actions such as successful user login, a user entering an incorrect password, or a user account update.
   - Choose the *Admin Events* tab to view the admin events for actions that are performed by an administrator in the Admin Console.
   - Choose the *Config* tab to view the event settings.

> **Note**
>
> The default value for *Expiration* is `90` (days).

You can configure the login and admin event settings in the *Config* tab. For more information about configuring auditing to track events, see Server Administration Guide for Keycloak.

> **Note**
>
> All events are stored in the `B1AS` database, which consumes the database space on your disk. We suggest that you regularly monitor the disk usage depending on your needs.
