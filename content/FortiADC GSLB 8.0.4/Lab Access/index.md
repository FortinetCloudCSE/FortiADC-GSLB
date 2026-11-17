---
title: "Lab Access"
LinkTitle: "Lab Access"
weight: 30
---



### Lab Network Diagram

```mermaid
graph TD
    %% ----------------------------------------------------
    %% Style Definitions
    %% ----------------------------------------------------
    classDef default fill:#E1E4Eb,stroke:#475569,stroke-width:1.5px,color:#0f172a
    classDef eastObj fill:#ecfdf5,stroke:#10b981,stroke-width:2px,color:#064e3b
    classDef westObj fill:#f5f3ff,stroke:#8b5cf6,stroke-width:2px,color:#4c1d95

    %% --- Top Section (Inside & Outside Clients / Firewalls) ---
    Client_Inside((Client_Inside)):::westObj
    NS2b((NS2b)):::westObj
    Internal_Net([Internal]):::westObj
    FGT_West[[FGT-West]]:::westObj

    Client_Outside((Client_Outside)):::eastObj
    NS1b((NS1b)):::eastObj
    External_Net([External]):::eastObj
    FGT_East[[FGT-East]]:::eastObj

    %% --- Center: Core Transit Networks ---
    Internal_East_Net([Internal-East]):::eastObj
    Internal_West_Net([Internal-West]):::westObj
    External_East_Net([External-East]):::eastObj
    External_West_Net([External-West]):::westObj

    %% --- Load Balancers (FAD) ---
    FAD_East[[FAD-East]]:::eastObj
    FAD_West[[FAD-West]]:::westObj

    %% --- Server Networks ---
    Servers_East_Net([servers-east]):::eastObj
    Servers_West_Net([servers-west]):::westObj

    %% --- Bottom Section (Servers) ---
    svr01_e((svr01-e)):::eastObj
    svr02_e((svr02-e)):::eastObj
    svr03_e((svr03-e)):::eastObj

    svr01_w((svr01-w)):::westObj
    svr02_w((svr02-w)):::westObj
    svr03_w((svr03-w)):::westObj

    %% ----------------------------------------------------
    %% Connections & Interface Labels
    %% ----------------------------------------------------

    %% Inside Connections (West Side)
    Client_Inside --- |"port3 10.1.1.16"| Internal_Net
    NS2b --- |"port2 10.1.1.17"| Internal_Net
    Internal_Net --- |"port2 10.1.1.12"| FGT_West

    %% Outside Connections (East Side)
    Client_Outside --- |"port2 100.64.12.16"| External_Net
    NS1b --- |"port2 100.64.12.17"| External_Net
    External_Net --- |"port2 100.64.12.11"| FGT_East

    %% Core Mesh Interconnections (Firewalls down to Transit & FADs)
    FGT_West --- |"port3 10.1.2.12"| Internal_East_Net
    FGT_West ---- |"port4 10.1.3.12"| Internal_West_Net
    Internal_East_Net --- |"port3 10.1.2.9"| FAD_East
    Internal_West_Net --- |"port3 10.1.3.10"| FAD_West

    FGT_East ---- |"port3 100.64.11.11"| External_East_Net
    FGT_East --- |"port4 100.64.10.11"| External_West_Net
    External_East_Net --- |"port5 100.64.11.9"| FAD_East
    External_West_Net --- |"port5 100.64.10.10"| FAD_West

    %% East Server Connections
    FAD_East --- |"port4 10.1.4.9"| Servers_East_Net
    Servers_East_Net --- |"port2 10.1.4.6"| svr01_e
    Servers_East_Net --- |"port2 10.1.4.7"| svr02_e
    Servers_East_Net --- |"port2 10.1.4.8"| svr03_e

    %% West Server Connections
    FAD_West --- |"port4 10.1.5.10"| Servers_West_Net
    Servers_West_Net --- |"port2 10.1.5.13"| svr01_w
    Servers_West_Net --- |"port2 10.1.5.14"| svr02_w
    Servers_West_Net --- |"port2 10.1.5.15"| svr03_w


```

### Device Access

1. Log into the **US Sunnyvale IPsec VPN**.

{{< figure src="Sunnyvale-VPN.png" >}}

2. Using the link your instructor sent you, go to the evoke admin page
3. Click **Edit**

{{< figure src="evoke1.png" >}}

On this page you see **External IP Addresses**, **Internal IP Addresses**, **Credential** access etc...

To access any of the clients use the spice console in the far right.
To reach the FortiADC's use the **External IP**.

{{< figure src="evoke2.png" >}}

| Device Name     | Username       | Password       | 
|-----------------|----------------|----------------|
| FAD-East        | ```admin```    | ```fortinet``` |
| FAD-West        | ```admin```    | ```fortinet``` |
| Client_Inside   | ```fortinet``` | ```fortinet``` |
| Client_Outside  | ```fortinet``` | ```fortinet``` |

### Set screen resolution on Lubuntu

1. Click in the lower left corner to open the **Application Menu**
2. In the search field type **Monitor**
3. Select **Monitor Settings**
4. Set the screen resoltion to **1600x900**
5. Click **Apply**
6. Click **Save**
7. **Close**

{{< figure src="lubuntu-desktop4.png" >}}



