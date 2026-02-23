---
title: MySQL end-of-support notice and database compatibility guidance for Adobe Commerce
description: This article provides information about MySQL end‑of‑support timelines and database compatibility guidance for supported Adobe Commerce versions.
---
# MySQL end-of-support notice and database compatibility guidance for Adobe Commerce

This article provides important information about MySQL end of support (EOS) and database compatibility for supported Adobe Commerce versions.
Adobe strongly recommends that merchants review this announcement and take action to maintain platform stability and remain in compliance with support requirements.

## MySQL 8.0 End of Support (EOS)

MySQL 8.0 reaches end of support (EOS) on April 30, 2026.
After this date, the following Adobe Commerce versions will not support or maintain compatibility with MySQL versions released after MySQL 8.0:

* Adobe Commerce 2.4.7
* Adobe Commerce 2.4.6
* Adobe Commerce 2.4.5

Adobe will not validate or provide support for newer MySQL major versions on these Adobe Commerce releases.

## Required action for on‑premises customers

All Adobe Commerce on‑premises customers running the following versions:

* 2.4.5
* 2.4.6
* 2.4.7

are strongly advised to migrate their database servers to a compatible MariaDB version.
MariaDB is fully supported for these Adobe Commerce versions and is the recommended database platform moving forward.

## MySQL support in Adobe Commerce 2.4.8 and 2.4.9

Adobe Commerce 2.4.8 and 2.4.9 are the last Adobe Commerce versions that support MySQL.

For these versions:
* MySQL 8.4 is the final MySQL version supported by Adobe Commerce.
* No MySQL versions released after 8.4 will be certified or supported in Adobe Commerce.

## Future direction: MariaDB as the default database platform

Going forward, Adobe Commerce continues to support MariaDB as the default and recommended database platform.

Adobe strongly recommends that the following customers begin planning their migration to MariaDB to maintain long‑term compatibility and support alignment:
* All Adobe Commerce 2.4.8 and 2.4.9 on‑premises customers
* Customers running earlier supported Adobe Commerce versions