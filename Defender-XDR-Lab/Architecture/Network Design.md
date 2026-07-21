# Network Design

## Network Range
192.168.100.0/24

## Devices
|  Device  |  IP  |  Purpose  |
|---|---|---|
|  LAB-DC01  |  192.168.100.10  |  Domain Controller  |
|  LAB-WIN11-01  |  DHCP  |  User Endpoint  |
|  LAB-WIN11-02  |  DHCP  |  User Endpoint  |

## DNS
Domain Controller provides DNS.

DNS Server:
192.168.100.10

## Domain Information
| Setting      | Value                  |
| ------------ | ---------------------- |
| Domain Name  | corp.securitylab.local |
| Forest Level | Windows Server 2022    |
| DNS          | LAB-DC01               |
| DHCP         | Optional               |
| Network      | 192.168.100.0/24       |

