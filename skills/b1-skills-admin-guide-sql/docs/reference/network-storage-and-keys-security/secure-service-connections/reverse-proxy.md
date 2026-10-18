---
title: "Secure Connections: Reverse Proxy"
source: pdf pp. 222-223, sec 12.4.2.4
summary: Why to deploy a reverse proxy for external clients, its default port, and the TLS versions and cipher suites it enforces.
---

# Secure Connections: Reverse Proxy

A reverse proxy works as an interchange between internal SAP Business One services and external clients. All the external clients send requests to the reverse proxy and the reverse proxy forwards their requests to the internal SAP Business One services. To handle external requests, we recommend that you deploy a reverse proxy rather than using NAT/PAT.

The default port for reverse proxy is `443`.

The reverse proxy enforces secure connection via HTTPS encryption with TLS version 1.2 or 1.3 and the corresponding TLS cipher suites are listed as follows:

- `TLS13-AES-256-GCM-SHA384`
- `TLS13-CHACHA20-POLY1305-SHA256`
- `TLS13-AES-128-GCM-SHA256`
- `TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256`
- `TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA384`
- `TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA`
- `TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256`
- `TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA384`
- `TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`
- `TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA256`
- `TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384`
- `TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA`
- `TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA256`
- `TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384`
- `TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`
