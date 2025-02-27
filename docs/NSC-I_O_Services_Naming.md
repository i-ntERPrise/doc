---
title: NSC:I/O Services Naming
permalink: /NSC:I_O Services Naming/
---

#### I/O Server \*MODULE

An I/O Server \*MODULE is created, with few exceptions, for one, and only one, FILE, including Logicals, within the database. Generally speaking a module contains one exported pointer and one exported procedure. Other procedures usually exist to provide function for the I/O Server.

The exported pointer is named `filenameP`, where filename is followed by "P". This is a system pointer which is pointing to the file record buffer defined in the server code.

The exported procedure name (I/O Server Procedure) is `filename@`, file name followed by "@". This will be the name of the module after compilation as well as the procedure name called when the I/O Server functionality is required.

#### Binder Source Member

There is a binder source member for each Data-Set making up the database. It is named as `xxxIOS$$` where `xxx` is the data-set mnemonic identifying the data-set.

#### Service Program Compiler

The service program compiler is a CLLE program containing a single statement which when executed will create the service program.

This compiler is named for the data-set as `xxxIOS@@` where `xxx` is the data-set mnemonic. The service program \*SRVPGM created by this compiler will have the same name as the compiler, `xxxIOS@@`.