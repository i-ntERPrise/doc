---
title: Use of special characters in source and object naming
permalink: /Use of special characters in source and object naming/
---
## Use of special characters in source and object naming

Due to the brevity of the naming scheme (10 character source member and
object names), special characters are used to indicate SPECIFIC
functions and use of components, to clearly highlight the specialized
nature of that component.

Kindly study the [Database components naming conventions](Database_components_naming_conventions.md) carefully for more detail.

### Binder Source Member

Every binder source member should have the ‘@$’ suffix, indicating that
it is binder source, consistent with the database layer components.

### Service Program Compiler

The service program compiler is a CLLE program containing a single
statement which when executed will create the service program.

This compiler is named for the service program with a suffix of ‘@@’,
consistent with the database components. The service program \*SRVPGM
created by this compiler will have the same name as the compiler.
