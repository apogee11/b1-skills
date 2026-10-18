---
title: "Secure Connections: Web Client"
source: pdf pp. 224-224, sec 12.4.2.6
summary: TLS versions and the cipher suites the SAP Business One Web client uses for HTTPS.
---

# Secure Connections: Web Client

SAP Business One, Web client enforces secure connection via HTTPS encryption with TLS version 1.2 or 1.3; the corresponding TLS cipher suites are listed as follows:

- `Preferred TLSv1.3 256 bits TLS_AES_256_GCM_SHA384 Curve 25519 DHE253`
- `Accepted TLSv1.3 256 bits TLS_CHACHA20_POLY1305_SHA256 Curve 25519 DHE 253`
- `Accepted TLSv1.3 128 bits TLS_AES_128_GCM_SHA256 Curve 25519 DHE 253`
- `Preferred TLSv1.2 128 bits ECDHE-RSA-AES128-GCM-SHA256 Curve 25519 DHE 253`
- `Accepted TLSv1.2 256 bits ECDHE-RSA-AES256-GCM-SHA384 Curve 25519 DHE 253`
- `Accepted TLSv1.2 256 bits ECDHE-RSA-CHACHA20-POLY1305 Curve 25519 DHE 253`
