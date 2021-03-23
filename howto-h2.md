# How to ... H2 !

## Define custom functions with liquibase

Format long value as size in MB:

```yaml
  - changeSet:
    id: 1
    author: 'harcyah'
    changes:
        - sql:
              stripComments: false
              splitStatements: false
              sql: >
                  CREATE ALIAS FORMAT_SIZE DETERMINISTIC AS $$
                   String format(long value) throws Exception {
                    return String.format(java.util.Locale.FRANCE, "%.2f MB", value / 1024.0f / 1024.0f);
                   };
                  $$;
```

Format long value as hh:mm duration:

```yaml
  - changeSet:
    id: 1
    author: 'harcyah'
    changes:
        - sql:
              stripComments: false
              splitStatements: false
              sql: >
                  CREATE ALIAS FORMAT_DURATION DETERMINISTIC AS $$
                    String format(long milliseconds) throws Exception {
                      long asMinutes = java.util.concurrent.TimeUnit.MILLISECONDS.toMinutes(milliseconds);
                      long hours = asMinutes / 60;
                      long minutes = asMinutes % 60;
                      return String.format("%dh %02dm", hours, minutes);
                    }
                  $$;
```
