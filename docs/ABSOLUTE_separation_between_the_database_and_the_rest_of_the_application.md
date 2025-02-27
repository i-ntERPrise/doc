---
title: ABSOLUTE separation between the database and the rest of the application
permalink: /ABSOLUTE separation between the database and the rest of the application/
---

## ABSOLUTE separation between the database and the rest of the application

Kindly review the architectural depiction at <https://www.i-nterprise.org/about.html>. From this, please acknowledge that integration and interfacing will occur at IO Services level.

Absolutely no updates will be allowed against the database, from external tools or methods and such updates will be summarily rejected by DB2. Be cautioned of this fact.

Read access external to the IO Services are possible due to the inherent capabilities of IBM i, but we would suggest that the IO Services should preferably be your ONLY connection/integration to the database.