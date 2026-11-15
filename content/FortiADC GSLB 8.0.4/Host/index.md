---
title: "Host"
LinkTitle: "Host"
weight: 9 
---

### Hosts

Host settings are used to form the zone configuration and resource records in the generated DNS zone used for global load balancing.

The Host Configuration to Generated Zone File Map shows how the host settings are mapped to zone settings and resource records. The domain is used in the generated zone configuration file name. The IP address and weight are derived from the virtual server pool.

**Host configuration and the generated DNS zone**

```mermaid
graph TB
    subgraph fqdn_generate["Host Configuration to Generated Zone File Map"]

    subgraph GeneratedZone["Generated Zone File"]
    direction TB
        zone-filename("File Name Suffix: _example_com")
        zone-domain-name("Domain Name")
        %%zone("Zone Records: Host Name: www")
        zone-host-name("Host Name")
        zone-ipaddress("IP Address")
        zone-weight("Weight")
    end
   
   subgraph HostConfig["Host Configuration"]
   direction TB
        host-domain("Domain: example.com")
        host-hostname("Host Name: www")
        host-vspool("Virtual Server Pool")
    end
    %%hostname <------> fqdn
    host-domain <------> zone-filename
    host-domain <------> zone-domain-name
    host-hostname <------> zone-host-name
    host-vspool <------> zone-ipaddress
    host-vspool <------> zone-weight
    
    style fqdn_generate fill:#C1D1E8,stroke:#111,stroke-width:2px,color:#000,rx:20px,ry:20px
    style HostConfig fill:#D8E1ED,stroke:#111,color:#000,rx:20px,ry:20px
    style GeneratedZone fill:#D8E1ED,stroke:#111,color:#000,rx:20px,ry:20px
end
```

**Before you begin:**
- You must have created the global virtual server pools you want to use.
- You must have Read-Write permission for Global Load Balance settings.

After you have created a host configuration object, it can be used to form the zone and resource records in the generated DNS zone configuration.

> [!details]- ### Configure FAD-East
>
>### FAD-East
>**Username:** ```admin``` 
> 
>**Password:** ```fortinet```
> 
>1. Go to **Global Load Balance > GLB Configuration**
>2. Click **Create New**
>
>{{< figure src="fad-east-host1.png" >}}
> 
>3. Configure the **Name** ```fortiware-east```
>4. Configure the **Host Name** ```www```
>5. Configure the **Domain Name** ```fortiware.zzz.```
>6. Move the **DEFAULT_DNS_POLICY** to the left into the **Selected Items** box
>7. Configure **Default Feedback IPv4** to ```127.0.0.1```
>8. Toggle **FortiView** to **ON**
>
>{{< figure src="fad-east-host2.png" >}}
> 
>9. Click **Save**
>
> **To add a Virtual Server Pool:**
> 
>10. Click **Create New**
>
>{{< figure src="fad-east-host3.png" >}}
>
>11. Configure the **Name** ```dvwa-east-int```
>12. Select the **Virtual Server Pool** <mark>dvwa-east-int</mark>
>13. Select the **ISP** <mark>ISP-East</mark>
>
>{{< figure src="fad-east-host4.png" >}}
> 
>14. Click **Save**
>15. Repeat Steps 10-14 for ```dvwa-west-int```
>
>{{< figure src="fad-east-host5.png" >}}
> 
>16. Click **Save** again
>
>{{< figure src="fad-east-host6a.png" >}}
>
>To see the dynamically generated zone file once the host section has been completed go to **Global Load Balance > Zone and DNS Security** and click on the **Zone** Tab.
> 
>{{< figure src="fad-east-zone-file.png" >}}

> [!details]- ### Configure FAD-West
>
>### FAD-West
>
>**Username:** ```admin```
> 
>**Password:** ```fortinet```
> 
>1. Go to **Global Load Balance > GLB Configuration**
>2. Click **Create New**
>
>{{< figure src="fad-west-host1.png" >}}
> 
>3. Configure the **Name** ```fortiware-west```
>4. Configure the **Host Name** ```www```
>5. Configure the **Domain Name** ```fortiware.zzz.```
>6. Move the **DEFAULT_DNS_POLICY** to the left into the **Selected Items** box
>7. Configure **Default Feedback IPv4** to ```127.0.0.1```
>8. Toggle **FortiView** to **ON**
>
>{{< figure src="fad-west-host2.png" >}}
> 
>9. Click **Save**
>
> **To add a Virtual Server Pool:**
> 
>10. Click **Create New**
>
>{{< figure src="fad-west-host3.png" >}}
>
>11. Configure the **Name** ```dvwa-east-int```
>12. Select the **Virtual Server Pool** <mark>dvwa-east-int</mark>
>13. Select the **ISP** <mark>ISP-East</mark>
>
>{{< figure src="fad-west-host4.png" >}}
> 
>14. Click **Save**
>15. Repeat Steps 10-14 for ```dvwa-west-int```
>
>{{< figure src="fad-west-host5.png" >}}
> 
>16. Click **Save** again
>
>{{< figure src="fad-west-host6a.png" >}} 
>
>To see the dynamically generated zone file once the host section has been completed go to **Global Load Balance > Zone and DNS Security** and click on the **Zone** Tab.
> 
>{{< figure src="fad-west-zone-file.png" >}}

