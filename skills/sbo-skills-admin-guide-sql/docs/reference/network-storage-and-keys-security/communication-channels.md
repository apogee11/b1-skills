---
title: Communication Channels
source: pdf pp. 217-218, sec 12.4*, 12.4.1
summary: Recommended trusted-environment use of SAP Business One and the TCP/IP channels between client-side and server-side components with the protocol each uses.
---

# Communication Channels

## Network and Communication Security

We strongly recommend using SAP Business One in trusted environments only (corporate LAN with firewall protection).

To work with SAP Business One outside your corporate networks, you can use Citrix or similar third-party solutions.

## Communication Channels

TCP/IP provides the communication channels between the following:

<!-- table: t217-01 -->
| Client Side | Server Side | Protocol Used |
|---|---|---|
| SAP Business One client agent | System landscape directory | HTTPS |
| SAP Business One client agent | The shared folder `b1_shf` | SAMBA |
| Agent of SAP Business One remote support platform | SAP Business One server | ODBC |
| Browser Access server | Company database | ODBC |
| Browser Access server | System landscape directory | HTTPS |
| IM service | Company database | JDBC |
| Integration framework | Company database | JDBC |
| Integration framework | Integration framework database | JDBC |
| Integration framework | SAP Business One license server | HTTPS |
| Job service | Company database | JDBC |
| Job service | Service Layer | HTTPS |
| Job service | SMTP server | SMTP |
| Job service | System landscape directory | HTTPS |
| Mobile service | System landscape directory | HTTPS |
| SAP Business One client | Company database | ODBC |
| SAP Business One client | IM service | HTTPS |
| SAP Business One client | System landscape directory | HTTPS |
| SAP Business One client | The shared folder `B1_SHR` | SAMBA |
| SAP Business One client | Workflow service | HTTPS |
| SAP Business One DI API | Company database | ODBC |
| SAP Business One DI API | System landscape directory | HTTPS |
| Service Layer | Company database | ODBC |
| Service Layer | System landscape directory | HTTPS |
| System landscape directory | Domain controller | Kerberos |
| System landscape directory | Service unit database | JDBC |
| System landscape directory | System landscape directory database | JDBC (can be encrypted via SSL) |
| Third party add-on products | Service Layer | HTTPS |
| Web browser | Browser Access server | HTTPS |
| Web browser | Integration framework | HTTP or HTTPS |
| Web browser | System landscape directory | HTTPS |
| Web browser | Workflow service | HTTPS |
| Workflow service | Company database | JDBC |
