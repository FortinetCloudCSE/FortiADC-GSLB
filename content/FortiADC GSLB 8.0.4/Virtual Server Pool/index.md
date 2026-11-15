---
title: "Virtual Server Pool"
LinkTitle: "Virtual Server Pool"
weight: 8 
---

### Virtual Server Pool

**Configuring virtual server pools**

The virtual server pool configuration defines the set of virtual servers that can be matched in DNS resource records, so it should include, for example, all the virtual servers that can be answers for DNS requests to resolve www.example.com.

You also specify the key parameters of the global load balancing algorithm, including proximity options, status checking options, load balancing method, and weight.

**The DNS response is an ordered list of answers. Virtual servers that are unavailable are excluded. Available virtual servers are ordered based on the following priorities:**
- Geographic proximity
- Dynamic proximity
- Weighted round robin

**A client that receives DNS response with a list of answers tries the first and only proceeds to the next answers if the first answer is unreachable.
Before you begin:**
- You must have created GLB Servers configuration objects.
- You must have Read-Write permission for Global Load Balance settings.

After you have created a virtual server pool configuration object, you can specify it in the global load balancing **host** configuration.

> [!details]- ### Configure FAD-East
>
>### FAD-East
>
>**Username:** ```admin``` 
> 
>**Password:** ```fortinet```
> 
>1. Go to **Global Load Balance > GLB Configuration**.
>2. Click the **Virtual Server Pool** tab.
>3. Click **Create New** to display the configuration editor.
>
>{{< figure src="fad-east-virtual-server.png" >}}
>
>4. Configure the **Name** ```dvwa-east-int```
>5. **Save**
>
>{{< figure src="fad-east-virtual-server-newa.png" >}}
>
>**To add a Server Member:**
>
>6. Click **Create New**
>
>{{< figure src="fad-east-select-server.png" >}}
>
>7. Select **Server** <mark>FAD-East</mark>
>
>{{< figure src="fad-east-add-server-membera.png" >}}
>
>8. Select **Server Member** <mark>fad-east-dvwa-https-int</mark>
>9. **Save**
>
>**Repeat**
>
>10. Click **Create New**
>11. Select **Server** <mark>FAD-West</mark>
>
>{{< figure src="fad-east-select-servera.png" >}}
>
>12. Select **Server Member** <mark>fad-west-dvwa-https-int</mark>
>
>{{< figure src="fad-east-dvwa-https-int.png" >}}
>
>13. Click **Save**
>
>{{< figure src="fad-east-dvwa-int.png" >}}
>
>14. Click **Save** again
>
>{{< figure src="fad-east-all-virt-servers-a.png" >}}
> 
>**Repeat for Virtual Server Pool** <mark>dvwa-west-int</mark>
> 
>1. Go to **Global Load Balance > GLB Configuration**.
>2. Click the **Virtual Server Pool** tab.
>3. Click **Create New** to display the configuration editor.
>
>{{< figure src="fad-east-virtual-server.png" >}}
>
>4. Configure the **Name** ```dvwa-west-int```
>5. **Save**
>
>{{< figure src="fad-east-dvwa-west-vspool.png" >}}
>
>**To add a Server Member:**
>
>6. Click **Create New**
>
>{{< figure src="fad-east-select-server.png" >}}
>
>7. Select **Server** <mark>FAD-East</mark>
>
>{{< figure src="fad-east-add-server-membera.png" >}}
>
>8. Select **Server Member** <mark>fad-east-dvwa-https-int</mark>
>9. **Save**
>
>**Repeat**
>
>10. Click **Create New**
>11. Select **Server** <mark>FAD-West</mark>
>
>{{< figure src="fad-east-select-servera.png" >}}
>
>12. Select **Server Member** <mark>fad-west-dvwa-https-int</mark>
>
>{{< figure src="fad-east-dvwa-https-int.png" >}}
>
>13. Click **Save**
>
>{{< figure src="fad-east-dvwa-west-int.png" >}}
>
>14. Click **Save** again
>
>{{< figure src="fad-east-dvwa-vspool.png" >}}

