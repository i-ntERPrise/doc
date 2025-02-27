---
title: Function Procedure Modules SRVPGM
permalink: /Function Procedure Modules SRVPGM/
---

## Function/Procedure ↔ Modules ↔ \*SRVPGM

It is CRITICAL that the inherent capabilities of ILE be fully exploited
and leveraged. As little code duplication and single instance re-usable
code components are the objective we strive for. This should be a
continuous focus of every participating developer.

The moment there is a possibility that a specific function/procedure may
be required or potentially valuable to other functions, it should
immediately be made available as a module in a service program.

If uncertain about this, please review the materials at
<https://www.ile-rpg.org/education.html> again.

### Procedures/Functions

As procedures are the basic building blocks everything is built upon
they should get extra attention when being developed. Consciously
consider the principle of single-instance re-usable code, with as little
as practically possible duplication. Consider future maintainability at
all times, keeping the functions/procedures tight and concise.

It is important to recognise that there is a fine balance between
limiting duplication, versus providing overly complicated code. As a
result, if overly complex code and “overloading” of an existing function
becomes a future maintenance concern, rather create a new
function/procedure, indicating the duplication/overlap.

If substantial duplication between two or more procedures/functions
exists, rather create a separate function/procedure with the common code
within the same module. The objective should always be to limit
duplication as far as practically possible.

### Modules

Modules are the basic building block of any program and/or service
program. The size of a module varies greatly but should be kept as short
and concise as practical. Consciously consider the maintainability of
the code produced.

As described in the preceding paragraph describing functions/procedures,
always strive to limit duplication, by “wrapping” common code in
separate functions/procedures within the module.

The following principles should be followed:

- One module should only cover one domain.
- One module should preferably have multiple procedures.
- Each procedure in a module should have a prototype definition copybook.

### Service programs

A service program may preferably contain multiple modules. Additionally
service programs should be function bound, grouping all related activity
together.