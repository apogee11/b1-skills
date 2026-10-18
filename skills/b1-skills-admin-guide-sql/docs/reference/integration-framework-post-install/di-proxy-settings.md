---
title: Changing SAP Business One DI Proxy Settings
source: pdf pp. 154-155, sec 9.7.8
summary: The parameters of diproxyserver.properties (ports, restart and orphan behavior, JCo path and version) that control the SAP Business One DI Proxy service.
---

# Changing SAP Business One DI Proxy Settings

## Context

SAP Business One DI Proxy is the SAP Business One-related component that enables data exchange with SAP Business One using the DI API. No additional steps are required to set up the SAP Business One DI Proxy service.

To influence the behavior of the SAP Business One DI Proxy service, parameters are available in the `diproxyserver.properties` file.

## Procedure

1. To change parameters, access the `diproxyserver.properties` file in the `…SAP\SAP Business One Integration\DIProxy` path.

<!-- table: t154-01 -->
- **Property**: RMI_PORT
  - **Description**: The parameter is obsolete.
- **Property**: HTTPS_PORT
  - **Description**: DI Proxy TCP port for HTTPS.
- **Property**: MAXDIERRORS
  - **Description**: If this property exists and has a value greater than 0, the value defines the number of DI errors that may occur before the DI Proxy restarts. The default is 50.
- **Property**: RESTARTPERIOD
  - **Description**: If this property exists and has a value greater than 0, the value determines the time in minutes after which the DI Proxy restarts. The default is 60.
- **Property**: ORPHANED
  - **Description**: This property defines the value in minutes after which the system defines a pending and not yet completed DI transaction as orphaned. The DI Proxy removes the transaction from the internal transaction list. If this property does not exist or does not have a positive value, the default is 10. If it exists, the default is 30.
- **Property**: JCOPATH
  - **Description**:

    If this property exists and is not empty, it defines the path the DI Proxy uses to search for the JCo installation. In this case the system ignores any value coming from B1iP requested by an adapter.

    If the property does not exist, the system uses any value coming from B1iP requested by an adapter. In this case the setting is probably not definite.

    SAP recommends setting the JCo path in the `diproxyserver.properties` file.

    If you want to change a JCo path that someone has already maintained and that the system has used for connection, you can apply this change only after you have restarted the SAP Business One DI Proxy Service.

    Use / or \\ instead of \ as a separator in the JCOPATH value. Use for example C:\\Program Files\\SAP\\SAP Business One DI API\\JCO\\LIB

- **Property**: JCOVERSION
  - **Description**: If this property exists and is not empty, it defines the version the DI Proxy uses to search for the JCo installation.
- **Property**: restartAttemptDelay
  - **Description**:

    As of DI Proxy version 30002211, you can overlay the default for a restart delay (500 milliseconds).

    Provide a value in milliseconds.

- **Property**: restartAttemptCap
  - **Description**: As of DI Proxy version 30002211, you can overlay the default number of restart attempts (10).

2. If you change any settings, restart the *SAP Business One DI Proxy Service*.
