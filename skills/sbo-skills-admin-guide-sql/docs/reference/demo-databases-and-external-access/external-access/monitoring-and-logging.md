---
title: Monitoring and Logging Browser Access
source: pdf pp. 144-144, sec 9.4.7, 9.4.8
summary: The service monitor URL for Browser Access processes, and where the Browser Access logs are and how to raise the logging level.
---

# Monitoring and Logging Browser Access

## Monitoring Browser Access Processes

You can monitor the Browser Access processes in a Web page using this URL: `https:// <dispatcherHostname>:<port>/serviceMonitor/`.

## Logging

The log files for the Browser Access service are stored at `<Installation Folder>\SAP Business One BAS GateKeeper\tomcat\logs`.

If you need to troubleshoot problems, edit the file `<Installation Folder>\SAP Business One BAS GateKeeper\tomcat\webapps\dispatcher\WEB-INF\classes\logback.xml`, and change the logging level from the default `WARN` to `DEBUG`. Note that you must change the logging level back to the default value after the investigation.
