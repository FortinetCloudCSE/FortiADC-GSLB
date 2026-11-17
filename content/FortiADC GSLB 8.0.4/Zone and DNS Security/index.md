---
title: "Zone and DNS Security"
LinkTitle: "Zone and DNS Security"
weight: 100
---

### Zone and DNS Security

The Zone and DNS Security module provides the essential tools for managing DNS authority and securing the resolution process. While the GLB Configuration module defines where traffic should go, this module manages the public presentation of those records and ensures the DNS infrastructure is protected against common attacks. By configuring zones, policies, and security parameters, you ensure that your global application names are resolved reliably and securely for clients worldwide.

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
>1. Go to **Global Load Balance > Zone and DNS Security**
>2. Click on the **Zone** Tab
>
>You should see the generated zone file we created in the host section.
>
>{{< figure src="fad-east-zone-1.png" >}}
>
>**Check the Policy**
> 
>4. Go to **Global Load Balance > Zone and DNS Security**
>5. Click on the **Global DNS Policy** Tab
>
>{{< figure src="fad-east-global-dns-policy.png" >}}

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
>1. Go to **Global Load Balance > Zone and DNS Security**
>2. Click on the **Zone** Tab
>
>You should see the generated zone file we created in the host section.
>
>{{< figure src="fad-west-zone-1.png" >}}
>
>**Check the Policy**
> 
>4. Go to **Global Load Balance > Zone and DNS Security**
>5. Click on the **Global DNS Policy** Tab
>
>{{< figure src="fad-east-global-dns-policy.png" >}}