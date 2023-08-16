---
layout: default
title: CREATE DATABASE
description: Reference and syntax for the CREATE DATABASE command.
great_grand_parent: SQL reference
grand_parent:  SQL commands
parent: Data definition
---

# CREATE DATABASE
Creates a new database.

## Syntax

```sql
CREATE DATABASE [IF NOT EXISTS] <database_name>
[WITH <properties>]
```

Where `<properties>` are:

* `ATTACHED_ENGINES = ( '<engine_name>' [, ... ] )`
* `DEFAULT_ENGINE = 'engine_name'`
* `DESCRIPTION = 'description'`


| Parameter                                      | Description                                                                                                                                                                                                                                                                                                                                                                             | Mandatory? Y/N |
| :---------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |: -------------- |
| `<database_name>`                              | An identifier that specifies the name of the database.<br>For example: `my_database`                                                                                                                                                                                                                                                                                  | Y              |
| `ATTACHED_ENGINES = ( <engine_name> [ ... ] )` | A list of engine names, for example: `ATTACHED_ENGINES = (my_engine_1 my_engine_2)`. The specified engines must be detached from any other databases first.                                                                                                                                                                                                     | N              |
| `DEFAULT_ENGINE = engine_name`                 | An identifier that specifies the name of the default engine. If not specified, the first engine in the attached engines list will be used as default. If a default engine is specified without specifying the list of attached engines or if the default engine is not in that list, the default engine will be both attached to the database and used as the default engine. | N              |
| `DESCRIPTION = 'description'`                  | The engine's description (up to 64 characters).                                                                                                                                                                                                                                                                                                                                         | N              |

## Example&ndash;create a database with (non-default) properties

```sql
CREATE DATABASE IF NOT EXISTS my_db
WITH DESCRIPTION = 'Being used for testing'
```