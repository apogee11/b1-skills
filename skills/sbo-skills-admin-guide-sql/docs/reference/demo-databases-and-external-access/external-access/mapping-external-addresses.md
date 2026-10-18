---
title: Mapping External Addresses to Internal Addresses
source: pdf pp. 141-142, sec 9.4.5
summary: Which components need an external-to-internal address mapping registered in the SLD, and the services to restart afterwards.
---

# Mapping External Addresses to Internal Addresses

You must register in the System Landscape Directory the mapping between the external address of each of the following components and its internal address:

- System Landscape Directory (SLD)
- Authentication Server
- Browser Access Service
- Mobile Service (Mobile service is required only if you are using SAP Business One Sales app.)
- Web Client
- Microsoft 365 Integration

Note that you do not need to register the mapping for the integration framework.

For detailed instructions, see [Mapping External Addresses to Internal Addresses](../../system-landscape-directory/external-address-mapping.md) [page 93].

**Post-requisite**

After finishing mapping external addresses to all required components, you must restart the services that have enabled external access on the machines where they're installed.

For example, if you have registered the external address mapping for a Browser Access server, you must restart the SAP Business One Browser Access Server Gatekeeper service.

Note that the restart of SAP Business One Browser Access Server Gatekeeper service may take from 5 to 10 minutes. For more information, see SAP Note 2198134.
