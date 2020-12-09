# How to ... SQL !

## 

Given a document_version table:

| document\_id | version | name |
| :--- | :--- | :--- |
| 1 | 1 | file 1.1 |
| 1 | 2 | file 1.2 |
| 1 | 3 | file 1.3 |
| 2 | 1 | file 2.1 |
| 2 | 2 | file 2.2 |
| 3 | 1 | file 3.1 |
| 3 | 2 | file 3.3 |
| 4 | 1 | file 4.1 |
| 4 | 2 | file 4.2 |
| 4 | 3 | file 4.3 |
| 4 | 4 | file 4.4 |
| 4 | 5 | file 4.5 |

```sql
create table document_version (
    document_id integer not null,
    version integer not null,
    name varchar(32)
);
insert into document_version (document_id, version, name)
values  (1, 1, 'file 1.1'),
        (1, 2, 'file 1.2'),
        (1, 3, 'file 1.3'),
        (2, 1, 'file 2.1'),
        (2, 2, 'file 2.2'),
        (3, 1, 'file 3.1'),
        (3, 2, 'file 3.3'),
        (4, 1, 'file 4.1'),
        (4, 2, 'file 4.2'),
        (4, 3, 'file 4.3'),
        (4, 4, 'file 4.4'),
        (4, 5, 'file 4.5');
```

How can we get:

| document\_id | version | name |
| :--- | :--- | :--- |
| 1 | 3 | file 1.3 |
| 2 | 2 | file 2.2 |
| 3 | 2 | file 3.3 |
| 4 | 5 | file 4.5 |

```sql
select * 
from document_version
where version = (
    select max(version) 
    from document_version dv 
    where dv.document_id = document_version.document_id
)
order by document_id
```
