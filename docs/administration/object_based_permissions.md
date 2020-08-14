# Permissions

Object-based permissions enable an administrator to grant users or groups the ability to perform an action on arbitrary subsets of objects, rather than all objects of a certain type. For example, it is possible to grant a user permission to view only sites within a particular region.

# Object Permissions

A permission represents a relationship shared by several components:

* Object type(s) - One or more types of object in NetBox
* User(s)/Group(s) - One or more users or groups of users
* Action(s) - The action(s) that can be performed on an object
* Constraints - An arbitrary filter used to limit the granted action(s) to a specific subset of objects

At a minimum, a permission assignment must specify one object type, one user or group, and one action. The specification of constraints is optional: A permission without any constraints specified will apply to all instances of the selected model(s).

## Actions

There are four core actions that can be permitted for each type of object within NetBox, roughly analogous to the CRUD convention (create, read, update, and delete):

* **View** - Retrieve an object from the database
* **Add** - Create a new object
* **Change** - Modify an existing object
* **Delete** - Delete an existing object

## Constraints

Constraints are expressed as a JSON object or list representing a [Django query filter](https://docs.djangoproject.com/en/stable/ref/models/querysets/#field-lookups). As with query filters, double underscores can be used to traverse related objects or invoke lookup expressions. Some example queries and their corresponding definitions are shown below.

All attributes defined within a single JSON object are applied with a logical AND. For example, suppose you assign a permission for the site model with the following constraints.

```json
{
  "status": "active",
  "region__name": "Americas"
}
```

The permission will grant access only to sites which have a status of "active" **and** which are assigned to the "Americas" region.

To achieve a logical OR with a different set of constraints, define multiple objects within a list. For example, if you want to constrain the permission to VLANs with an ID between 100 and 199 _or_ a status of "reserved," do the following:

```json
[
  {
    "vid__gte": 100,
    "vid__lt": 200
  },
  {
    "status": "reserved"
  }
]
```

Additionally, where multiple permissions have been assigned for an object type, their collective constraints will be merged using a logical "OR" operation.

### Example Constraint Definitions

| Constraints | Description |
| ----------- | ----------- |
| `{"status": "active"}` | Status is active |
| `{"status__in": ["planned", "reserved"]}` | Status is active **OR** reserved |
| `{"status": "active", "role": "testing"}` | Status is active **OR** role is testing |
| `{"name__startswith": "Foo"}` | Name starts with "Foo" (case-sensitive) |
| `{"name__iendswith": "bar"}` | Name ends with "bar" (case-insensitive) |
| `{"vid__gte": 100, "vid__lt": 200}` | VLAN ID is greater than or equal to 100 **AND** less than 200 |
| `[{"vid__lt": 200}, {"status": "reserved"}]` | VLAN ID is less than 200 **OR** status is reserved |
