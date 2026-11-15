---
title: "What's New"
LinkTitle: "What's New"
weight: 2
---

### Global Load Balance

**Response Policy Zone (RPZ) Support for GLB Zones 8.0.4**

You can now configure Response Policy Zones (RPZ) within Global Load Balance (GLB) zones to act as a DNS firewall. RPZ allows FortiADC to intercept DNS queries for known malicious or unwanted domains and apply customized policy actions, such as returning an NXDOMAIN response to block access or redirecting client requests to a secure walled garden.

1. Go to **Global Load Balance / Zone and DNS Security / Zone**
2. Click **Create New**
3. Enable **Response Policy Zone**
4. Select the **RPZ Action**

**Options are:**
- **No Override** - Follow actions defined in zone records. The local domain list has no effect.
- **Walled Garden** - Return a CNAME pointing to the configured destination.
- **NXDomain** - Return a non-existent-domain response.

**Walled Garden** and **NXDOMAIN** override record-defined actions. Hostnames in **Zone Records** also trigger the selected action.

{{< figure src="rpz-zone.png" >}}

**Global Load Balancing Service Overview and Onboarding 8.0.4**

You can now review end-to-end service relationships across your global deployment from the new GLB Onboarding page in the web UI. This centralized overview maps configured hostnames directly to their associated virtual server pools and backend servers, complete with real-time operational status indicators to accelerate setup verification and service troubleshooting. 

Go to **Global Load Balance / GLB Onboarding**

{{< figure src="service-overview.png" >}}

**Global Server Load Balancing Traffic Log Enhancements 8.0.4**

You can now monitor authoritative DNS queries across all hosted DNS zones under the newly renamed GLB DNS category in Traffic Log. Enhanced logging captures query events for Primary, Secondary, and Forward zones, expands supported record types to include PTR, TXT, MX, SRV, NS, CNAME, and CAA, and introduces granular log fields such as Domain Name and Record Type for streamlined auditing and security analysis.

{{<figure src="glb-dns.png" title="Log View">}}
{{<figure src="glb-dns1.png" title="Log Detail View">}}