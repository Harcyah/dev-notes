# How to ... PostgreSQL !

## Use postgresql to build a cross join from raw data

__SQL:__
```sql
SELECT * FROM
    (VALUES ('Funky'), ('Sad'), ('Fat')) as ADJECTIVES (adjective)
CROSS JOIN
    (VALUES ('Red'), ('Blue'), ('Black')) as COLORS (color)
CROSS JOIN
    (VALUES ('Rat'), ('Bear'), ('Tiger'), ('Fly')) as BEAST (beast)
```

__Results:__

| adjective | color | beast |
| :--- | :--- | :--- |
| Funky | Red | Rat |
| Funky | Red | Bear |
| Funky | Red | Tiger |
| Funky | Red | Fly |
| Funky | Blue | Rat |
| Funky | Blue | Bear |
| Funky | Blue | Tiger |
| Funky | Blue | Fly |
| Funky | Black | Rat |
| Funky | Black | Bear |
| Funky | Black | Tiger |
| Funky | Black | Fly |
| Sad | Red | Rat |
| Sad | Red | Bear |
| Sad | Red | Tiger |
| Sad | Red | Fly |
| Sad | Blue | Rat |
| Sad | Blue | Bear |
| Sad | Blue | Tiger |
| Sad | Blue | Fly |
| Sad | Black | Rat |
| Sad | Black | Bear |
| Sad | Black | Tiger |
| Sad | Black | Fly |
| Fat | Red | Rat |
| Fat | Red | Bear |
| Fat | Red | Tiger |
| Fat | Red | Fly |
| Fat | Blue | Rat |
| Fat | Blue | Bear |
| Fat | Blue | Tiger |
| Fat | Blue | Fly |
| Fat | Black | Rat |
| Fat | Black | Bear |
| Fat | Black | Tiger |
| Fat | Black | Fly |

## Get databases sizes

__SQL:__
```sql
SELECT
   datname as database_name,
   pg_database_size(datname) as database_size,
   pg_size_pretty(pg_database_size(datname)) as database_size_pretty
FROM pg_database
WHERE datistemplate = false
AND datname != 'azure_maintenance'
ORDER BY database_size DESC
```

Note: `datname != 'azure_maintenance'` skips azure protected database.
