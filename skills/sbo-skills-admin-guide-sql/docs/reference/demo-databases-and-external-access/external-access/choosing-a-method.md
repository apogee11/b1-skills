---
title: Enabling External Access and Choosing a Method
source: pdf pp. 129-130, sec 9.4*, 9.4.1
summary: What secure external access to SAP Business One services requires, and how to choose between a reverse proxy and NAT/PAT to handle external requests.
---

# Enabling External Access and Choosing a Method

The SAP Business One Browser Access service, integration framework, mobile service and Web client help you use SAP Business One outside your corporate networks. For secure access, you must do the following:

1. Use an appropriate method to handle external requests.
2. Use valid certificates to install relevant SAP Business One services.
3. Assign an external address to each relevant SAP Business One service.
4. Build proper mapping between the external addresses and the internal addresses.

Alternatively, you can use Citrix or similar solutions for external access. These third-party solutions are not covered in this guide.

## Choosing a Method to Handle External Requests

As the Browser Access service, integration framework, mobile service and Web client enable you to access SAP Business One from external networks, it is essential that external requests can be sent properly to internal services.

To handle external requests, we recommend deploying a reverse proxy rather than using NAT/PAT (Network Address Translation/Port Address Translation). Compared with NAT/PAT, the reverse proxy is more flexible and can filter incoming requests.

> **Note**
>
> Regardless of the method, the database services are not exposed to external networks; only the SAP Business One services are exposed. However, you must never directly assign an external IP address to any server with SAP Business One components installed.
>
> To improve your landscape security, you can install your database server on a machine other than the one holding SAP Business One components.

### Reverse Proxy

A reverse proxy works as an interchange between internal SAP Business One services and external clients. All the external clients send requests to the reverse proxy and the reverse proxy forwards their requests to the internal SAP Business One services.

> **Note**
>
> **Please make sure that the external address of the SLD is accessible from the internal network. If not, please configure a DNS entry resolving to Reverse Proxy server address.**

To use a reverse proxy to handle incoming external requests, you need to:

1. Import a trusted root certificate for all SAP Business One services during the installation. The certificate can be issued by a third-party certification authority (CA) or a local enterprise CA. For instructions on setting up a local certification authority to issue internal certificates, see Microsoft documentation (https://technet.microsoft.com/en-us/library/cc995096.aspx).

   > **Note**
   >
   > If you have enabled [Validate SSL Certificate](../../network-storage-and-keys-security/security-certificate-verification.md) [page 224], all the components (including the reverse proxy) in the SAP Business One landscape should trust the root CA which issued the internal certificate for all SAP Business One services.

2. Purchase a certificate from a third-party public CA and import the certificate to the reverse proxy server. Note that this certificate must be different from the first certificate. While the first certificate allows the reverse proxy to trust the CA and, in turn, the SAP Business One services, the second certificate allows the reverse proxy to be trusted by external clients. All clients from external networks naturally trust the public CA and, in turn, the reverse proxy. A chain of trust is thus established from the internal SAP Business One services to the reverse proxy, and to the external clients.

### NAT/PAT

If you prefer NAT/PAT to a reverse proxy, be aware that all clients connect directly to the internal SAP Business One services, external clients and internal clients alike.

To use NAT/PAT, you must purchase a certificate from a third-party CA and import the certificate to all machines installed with SAP Business One services. All the clients must trust this third-party public CA.

> **Note**
>
> **Please make sure that the external address of the SLD is accessible from the internal network. If not, please configure DNS and make sure it is accessible. Please use a domain name for the external address rather than the IP address.**
