---
title: Use of libraries (schemas)
permalink: /Use of libraries (schemas)/
---

## Use of libraries (schemas)

The following libraries will be created during the automated build
process, for storing the various categories of components:

|        |                                                                                                                                                                                                                                                                                                                                |
|--------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| IRPGPL | intERPrise General Purpose Schema.                                                                                                                                                                                                                                                                                             |
| IRPDB2 | intERPrise all PF and LF database components.                                                                                                                                                                                                                                                                                  |
| IRPDBC | intERPrise all other database components – see [Definition of database layer components that will be delivered by AO](Definition_of_database_layer_components_that_will_be_delivered_by_AO.md) for a complete list.                                                                                                   |
| IRPENT | intERPrise Enterprise (Controller) Layer of all other logic objects not part of database components.                                                                                                                                                                                                                           |
| IRPSRC | intERPrise ALL source files, regardless of function.                                                                                                                                                                                                                                                                           |
| IRPJRN | intERPrise OPTIONAL journaling library for commitment control and HA. Usually, the IRPDB2 and IRPDBC libraries will represent/define the database layer of intERPrise. Users may optionally decide to keep the journal receivers separately. Normally the journals and journal receivers will be located in the IRPDB2 schema. |