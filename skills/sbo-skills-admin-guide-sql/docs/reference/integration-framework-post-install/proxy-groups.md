---
title: Using Proxy Groups
source: pdf pp. 155-157, sec 9.7.9
summary: How to load-balance DI requests with several DI proxies, define proxy groups in the DI adapter global configuration, and reference a group in SLD.
---

# Using Proxy Groups

The DI adapter allows defining multiple proxy groups in the global adapter configuration properties. This allows load balancing by processing requests to multiple proxies. Requests can come from IPO steps that are independent of each other. If you process a step using a certain proxy, the step uses the proxy during the complete step processing.

You can find the following information in the proxy log file:

- The proxy logs the processing start and stop time and describes how the proxy was stopped.
- Find a usage statistics summary, which lets you decide whether the proxy suits the processing requirements or whether it should be enhanced to a proxy group to fulfill the overall requests.

## Providing Further Proxies

### Context

To use proxy groups, provide several DI proxies.

### Procedure

1. To enable a configuration set for a second *DIProxy* instance, copy the `DIProxy` folder and paste it.

   The system creates the `DIProxy - Copy` folder.

2. Rename the folder to `DIProxy2`.
3. In the `...\DIProxy2` folder, open the `service.ini` file and change the following entries:
   - `ServiceName = SAPB1iDIProxy2`
   - `DisplayName = SAP Business One DI Proxy 2 Service`
4. In the `...\DIProxy2` folder, open the `diproxyserver.properties` file.
5. Change the `HTTPS_PORT` parameter to `2098`, if port `2098` is available on your machine.

```text
HTTPS_PORT=2098
```

6. Choose *Start*, right-click *Command Prompt* and choose the *Run as administrator* option.
7. Run `service.exe` with the `-install` parameter in the `...\DIProxy2` folder.
8. Start the *SAP Business One DI Proxy 2 Service Monitor* service.
9. Repeat the steps above for the number of DI Proxies you want to use.

## Adding Proxy Groups to the DI Adapter Global Configuration

### Context

In the integration framework, you have the option of defining proxy groups with proxies. Define the proxy groups and proxies in the DI adapter global configuration.

### Procedure

1. In the integration framework, choose *Tools* > *Control Center* > *Configuration* > *Global Adapter Config*.
2. In the *Global Adapter Configuration Properties* user interface, for the *B1DI* adapter, click the *Edit Global Configuration Properties* link.
3. For the *diProxyGroupList* property, define the proxy groups in the following way:

```json
[<groupname1> <hostname1>:<port1>,<port2>][<groupname2>
<hostname2>:<port1>,<port2>]
```

   - `<groupname1,2>` are the proxy group names
   - `<hostname1,2>` are the host names or IP addresses of the proxies
   - `port1,2` are the port numbers

### Example

You want to provide the following proxy groups:

- `alpha` and `beta`
- Each group has two proxies

```json
[alpha abc:2099 def:3701][beta 1.2.3.4:2099,3000]
```

## Using Proxy Groups in SLD

In SLD, enter the proxy group definition that you want to use for a certain company database in the *diProxyhost* field of the SAP Business One company database entry in the following way, for example: `[alpha]`

If you use a proxy group, leave the *diProxyport* field empty.
