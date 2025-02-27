---
title: Use of surrogate keys in the database
permalink: /Use of surrogate keys in the database/
---

## Use of surrogate keys in the database

Although there are some situations where surrogate keys provide
flexibility and some additional abstraction (we use it ourselves in very
specific situations), we believe the use of surrogate keys usually
suggest a lack of enough data analysis and correct implementation of
proper normalization principles.

We acknowledge that most SQL developers believe in using surrogate keys,
although the approach flies in the face of Codd’s database normalization
rules, and in our opinion highlight limited analysis of the true
requirement and provide a way to “get away” with limited upfront
analysis.