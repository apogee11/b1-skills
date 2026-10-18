---
title: Adding Services in the SLD
source: pdf pp. 86-87, sec 9.1.2
summary: Which services the SLD Services tab lists, and how to add a service with the correct service URL for each type.
---

# Adding Services in the SLD

The *Services* tab of the SLD displays all SAP Business One services that have been installed and registered on the license server. The services include the following:

- License Manager
- Job Service
- Microsoft 365 Integration
- Browser Access Service
- Workflow Service
- Service Layer
- Mobile Service
- Web Client
- Webhook Messenger
- Electronic Document Service
- Electronic File Mapping Transformation Service
- API Gateway Service

As of 10.0 FP 2602, the new columns *Version* and *Certificate Expiration Date* are available in the *Services* table.

- The *Version* column offers a centralized view of all installed component versions. This helps administrators maintain consistency and verify updates across the entire landscape, preventing potential issues.
- The *Certificate Expiration Date* column shows the expiration date of all installed components. If a certificate expires within **30** days or has already expired, the date will be displayed in red, and a warning message will appear upon accessing the SLD control center. You may choose to disable certificate expiration warnings through the *Global Settings* tab. For more information, see [Disabling Certificate Expiry Warnings](certificate-expiry-warnings.md) [page 95].

If you accidentally delete a service from the SLD, you must add the service again; otherwise, you cannot use the service.

**Procedure**

1. Log in to the SLD control center.
2. On the *Services* tab, choose *Add*.
3. In the *Add Service* window, specify the following information:
   - Service type: Only installed service types are available.
   - Service name: Enter a name for the service.
   - Service Unit: For Job Service, you must make sure to select a database instance which is already registered in the SLD control center.
   - Service URL: Specify the service URLs as below:
     - License Manager: `https://<Server Name/IP>:<port>/LicenseControlCenter`

       > **Note**
       >
       > If you have enabled high availability for the license server, you need to specify the License Manager as `https://<Virtual IP Address>:<port>/LicenseControlCenter`.

     - Job Service: `https://<Server Name/IP>:<port>/job`
     - Browser Access Service: `https://<Server Name/IP>:<port>dispatcher`
     - Workflow: `https://<Server Name/IP>:<port>/workflow`
     - Service Layer: `https://<Server Name/IP>:<port>` (Documentation for SAP Business One Service Layer) or `https://<Server Name/IP>:<port>/ServiceLayerController` (SAP Business One Service Layer Controller)
     - Mobile Service: `https://<Server Name/IP>:<port>/mobileservice`
     - Web Client: `https://<Server Name/IP>:<port>`
     - Webhook Messenger: `https://<Server Name/IP>:<port>/WebhookMessenger`
     - Electronic Document Service: `https://<Server Name/IP>:<port>`
     - Electronic File Mapping Transformation Service: `https://<Server Name/IP>:<port>`
     - API Gateway Service: `https://<Server Name/IP>:<port>`
     - Microsoft 365 Integration: `https://<Server Name/IP>:<port>/ms365i`
