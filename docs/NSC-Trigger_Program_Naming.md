---
title: NSC:Trigger Program Naming
permalink: /NSC:Trigger Program Naming/
---

Physical files have 7 events to which 1 or more trigger programs may be
attached. These events are;

- BEFORE - \*INSERT, \*DELETE, \*UDATE
- AFTER - \*INSERT, \*DELETE, \*UDATE, \*READ

Also one trigger program may be attached to multiple events.

All trigger programs will be written in RPGILE and will use the Error
Handling Services to communicate with the RDBMS

Typically the \*BEFORE trigger programs provide validation, provision of
defaults and specialized calculations to be done before accepting the
event. In the case of the \*DELETE trigger the only validations which
are appropriate are to check that the deletion is allowed. For example,
a customer has no balance owing.

The \*AFTER trigger programs are used mainly to synchronize other files
in the database when an event has been executed.

The naming of trigger programs for all the events follows the same
pattern;

`ffffffF_xn`

Where

- `ffffffF` is the name of the physical file to which the trigger program will be attached.
- `_x` = `_B` if the program is a \*BEFORE trigger and `_A` if the program is an \*AFTER trigger.
- `n` = a sequence number from 0 to 9 for use when multiple \*BEFORE/\*AFTER trigger programs are required for the same file.

When a trigger program is attached to a file event, that link is given a unique trigger name. The default for the ADDPFTRG command is \*GEN which provides a system generated name. It is not advisable to allow this to happen as the names can sometimes be confusing and meaningless.

The convention used in IRP for these event names is as follow;

`ffffffF_xyn`

Where

- `ffffffF` is the name of the physical file to which the trigger program will be attached.
- `_x` = `_B` if the program is a \*BEFORE trigger and `_A` if the program is an \*AFTER trigger.
- `y` = I for Update, U for Update, D for Delete and R for Read.
- `n` = a sequence number from 0 to 9 for use when multiple trigger programs are required for the same file and event.