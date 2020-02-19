# Device Types

A device type represents a particular make and model of hardware that exists in the real world. Device types define the physical attributes of a device (rack height and depth) and its individual components (console, power, and network interfaces).

Device types are instantiated as devices installed within racks. For example, you might define a device type to represent a Juniper EX4300-48T network switch with 48 Ethernet interfaces. You can then create multiple devices of this type named "switch1," "switch2," and so on. Each device will inherit the components (such as interfaces) of its device type at the time of creation. (However, changes made to a device type will **not** apply to instances of that device type retroactively.)

## Manufacturers

Each device type must be assigned to a manufacturer. The model number of a device type must be unique to its manufacturer.

!!! Audit_Step
    Select the **Manufacturer** of the new device type from the dropdown.
---

## Model

This is the model name that will be referred to when adding devices. Include series/version numbers, capitalization, and all other details in the model name excluding manufacturer.

!!! Audit_Step
    Input the **Model** of the new device type in the text box.
---

## Height & Depth

This is the number of rack units a device occupies. If the device spans the full length of the rack then the device is full depth. If the device sits on a shelf/chassis set the **Height** to 0 and **parent/child status** to child.  

!!! Audit_Step
    Input the **Height** (in (U) or every three bolt holes) in the input box and **Depth** using the check button.
---

## Parent/child Status

Some devices house child devices which share physical resources, like space and power, but which functional independently from one another. A common example of this is blade server chassis. If the device is not designed to be rack mounted, it is considered a child device. When such a device is audited it will be represented as a child of the infrastructure that supports it in the rack (the parent).  Each device type is designated as one of the following:

* A parent device (which has device bays)
* A child device (which must be installed in a device bay)
* Neither

!!! Audit_Step
    Select the **Parent/child Status** from the dropdown. Ignore if the device is standalone.
---

!!! Submit
    Select **Create** to submit the device type record.
---

## Device Components

Each device type is assigned a number of component templates which define the physical components within a device. These are:

* Console ports
* Console server ports
* Power ports
* Power outlets
* Network interfaces
* Front ports
* Rear ports
* Device bays (which house child devices)

Whenever a new device is created, its components are automatically created per the templates assigned to its device type. For example, a Juniper EX4300-48T device type might have the following component templates defined:

* One template for a console port ("Console")
* Two templates for power ports ("PSU0" and "PSU1")
* 48 templates for 1GE interfaces ("ge-0/0/0" through "ge-0/0/47")
* Four templates for 10GE interfaces ("xe-0/2/0" through "xe-0/2/3")

Once component templates have been created, every new device that you create as an instance of this type will automatically be assigned each of the components listed above.

There are eight types of device components which comprise all of the interconnection logic:

* Console ports
* Console server ports
* Power ports
* Power outlets
* Network interfaces
* Front ports
* Rear ports
* Device bays

### Console

Console ports connect only to console server ports.

### Power

Power ports connect only to power outlets.

### Interfaces

Interfaces connect to one another in a symmetric manner: If interface A connects to interface B, interface B therefore connects to interface A.

Each interface is a assigned a type denoting its physical properties.

### Pass-through Ports (Front & Rear)

Pass-through ports are used to model physical terminations which comprise part of a longer path, such as a cable terminated to a patch panel. Each front port maps to a position on a rear port. A 24-port UTP patch panel, for instance, would have 24 front ports and 24 rear ports. Although this relationship is typically one-to-one, a rear port may have multiple front ports mapped to it. This can be useful for modeling instances where multiple paths share a common cable (for example, six different fiber connections sharing a 12-strand MPO cable).

Pass-through ports can also be used to model "bump in the wire" devices, such as a media convertor or passive tap.

Rear must be created before front ports.

### Device Bays

Device bays represent the ability of a device to house child devices. For example, you might install four blade servers into a 2U chassis. The chassis would appear in the rack elevation as a 2U device with four device bays. Each server within it would be defined as a 0U device installed in one of the device bays. Child devices do not appear within rack elevations or the "Non-Racked Devices" list within the rack view.

Child devices are first-class Devices in their own right: that is, fully independent managed entities which don't share any control plane with the parent.  Just like normal devices, child devices have their own platform (OS), role, tags, and interfaces.

!!! Audit_Step
    Select the **Add Components** dropdown and add any components the device has using the fields specific to each component type.
---
