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