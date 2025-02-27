---
title: Validation rules
permalink: /Validation rules/
---

## Validation rules

The validations are stored and implemented from the Data Dictionary
(**DD** aka Metadata repository) into the underlying code, by way of one
of the following, with a “weighting” attached to the “seniority” of the
validation rule within the Validation Rules Repository (**VRR**):

- the element (field) level globally as defined in DD,
- then an element (field) \<-\> file level defined within VRR and optionally overriding the global definition
- custom user developed validation procedure, optionally overriding any previous validations