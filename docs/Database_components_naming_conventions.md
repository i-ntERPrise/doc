---
title: Database components naming conventions
permalink: /Database components naming conventions/
---
## Database components naming conventions

### Database File Naming

The broad name "FILE" in this context is used to include the following;

- Physical Data Files
    - DDL Tables
    - DDS Physical Files (unlikely to be used)
- Logical Files
    - DDL Encoded Vector Index (EVI)
    - DDL Binary Radix Index (BRI)
    - DDL View
    - DDS Logical View
    - DDS Logical Join
    - DDS Logical Non-Join (Multi/Format)

The naming standards and conventions described below apply to ALL of the
above file types.

### Physical Name Structure

`abbnnnF`

Where

- `a` = Must be an acceptable IBM i naming start character.
- `bb` = 2 alphanumeric characters. The abb characters together make up a data-set identification mnemonic that groups together files of common purpose. An example of this would be "DEB" as the Data-Set to use to group all "Debtors" related files (both Physical & Logical) together.
- `nnn` = These 3 characters are the alphanumeric characters (preferably numeric) which uniquely identify the file. They should also be used to sequence and group the files within the data-set into a logical, readable order. Using numerics allows for the sub-grouping by hundreds (10 sub-groups) and sequencing the files from 0 to 99 in the sub-group. It is always advisable to number in steps of 5 or 10 to allow for the insertion of new files in an appropriate place in the sequence.
- `F` is the final letter, of the 7 making up the physical file name, signifying that the object is a DDS physical file or DDL table.

There is a valid reason as to why the name of the physical file/table is restricted to 7 characters. This file is impacted by many of the other functions and components available in the DB2 database and this need to be named.

By leaving 3 available characters after the file name, the other components can be named effectively by adding to the file name on which they are based. The naming standards for the other DB2 components will illustrate this in detail.

### Logical Name Structure

`ffffffFx(x)`

Where

- `ffffffF` is the name of the "Primary" or "Only" file upon which the logical is based.
- `x(x)` = A to Z or 01 to 99 making 8-9 character names. The convention is to use 01 to 49 for "join" files, 50 - 99 for Multi-Format logicals and A to Z for "non-join" files. The choice of using 1 - 9 or 01 - 99 is based upon the maximum number of joins and multi-format logicals, where ffffffF is the MASTER in the join or multi-format.

The justification for this form of naming is;

1.  It is easy to identify the primary file associated with a logical.
2.  When viewed in alphabetical sequence the logicals are listed following their common primary physical file.
3.  When restoring the database, the physical files are restored first, followed by the logicals allowing for a more efficient index build process.

### Trigger Program Naming

Physical files have 7 events to which 1 or more trigger programs may be
attached. These events are;

- BEFORE - \*INSERT, \*DELETE, \*UDATE
- AFTER - \*INSERT, \*DELETE, \*UDATE, \*READ

Also one trigger program may be attached to multiple events. All trigger
programs will be written in RPGILE and will use the intERPrise Error
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

When a trigger program is attached to a file event, that link is given a
unique trigger name. The default for the ADDPFTRG command is \*GEN which
provides a system generated name. It is not advisable to allow this to
happen as the names can sometimes be confusing and meaningless.

The convention used in IRP for these event names is as follow;

`ffffffF_xyn`

Where

- `ffffffF` is the name of the physical file to which the trigger program will be attached.
- `_x` = `_B` if the program is a \*BEFORE trigger and `_A` if the program is an \*AFTER trigger.
- `y` = `I` for Update, `U` for Update, `D` for Delete and `R` for Read.
- `n` = `a` sequence number from 0 to 9 for use when multiple trigger programs are required for the same file and event.

### I/O Services Naming

### I/O Services \*MODULE

An I/O Services \*MODULE is created, with few exceptions, for one, and
only one, FILE, including Logicals, within the database. Generally
speaking a module contains one exported pointer and one exported
procedure. Other procedures usually exist to provide function for the
I/O Service.

The exported pointer is named filenameP, where filename is followed by
"P". This is a system pointer which is pointing to the file record
buffer defined in the services code.

The exported procedure name (I/O Services Procedure) is filename@, file
name followed by "@". This will be the name of the module after
compilation as well as the procedure name called when the I/O Service
functionality is required.

### Binder Source Member

There is a binder source member for each Data-Set making up the
database. It is named as xxxIOS@$ where xxx is the data-set mnemonic
identifying the data-set.

**NOTE: Under no circumstances must the EXPORT statements within a
binder source member be re-sequenced or removed. ANY procedure additions
must be added at the END of the EXPORT list.**

### Service Program Compiler

The service program compiler is a CLLE program containing a single
statement which when executed will create the service program.

This compiler is named for the data-set as xxxIOS@@ where xxx is the
data-set mnemonic. The service program \*SRVPGM created by this compiler
will have the same name as the compiler, xxxIOS@@.