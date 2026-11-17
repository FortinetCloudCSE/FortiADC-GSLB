---
title: "Link"
LinkTitle: "Link"
weight: 70 
---
### Link

In FortiADC Global Server Load Balancing (GSLB), the global load balance link object represents an ISP or WAN access path associated with a specific data center.

**Link is used to:**
- **Define Access Points and ISPs** - Identifying the ISP and data center details for external network connections.
- **Integrate Link Load Balancing (LLB) Gateways** - Mapping the gateways from the local Server Load Balancing (SLB) or Link Load Balancing (LLB) configuration so the GSLB module can track the health and status of the link.
- **Share RTT Metrics** - Allowing the GSLB system to monitor the status of the link and share Round-Trip Time (RTT) detection results for dynamic proximity steering.

**Link Configuration Guidelines**

| Settings | Guidelines |
|----------|------------|
| Name | Configuration name. Valid characters are A-Z, a-z, 0-9, _, and -. No spaces. You reference this name in the global load balance servers configuration.<br>**Note:** After you initially save the configuration, you cannot edit the name. |
| Data Center | Select a data center from the list.<br>**Note:** You must the data center(s) configured ahead of time. |
| ISP | Select an ISP from the list. |
| Gateway | |
| Server | Select a server. |
| Gateway Name | Specify the name of a gateway. |
| or Select Here | Click the down arrow to select a gateway from the drop-down list.<br>**Note:** Use this option only when you already have a list of gateways configured on the server. |

> [!details]- ### Configure FAD-East
>
>### FAD-East
>
>**From the evoke admin console, look for the External IP for FAD-East:**
>
>{{< figure src="fad-east-access.png" >}}
>
>**Log in with:**
>
>**Username:** ```admin``` 
> 
>**Password:** ```fortinet```
>
>1. Go to **Global Load Balance > GLB Configuration**
>2. Click the **Link** tab.
>3. Click **Create New** to display the configuration editor. 
>
>{{< figure src="gslb-link.png" >}}
>
>4. Configure the **Name** ```Link-East```
>5. Select the **Data Center** <mark>Datacenter-East</mark>
>6. Select the **ISP** <mark>ISP-East</mark>
>7. **Save**
>
>{{< figure src="gslb-link-1.png" >}}
>
>**Add the Gateways:**
>
>8. Click **Create New**
>9. Select the **Server** <mark>FAD-East</mark>
>10. Configure the **Gateway Name** ```FGT-East```
>11. Click **or Select Here** and select <mark>FGT-East</mark>
>
>{{< figure src="gslb-link-2.png" >}}
>
>**Note:** Link Load Balancing needs to already be configured in order to be able to select a Gateway.
>
>12. **Save**
>
>{{< figure src="gslb-link-5.png" >}}
>
>13. Repeat steps 8 - 12 for **Link-West** as shown below.
>14. **Save**
>
>{{< figure src="gslb-link-6.png" >}}

> [!details]- ### Configure FAD-West
>
>### FAD-West
>
>**From the evoke admin console, look for the External IP for FAD-West:**
>
>{{< figure src="fad-west-accessa.png" >}}
>
>**Log in with:**
>
>**Username:** ```admin``` 
> 
>**Password:** ```fortinet```
>
>1. Go to **Global Load Balance > GLB Configuration**
>2. Click the **Link** tab.
>3. Click **Create New** to display the configuration editor.
>
>{{< figure src="gslb-link-3.png" >}}
>
>4. Configure the **Name** ```Link-West```
>5. Select the corresponding **Data Center** <mark>Datacenter-West</mark>
>6. Select the corresponding **ISP** <mark>ISP-West</mark>
>
>{{< figure src="gslb-link-4.png" >}}
>
>7. **Save**
>
>**Add the Gateways:**
>
>8. Click **Create New**
>9. Select the **Server** <mark>FAD-West</mark>
>10. Configure the **Gateway Name** ```FGT-West```
>11. Click **or Select Here** and select <mark>FGT-West</mark>
>
>{{< figure src="gslb-link-7.png" >}}
>
>**Note:** Link Load Balancing needs to already be configured in order to be able to select a Gateway.
>
>12. **Save**
>
>{{< figure src="gslb-link-8.png" >}}
>
>13. Repeat steps 8 - 12 for **Link-East** as shown below.
>14. **Save**
>
>{{< figure src="gslb-link-9.png" >}}