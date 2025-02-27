---
title: Main Page
permalink: /Main Page/
---

**V1.1 – APPROVED (23 January 2019)**

## Introduction & Background

It is important for all participants to understand and acknowledge that
the architecture, especially the (database) components that will be
delivered by TEMBO using AO, will by nature adhere to strictly enforced
naming conventions and coding standards. Kindly review the graphic
depiction <https://www.i-nterprise.org/about.html> of the intERPrise
architecture carefully? This is a FOUNDATIONAL consideration.

Fundamental to the intERPrise architecture, is the ABSOLUTE
implementation and enforcement of true data centricity
(https://datacentricmanifesto.org/principles/) at the lowest possible
layer within the DB2 for i database.

This means that ALL validations are enforced by way of \*BEFORE triggers
on the database and that entity relationships are enforced with the
various available DB2 for i constraints. Secondary processing MAY be by
way of \*AFTER triggers, as optimal solution, where it makes sense.

Additionally, all participants should note that [ABSOLUTE separation between the database and the rest of the application](ABSOLUTE_separation_between_the_database_and_the_rest_of_the_application.md)
will be enforced. Any integration will occur at the I/O Services layer
and above, implementing the provided standardized “Error Handling”
processes. No deviation from this will be considered for inclusion in
the standard public repository, unless formally adopted by the
intERPrise standards committee.

All of the intERPrise database components (metadata repository {aka data
dictionary}, validation rules repository, tables {aka physical files},
logical layer {aka logical files, indexes, views}, constraints,
triggers, IO Services and Enterprise Services – a genuine
“data-centric”, modern DB2 implementation that are “self-aware” and
“self-enforcing”) are managed by AO in an integrated, cohesive manner. A
copy of AO has been made available to the participating intERPrise
developers – see [Use of Adsero Optima](Use_of_Adsero_Optima.md).

All the IBM i source and resulting objects can however be managed
manually, using standard IBM i functionality, without requiring AO. AO
simply manages and enforces this in a cohesive, comprehensive and
holistic fashion.

During the Synon 2E (S2E) “harvesting“ process all functional
definitions are retrieved from the internal S2E files, and internal AO
files are populated with relevant “harvested” information. This is
particularly important to acknowledge with regards to ANY validations
found within the S2E models and action diagrams.

All data validations found within the S2E models are stored in the AO
[Validation rules](Validation_rules.md) Repository.

An additional consideration in all intERPrise provided components is how
best to leverage ILE, RPG IV, DB2 for i and standard IBM i functionality
(such as \*MSGF, \*USRSPC, \*USRIDX, Pointers, subsystems, etc.),
combined with developer productivity. This immediately place short data
(aka internal) names on the agenda. Most heritage developers are
intimately familiar with the naming conventions in use for the past 30+
(actually since the announcement of CPF and the System/38 in 1978) years
and this naming scheme has served most well.

Underlying this entire issue though, is the fact that IBM i enforces a
10 character HARD limit on ANY object name. See
<https://www.ibm.com/support/knowledgecenter/ssw_ibm_i_72/rbam6/rbam6objnamrules.htm>
for more detail, if in doubt. This despite all the changes around how
source may be stored on the platform and perceptions that “long, more
descriptive” program names and other objects names can be defined.

It is vital that all participants acknowledge that the 10 character
object name (QSYS.LIB file system) is fundamental to the intERPrise
naming conventions, to keep everything simple, clear and concise.

The “long” name perception developers and administrators may have is
exactly that; a perception. The average IBM i developers and
administrators in the SMB market can do without the complications of
dealing with inconsistent naming between source and objects, especially
in an environment where you may potentially deal with thousands of
objects. This becomes particularly relevant in 24-hour production
installations, where serious program malfunctions usually occur in the
dead of night and immediate fixes are expected and demanded.

## Sections

1.  [Target Audience](Target_Audience.md)
    - [Consumers of intERPrise](Target_Audience.md#consumers-of-interprise)
    - [Contributing Developers to intERPrise](Target_Audience.md#contributing-developers-to-interprise)
2.  [Source Repository and location of source files](Source_Repository_and_location_of_source_files.md)
3.  [Supported Operating System Releases](Supported_Operating_System_Releases.md)
4.  [Supported programming languages](Supported_programming_languages.md)
5.  [Recommended IDE Release](Recommended_IDE_Release.md)
6.  [RDi Extension Names](RDi_Extension_Names.md)
7.  [General IBM i naming conventions/principles applied](General_IBM_i_naming_conventions_principles_applied.md)
8.  [Open Source tooling](Open_Source_tooling.md)
9.  [Use of special characters in source and object naming](Use_of_special_characters_in_source_and_object_naming.md)
10. [Use of FULLY FREE format RPG source](Use_of_FULLY_FREE_format_RPG_source.md)
11. [Length of object and source member names](Length_of_object_and_source_member_names.md)
12. [Line length of source members](Line_length_of_source_members.md)
13. [Comments in Code](Comments_in_Code.md)
14. [ Use and leveraging of standard IBM i objects and architecture](Use_and_leveraging_of_standard_IBM_i_objects_and_architecture.md)
15. [Standardized Error Handling](Standardized_Error_Handling.md)
16. [ABSOLUTE separation between the database and the rest of the application](ABSOLUTE_separation_between_the_database_and_the_rest_of_the_application.md)
17. [Function/Procedure ↔ Modules ↔ \*SRVPGM](Function_Procedure_Modules_SRVPGM.md)
18. [Suggested maximum number of elements/components](Suggested_maximum_number_of_elements_components.md)
19. [Use of Source code “Copy Books”](Use_of_Source_code_Copy_Books.md)
20. [Prototypes (External)](Prototypes_External.md)
21. [Compiler Directives](Compiler_Directives.md)
22. [Use of libraries (schemas)](Use_of_libraries_schemas.md)
23. [Source Files](Source_Files.md)
24. [“Delivery” channel or “user interface”](Delivery_channel_or_user_interface.md)
25. [JSON standards](JSON_standards.md)
26. [Enhancing procedures/functions](Enhancing_procedures_functions.md)
27. [Definition of database layer components that will be delivered by AO](Definition_of_database_layer_components_that_will_be_delivered_by_AO.md)
28. [Database components naming conventions](Database_components_naming_conventions.md)
29. [Validation rules](Validation_rules.md)
30. [Use of surrogate keys in the database](Use_of_surrogate_keys_in_the_database.md)
31. [Central Metadata Repository (aka “Data Dictionary”)](Central_Metadata_Repository.md)
32. [RLA and SQL result set processing](RLA_and_SQL_result_set_processing.md)
33. [Standard Code templates](Standard_Code_templates.md)
34. [MakeFile (or BUILD) Utility](MakeFile_Utility.md)
35. [High Availability/Continuous Operations considerations](High_Availability.md)
36. [Security Implementation](Security_Implementation.md)
37. [Unacceptable coding constructs](Unacceptable_coding_constructs.md)
38. [Documentation](Documentation.md)
39. [Use of Adsero Optima™ (AO) by intERPrise participating developers](Use_of_Adsero_Optima.md)

## Some additional background on naming of database components

- <https://www.itjungle.com/2008/02/06/fhg020608-story02/> - Don’t Let SQL Name Your Baby
- <https://www.itjungle.com/2008/03/05/fhg030508-story02/> - Don’t Let SQL Name Your Baby, Take 2
- <https://www.ibm.com/developerworks/data/library/techarticle/milligan/0108milligan.html> - DB2 UDB for iSeries Long and Short Identifiers
- <https://www.ibm.com/support/knowledgecenter/ssw_ibm_i_72/rbam6/rbam6objnamrules.htm> - Object Naming Rules
