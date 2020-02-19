# Cables

A cable represents a physical connection between two termination points, such as between a console port and a patch panel port, or between two network interfaces. Cables can be traced through pass-through ports to form a complete path between two endpoints. In the example below, three individual cables comprise a path between the two connected endpoints.

```
|<------------------------------------------ Cable Path ------------------------------------------->|

  Device A                   Patch Panel A                 Patch Panel B                  Device B
+-----------+               +-------------+               +-------------+               +-----------+
| Interface | --- Cable --- | Front Port  |               | Front Port  | --- Cable --- | Interface |
+-----------+               +-------------+               +-------------+               +-----------+
                            +-------------+               +-------------+
                            |  Rear Port  | --- Cable --- |  Rear Port  |
                            +-------------+               +-------------+
```

All connections between device components are represented using cables.

Cables are also used to associated ports and interfaces with circuit terminations. To do this, first create the circuit termination, then navigate the desired component and connect a cable between the two.

!!! Audit_Step
    Navigate to the device details page for the device that the A side of the cable plugs into. You can accomplish this by clicking on the name of the device in either the rack elevation view or the device table. Locate the port that it plugs into at the bottom of the device details page.
---

!!! Audit_Step
    If there are no ports shown or the port you are looking for is not displayed at the bottom of the device details page you must add ports to this device to connect the cable. See the [Device Components](device-types.md#device-components) section of the device type guide for information on how to add ports but instead of executing this at the device type level do it from the device
---

!!! Audit_Step
    Select the connect button (green with arrows) then choose the type of port the b side of the cable connects to.
---

## B Side Information

!!! Audit_Step
    Using the Site, Rack, and Device dropdowns, select the device that has the port that the b side of the cable connects to and then select the name of that port from the name dropdown.
---

## Cable Information

!!! Audit_Step
    Input into the cable fields the characteristics of the cable.
---

!!! Audit_Step
    Once finished, submit the record by clicking connect.
---
