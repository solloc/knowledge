# 3DEXPERIENCE

Dassault Systèmes 3DEXPERIENCE Platform

* ENOVIA
* CATIA V6
* MatrixOne

## MQL

Matrix Query Language

### Demote Business Object

Definition:
``` MQL
demote bus <type> <name> <revision>;
```

Example:
``` MQL
demote bus Part 19010860000 A;
```

### Query Trigger

Definition:
``` MQL
temp query bus "eService Trigger Program Parameters" <Name> *;
```

Example:
``` MQL
temp query bus "eService Trigger Program Parameters" *enit* *;
```

### Deactivate Trigger

Example:
``` MQL
mod businessobject "eService Trigger Program Parameters" "ProductToReleasedTrigger" "ProductToReleased" current "Inactive";
```

### Add/Remove Trigger from Attribute/Type/Policy

Read:
``` MQL
print attribute PRE_FIX.ATT_Name select trigger dump;

print type DerivedOutputEntity select trigger dump;

print policy 'Change Action' select state[Approved].trigger dump;
```

Add:
``` MQL
mod attribute PRE_FIX.ATT_Name add trigger modify action emxTriggerManager input AttributeModificationTrigger;

mod type DerivedOutputEntity add trigger checkin action emxTriggerManager input CheckinTrigger;
```

Remove:
```MQL
mod attribute PRE_FIX.ATT_Name remove trigger modify action;

mod type DerivedOutputEntity remove trigger checkin action;
```
