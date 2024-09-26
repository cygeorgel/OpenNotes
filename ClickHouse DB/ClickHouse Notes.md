# ClickHouse Notes



## uniq()


```
SELECT uniq(*)/count(*) FROM calls
```


## Removing duplicates

```
OPTIMIZE TABLE calls FINAL DEDUPLICATE
```


Or on a subset of columns:

```
OPTIMIZE TABLE calls FINAL DEDUPLICATE BY call_id;
```

