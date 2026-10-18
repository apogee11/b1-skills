---
title: Assigning More Random-Access Memory (RAM)
source: pdf pp. 149-150, sec 9.7.5
summary: How to raise the maximum memory pool of the integration framework Tomcat server for high message load.
---

# Assigning More Random-Access Memory (RAM)

## Context

We recommend checking the performance aspects in the related documentation.

Choose *Start* > *All programs* > *Integration Framework for SAP Business One* > *Integration Framework*, and then choose *Help* > *Documents* > *Operations: Performance and Security*.

If you expect your system to run under very high load and to process a high number of messages, you can assign more random-access memory (RAM) to the integration framework server to improve performance.

## Procedure

1. On your local drive `C:\Program Files\SAP\SAP Business One Integration\IntegrationServer\tomcat\bin\` double-click `tomcat<version>.exe`.

   If the system denies access, select `tomcat<version>.exe`, open the context menu and select the *Run as Administrator* option.

2. In a 64-bit operating system, the default is 2048 MB for the maximum memory pool amount for Tomcat. Select the *Java* tab and increase the maximum memory pool amount.
