# Devices

!!! Audit_Step
    Navigate to the rack detail page for the rack that the device is in. You can accomplish this by clicking on the name of the rack in the rack table.
    Use the rack elevation displayed to the right of the page to select the bottom RU occupied by the device in order to prepopulate the device location information.
---

!!! Audit_Step
    If the device is not racked or is a child device, such as devices that are not designed to be rack mounted and sit on shelves or rest on top of other devices in the rack, select the "add a non-racked device" button located below the elevations.
---

## Parent/child

When auditing parent/child devices audit the parent device before the child. Devices that sit on shelves or rest on top of other devices will need something to represent the space that they occupy in the rack. In order to do this, create a parent device with manufacturer: "Occupied Space" and device type:"(RU height) of Occupied Space" to represent the occupied space. See the [Parent/child](device-types.md#parentchild-status) section of the device type guide for more info on these types of relationships.

## Name

This is the name that the client has assigned to this device.

!!! Audit_Step
    Input the **Name** of the device in the text box.
---

## Device Role

A Device must be designated as one of the following roles:

* Firewall: A network security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules.
* Infrastructure: Things that support or hold other devices.
* Network: A type of device that aids in distributing connectivity to other devices.
* Patch Panel: A mounted assembly that connects incoming and outgoing cables.
* Power: Devices that provide or distribute power to other devices.
* Server: A device that accepts and responds to requests made over a network.
* Storage: A type of server that is used to store, access, secure and manage digital data, files and services.


!!! Audit_Step
    Select the **Device role** of the device from the dropdown.
---

## Manufacturer

This is the manufacturer or make of the device

!!! Audit_Step
    Select the **Manufacturer** of the device from the dropdown. If the Manufacturer is not listed select Add New Manufacturer to add it to the database.
    See the [Manufacturer guide](manufacturers.md) for further information on adding manufacturers.
---

## Device Type

This is the device type or model of the device

!!! Audit_Step
    Select the **Device Type** of the device from the dropdown. If the Device Type is not listed select Add New Device type to add it to the database. See the [Device type guide](device-types.md) for further information on adding device types.
---

## Serial Number

This is the unique identifier assigned incrementally or sequentially to a device by the manufacturer, to uniquely identify it.

!!! Audit_Step
    Input the **Serial Number** of the device in the text box.
---

!!! Audit_Step
    Select the create button to submit the record.
---

!!! Audit_Step
    If the device just audited is a child device, navigate to the device detail page of the parent and add the child device to a device bay in the parent device.
---
