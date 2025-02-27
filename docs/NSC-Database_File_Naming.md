---
title: NSC:Database File Naming
permalink: /NSC:Database File Naming/
---

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

The naming standards and conventions described below apply to ALL of the above file types.

#### Physical Name Structure

`abbnnnF`

Where

- `a` = Must be an acceptable IBM i naming start character.
- `bb` = 2 alphanumeric characters.
	- The abb characters together make up a data-set identification mnemonic that groups together files of common purpose. An example of this would be "DEB" as the Data-Set to use to group all "Debtors" related files (both Physical & Logical) together.
- `nnn` = These 3 characters are the alphanumeric characters (preferably numeric) which uniquely identify the file.
	- They should also be used to sequence and group the files within the data-set into a logical, readable order. Using numerics allows for the sub-grouping by hundreds (10 sub-groups) and sequencing the files from 0 to 99 in the sub-group. It is always advisable to number in steps of 5 or 10 to allow for the insertion of new files in an appropriate place in the sequence.
- `F` is the final letter, of the 7 making up the physical file name, signifying that the object is a DDS physical file or DDL table.

There is a valid reason as to why the name of the physical file/table is
restricted to 7 characters. This file is impacted by many of the other
functions and components available in the DB2 database and these need to
be named. By leaving 3 available characters after the file name, the
other components can be named effectively by adding to the file name on
which they are based. The naming standards for the other DB2 components
will illustrate this in detail.

#### Logical Name Structure

`ffffffFx`

Where

- `ffffffF` is the name of the "Primary" or "Only" file upon which the logical is based.
- `x` = A to Z or 0 to 9 making 8 character names. The convention is to use 0 to 9 for "join" files and A to Z for "non-join" files.

The justification for this form of naming is;

1.  It is easy to identify the primary file associated with a logical.
2.  When viewed in alphabetical sequence the logicals are listed following their common primary physical file.
3.  When restoring the database, the physical files are restored first, followed by the logicals allowing for a more efficient index build process.