> [!details]- ### Configure FAD-West
>
>### FAD-West
>
>**Username:** ```admin``` 
> 
>**Password:** ```fortinet```
> 
>1. Go to **Global Load Balance > GLB Configuration**.
>2. Click the **Virtual Server Pool** tab.
>3. Click **Create New** to display the configuration editor.
>
>{{< figure src="fad-west-virtual-server.png" >}}
>
>4. Configure the **Name** ```dvwa-east-int```
>5. Click **Save**
>
>{{< figure src="fad-west-virtual-server-newa.png" >}}
>
>**To add a Server Member:**
>
>6. Click Create **New**
>
>{{< figure src="fad-west-select-server.png" >}}
>
>7. Select **Server** <mark>FAD-East</mark>
>
>{{< figure src="fad-west-add-server-membera.png" >}}
>
>8. Select **Server Member** <mark>fad-east-dvwa-https-int</mark>
>9. **Save**
>
>**Repeat**
>
>10. Click **Create New**
>11. Select **Server** <mark>FAD-West</mark>
>
>{{< figure src="fad-west-select-servera.png" >}}
>
>12. Select **Server Member** <mark>fad-west-dvwa-https-int</mark>
>
>{{< figure src="fad-west-dvwa-https-int.png" >}}
>
>13. Click **Save**
>
>{{< figure src="fad-west-dvwa-int.png" >}}
>
>14. Click **Save** again
>
>{{< figure src="fad-west-all-virt-servers-a.png" >}}
> 
>**Repeat for Virtual Server Pool** <mark>dvwa-west-int</mark>
> 
>1. Go to **Global Load Balance > GLB Configuration**.
>2. Click the **Virtual Server Pool** tab.
>3. Click **Create New** to display the configuration editor.
>
>{{< figure src="fad-west-virtual-server.png" >}}
>
>4. Configure the **Name** ```dvwa-west-int```
>5. **Save**
>
>{{< figure src="fad-west-dvwa-west-vspool.png" >}}
>
>**To add a Server Member:**
>
>6. Click **Create New**
>
>{{< figure src="fad-west-select-server.png" >}}
>
>7. Select **Server** <mark>FAD-East</mark>
>
>{{< figure src="fad-west-add-server-membera.png" >}}
>
>8. Select **Server Member** <mark>fad-east-dvwa-https-int</mark>
>9. **Save**
>
>**Repeat**
>
>10. Click **Create New**
>11. Select **Server** <mark>FAD-West</mark>
>
>{{< figure src="fad-west-select-servera.png" >}}
>
>12. Select **Server Member** <mark>fad-west-dvwa-https-int</mark>
>
>{{< figure src="fad-west-dvwa-https-int.png" >}}
>
>13. Click **Save**
>
>{{< figure src="fad-west-dvwa-west-int.png" >}}
>
>14. Click **Save** again
>
>{{< figure src="fad-west-dvwa-vspool.png" >}}

**Configuration Guidelines**

| Settings                       | Guidelines                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|--------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Preferred                      | **None:** No preference.<br>**Geo:** If selected, virtual servers with the same GEO information as the local DNS address will respond.<br>**Geo-ISP:** If selected, virtual servers with the same ISP information as the local DNS address will respond first, and virtual servers with the same GEO information as the local DNS address will respond second.<br>**RTT:** Virtual servers with the shortest latency link or closest to the data center will respond.<br>**Least-Connnections:** Virtual servers with the least connections will respond first.<br>**Connection-Limit:** Virtual servers will be responded by their connection limit determined by virtual servers' weight: the greater the weight of a virtual server, the more responses it will get.<br>**Bytes-Per-Second:** Virtual servers with the lowest traffic will respond.<br>**Server-Performance:** Virtual servers with better server-performancec in the CPU or Memory (whichever one you give more weight to) will respond. |
| Alternate                      | Same as above.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Load Balance Method            | Weighted Round Robin                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Check Server Status            | Enable/disable polling of the local FortiADC SLB. If the server is unresponsive, its virtual servers are not selected for DNS answers.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Check Virtual Server Existence | Enable/disable checks on whether the status of the virtual servers in the virtual server list is known. Virtual servers with unknown status are not selected for DNS answers.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Member                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Server                         | Select a GSLB Server configuration object                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Server Member                  | Select the name of the virtual server that is in the servers virtual server list configuration.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Weight                         | Assigns relative preference among members—higher values are more preferred and are assigned connections more frequently.<br>The default is 1. The valid range is 1-255.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Backup                         | Enable to designate the member as a backup. Backup members are inactive until all main members are down.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
