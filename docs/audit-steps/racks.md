# Racks

The rack model represents a physical two- or four-post equipment rack in which equipment is mounted. Each rack must be assigned to a site. Rack height is measured in *rack units* (U); racks are commonly between 42U and 48U tall, you can define racks of arbitrary height. A toggle is provided to indicate whether rack units are in ascending or descending order.

Each rack is assigned a name and (optionally) a separate facility ID. The facility will often assign a seemingly arbitrary ID to a rack (for example, "M204.313") whereas internally it is referred to as "R113." A unique serial number may also be associated with each rack.  

!!! Audit_Step
    Select the **Site** that you are auditing from the dropdown and input the **Name** of the rack in the text box
---

## Dimensions
A rack must be designated as one of the following types:

* 2-post frame
* 4-post frame
* 4-post cabinet
* Wall-mounted frame
* Wall-mounted cabinet

Each rack has two faces (front and rear) on which devices can be mounted. Rail-to-rail width may be 19 or 23 inches.

!!! Audit_Step
    Select the **Type**, **width**, and **Height** from the dropdowns.
---


## Rack Groups

Racks can be arranged into groups. As with sites, how you choose to designate rack groups will depend on the nature of the data center. Rack Groups are utilized to create multi- tenanted sites with racks being grouped into site specific naming conventions. Site and rack group instructions are found [here](./sitegroup.md).

!!! Audit_Step
    Select the create button to submit the record.
---
