# Liquify

Liquify is a command-line tool to convert [Liquibase](http://www.liquibase.org) changelog files
between the supported file formats(xml,yaml,json,sql).  The project comes with the
liquify bash shell script as the default way to launch the tool.  However, if you do not
have BASH on your machine, you can still launch the still using the java command as well (java -jar liquify.jar [-options] <source>).

```
Usage:
  liquify [-options] <source>

  Options:
    Required:
      -t,--type         Target changelog file type (xml,yaml,json,sql).
    Conditional:
      -db,--database    Database type to use when using the sql type (i.e oracle, h2, etc).
Example Usage:
liquify -t sql -db oracle db.changelog.xml (creates db.changelog.oracle.sql with the oracle dialect).
```
_Note: When using the sql change log file type, not all bundled change commands are supported the different
database types (i.e. createSequence, addAutoIncrement, etc).  If the tool fails to build when trying to,
convert to the sql type, it could be because of the desired database type not supporting a bundle change command
in the source change log file._