---
title: Default Ports for Server Components
source: pdf pp. 273-274, sec 15*, 15.1
summary: Default ports used by the SAP Business One server components, with remarks on which ports must be exposed to the Internet.
---

# Default Ports for Server Components

The following table lists the default ports used for different server components. Ensure that you have kept the following ports available.

<!-- table: t273-01 -->
- **Default Ports**: 30000 or 30001
  - **Server Components**: CORBA license server
- **Default Ports**: 40000
  - **Server Components**:

    Components in Server Tools

    - System Landscape Directory
    - Extension Manager

  - **Remarks**: This port should be exposed to the Internet if you need to use some SAP Business One components on the Internet.
- **Default Ports**: 40002
  - **Server Components**: License Service
- **Default Ports**: 40004
  - **Server Components**: Job Service
- **Default Ports**: 40005
  - **Server Components**:

    - Service Layer Controller
    - Mobile Service

- **Default Ports**: 40006
  - **Server Components**: Microsoft 365 Integration
- **Default Ports**: 40020
  - **Server Components**: Authentication Service in the System Landscape Directory
  - **Remarks**: The service is one part of the SLD. This port should be exposed to the internet.
- **Default Ports**:

    50000 (for load balancer);

    50001, 50002, 50003… (for load balancer members)

  - **Server Components**: Service Layer
  - **Remarks**: The service layer is for internal component calls only and you do not need to expose it to the Internet.
- **Default Ports**: 60000
  - **Server Components**: Workflow
- **Default Ports**: 443
  - **Server Components**: Reverse proxy
- **Default Ports**:

    8080 (for HTTP)

    8443 (for HTTPS)

  - **Server Components**: Integration Framework
- **Default Ports**: 8100
  - **Server Components**: Browser Access
  - **Remarks**: If you need to access SAP Business One services via the Internet, you need to expose this port to the Internet.
- **Default Ports**: 443
  - **Server Components**: Web Client
- **Default Ports**: 40008
  - **Server Components**: Webhook Messenger
- **Default Ports**: 7299
  - **Server Components**: Electronic Document Service
- **Default Ports**: 7297
  - **Server Components**: Electronic File Mapping Transformation Service
- **Default Ports**: 60010
  - **Server Components**: Authentication Service in API Gateway
  - **Remarks**: You need to define the port number if you install the API Gateway Service.
- **Default Ports**: 60020
  - **Server Components**: API Gateway Service
