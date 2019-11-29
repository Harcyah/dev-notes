# How to ... MySQL !

## Compute RIBPS [source](https://dba.stackexchange.com/questions/39467/mysql-performance-impact-of-increasing-innodb-buffer-pool-size)

RIBPS stands for `Recommended InnoDB Buffer Pool Size`

```
SELECT CEILING(SUM(data_length+index_length)/POWER(1024,2)) RIBPS FROM information_schema.tables WHERE engine='InnoDB';
```
