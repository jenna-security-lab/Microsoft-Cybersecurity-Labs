# Defender-XDR-Architecture-Details

## Overview
The environment consists of:
- One Active Directory Domain Controller
- Two Windows 11 user endpoints
- Microft Entra ID tenant
- Microsoft Defender XDR

## Architecture Outline

                              Internet
                                 │
                                 │
                   ┌───────────────────────────┐
                   │   Microsoft 365 Tenant    │
                   │         Entra ID          │
                   │       Defender XDR        │
                   └─────────────┬─────────────┘
                                 │
                      Secure Cloud Connection
                                 │
          ┌──────────────────────┴──────────────────────┐
          │                                             │
  ┌───────────────┐                             ┌───────────────┐
  │  LAB-WIN11-01 │                             │  LAB-WIN11-02 │
  │  Windows 11   │                             │   Windows 11  │
  │ User Endpoint │                             │ User Endpoint │
  │ Defender MDE  │                             │  Defender MDE │
  └───────┬───────┘                             └───────┬───────┘
          │                                             │
          └──────────────────────┬──────────────────────┘
                                 │
                           Domain Network
                                 │
                         ┌───────────────┐
                         │    LAB-DC01   │
                         │ Windows Server│
                         │   Active Dir  │
                         │     DNS       │
                         │  DHCP (opt.)  │
                         └───────────────┘


## Environment Components
|---Device---|---Purpose---|
|--LAB-DC01--|--Active Directory Domain Controller--| 
Purpose: Acts like the company's identity server. Provides user accounts, authentication, group policy, DNS, and domain management. 
Example: A company employee asks to sign into their laptop. The laptop asks the DC "is John Smith allowed to login?" The DC answers.
|--LAB-WIN11-01--|--User Workstation--|
Purpose: Simulates an employee computer. This device will run Defender, generate security events, receive policies, and simulate normal user activity. 
Example: Sarah - Accounting
|--LAB-WIN11-02--|--User Workstation--|
Purpose: Simulates a second employee workstation. This device will be used for testing attachs, comparing security events, and generating additional telemetry. 
Example: Mike - Finance
|--Microsoft Entra ID--|--Cloud Identity Provider--|
Purpose: Cloud identity platform. Simulates Microsoft 365 
Example: 
|Defender XDR--|--Endpoint detection and response--|
Purpose:
Example: 
