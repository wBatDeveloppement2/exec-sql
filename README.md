#Overview

This is a library to execute SQL files in directories.

It is not meant to be executed directly on the command line, although it can be used as the basis to create command line utilities to deploy SQL.

##Procedures

### connect

Connects to a given database. Currently always use 'localhost' as it was enough for our internal needs so far, but it will be specifiable as an argument in a future version.

#### Signature

```
connect(db, user, password)
```

#### Arguments

-db: Database to connect to
-user: Database user to connect as
-password: Password of the database user to connect as

#### Return value

Returns the database connection.

### disconnect

Disconnects from the database

#### Signature

```
disconnect()
```

#### Return value

None.

### executeFile

Execute a given SQL file.

#### Signature

```
executeFile(file, callback)
```

#### Arguments

- file: SQL file to execute. Needs to be a valid path to the file.
- callback: Callback to be executed once the execution of the SQL files has completed. An error will be passed as its sole argument if any.

#### Return value

None.

### executeDirectory

Execute all SQL files in a given directory. Note that currently, sub-directories are not supposed and will in fact cause an error.

In future versions, sub-directories will be traversed recursively if specified or otherwise will be ignored.

#### Signature

```
executeDirectory(directory, callback)
```

### Arguments

- directory: Directory to execute the SQL files from. Needs to be a valid path to the directory.
- callback: Callback to be executed once the execution of the SQL files has completed. An error will be passed as its sole argument if any.
