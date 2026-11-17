---
title: "Data Centers"
LinkTitle: "Data Centers"
weight: 60 
---

### Data Centers

The data center configuration sets key properties: Location and/or ISP and ISP province. These properties are used in the global load balancing algorithm that selects the FortiADC in closest proximity to the client.

**Before you begin:**

- If you want to select a user-defined ISP address book, you must create it before creating the data center configuration.
- You must have Read-Write permission for Global Load Balance settings.

After you have created a data center configuration object, you can specify it in the global load balance servers configuration.

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
>1. Go to **Global Load Balance > GLB Configuration**.
>2. Click the **Data Center** tab.
>3. Click **Create New** to display the configuration editor.
>
>{{< figure src="datacenter.png" >}}
>
>4. Configure the **Name** ```Datacenter-East``` 
>5. Select the **Location** <mark>United States</mark>
>
>{{< figure src="fad-east-datacenter-east.png" >}}
>
>6. **Save**
>7. Click **Create New**
>8. Configure the **Name** ```Datacenter-West``` 
>9. Select the **Location** <mark>United States</mark>
>
>{{< figure src="fad-east-datacenter-west.png" >}}
>
>10. **Save**
>
>{{< figure src="datacenter5.png" >}}

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
>1. Go to **Global Load Balance > GLB Configuration**.
>2. Click the **Data Center** tab.
>3. Click **Create New** to display the configuration editor.
>
>{{< figure src="datacenter2.png">}}
>
>4. Configure the **Name** ```Datacenter-East``` 
>5. Select the **Location** <mark>United States</mark>
>
>{{< figure src="fad-west-datacenter-east.png">}}
>
>6. **Save**
>7. Click **Create New**
>8. Configure the **Name** ```Datacenter-West``` 
>9. Select the **Location** <mark>United States</mark>
>
>{{< figure src="fad-west-datacenter-west.png" >}}
>
>10. **Save**
>
>{{< figure src="datacenter6.png" >}}

**Data Center Configuration Guidelines**

| Settings    | Guidelines                                                                                                                                                                                                                                |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Name        | Configuration name. Valid characters are A-Z, a-z, 0-9, _, and -. No spaces. You reference this name in the global load balance servers configuration.<br>**Note:** After you initially save the configuration, you cannot edit the name. |
| Location    | Select a location from the drop-down list menu. See the note below.                                                                                                                                                                       |
| Description | Optional description to help administrators know the purpose or usage of the configuration.                                                                                                                                               |

**Note:** Stating from FortiADC 5.x.x, the GUI shows the full country or region names listed in alphabetical order for location list and data center configuration. The Console uses country or region name abbreviations instead. The abbreviations are done in accordance with the ISO standards. So if you configure a location list or data center from the Console, be sure to consult [ISO-3166-1](https://en.wikipedia.org/wiki/ISO_3166-1) and/or [ISO 3166-2:CN](https://en.wikipedia.org/wiki/ISO_3166-2:CN) for the correct abbreviations to use. See the following example commands:

```text
config global-load-balance topology
    edit "tp1"
      set member ZZ US CN65
    next
end
```

Where ZZ stands for Reserved, US for United States, and CN65 for China, Xingjiang

