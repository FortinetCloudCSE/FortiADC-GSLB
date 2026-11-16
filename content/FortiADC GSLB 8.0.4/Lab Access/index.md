---
title: "Lab Access"
LinkTitle: "Lab Access"
weight: 3
---



### Lab Network Diagram

```mermaid
graph TD
    %% Nodes Defintions
    %% --- Top Section (Inside Network / FGT-West) ---
    classDef default fill:#E1E4Eb
    
    Client_Inside((Client_Inside))
    %% NS2((NS2))
    NS2b((NS2b))
    
    Internal_Net([Internal])
    FGT_West[[FGT-West]]

    %% --- Left Section (servers-east / FAD-East) ---
    svr01_e((svr01-e))
    svr02_e((svr02-e))
    svr03_e((svr03-e))
    
    Servers_East_Net([servers-east])
    FAD_East[[FAD-East]]

    %% --- Right Section (servers-west / FAD-West) ---
    svr01_w((svr01-w))
    svr02_w((svr02-w))
    svr03_w((svr03-w))
    
    Servers_West_Net([servers-west])
    FAD_West[[FAD-West]]

    %% --- Bottom Section (External / FGT-East) ---
    %% NS1((NS1))
    Client_Outside((Client_Outside))
    NS1b((NS1b))
    
    External_Net([External])
    FGT_East[[FGT-East]]

    %% --- Core Transit Networks / Subnets ---
    Internal_East_Net([Internal-East])
    Internal_West_Net([Internal-West])
    External_East_Net([External-East])
    External_West_Net([External-West])

    %% ----------------------------------------------------
    %% Connections & Interface Labels
    %% ----------------------------------------------------
    
    %% Top Group to Internal Network
    Client_Inside --- |"port3 10.1.1.16"| Internal_Net
    %% NS2           --- |"port2 10.1.1.15"| Internal_Net
    NS2b          --- |"port2 10.1.1.17"| Internal_Net
    Internal_Net  --- |"port2 10.1.1.12"| FGT_West

    %% Left Group to servers-east
    svr01_e          --- |"port2 10.1.4.6"| Servers_East_Net
    svr02_e          --- |"port2 10.1.4.7"| Servers_East_Net
    svr03_e          --- |"port2 10.1.4.8"| Servers_East_Net
    Servers_East_Net --- |"port4 10.1.4.9"| FAD_East

    %% Right Group to servers-west
    svr01_w          --- |"port2 10.1.5.13"| Servers_West_Net
    svr02_w          --- |"port2 10.1.5.14"| Servers_West_Net
    svr03_w          --- |"port2 10.1.5.15"| Servers_West_Net
    Servers_West_Net --- |"port4 10.1.5.10"| FAD_West

    %% Bottom Group to External Network
    %% NS1              --- |"port2 100.64.12.15"| External_Net
    Client_Outside   --- |"port2 100.64.12.16"| External_Net
    NS1b             --- |"port2 100.64.12.17"| External_Net
    External_Net     --- |"port2 100.64.12.11"| FGT_East

    %% Core Mesh Interconnections
    FGT_West --- |"port3 10.1.2.12"| Internal_East_Net
    FGT_West --- |"port4 10.1.3.12"| Internal_West_Net

    Internal_East_Net --- |"port3 10.1.2.9"| FAD_East
    Internal_West_Net --- |"port3 10.1.3.10"| FAD_West

    FGT_East --- |"port3 100.64.11.11"| External_East_Net
    FGT_East --- |"port4 100.64.10.11"| External_West_Net

    External_East_Net --- |"port5 100.64.11.9"| FAD_East
    External_West_Net --- |"port5 100.64.10.10"| FAD_West
    
    style Client_Inside fill:#bbd3fa;
    style NS2b fill:#bbd3fa;
    style Internal_Net fill:#bbd3fa;
    style Internal_East_Net fill:#bbd3fa;
    style Internal_West_Net fill:#bbd3fa;
    style FGT_West fill:#bbd3fa;
    style FAD_East fill:#bbd3fa;
    style Servers_East_Net fill:#bbd3fa;
    style svr01_e fill:#bbd3fa;
    style svr02_e fill:#bbd3fa;
    style svr03_e fill:#bbd3fa;
    
    style Client_Outside fill:#d9fada;
    
    style Servers_West_Net fill:#d9fada;
    style NS1b fill:#d9fada;
    style External_Net fill:#d9fada;
    style External_West_Net fill:#d9fada;
    style External_East_Net fill:#d9fada;
    style FAD_West fill:#d9fada;
    style FGT_East fill:#d9fada;
    style Servers_West_Net fill:#d9fada;
    style svr01_w fill:#d9fada;
    style svr02_w fill:#d9fada;
    style svr03_w fill:#d9fada;
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



