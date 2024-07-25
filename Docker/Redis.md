-p 6379

```
docker exec -it redis bash
```



## Clusterdown

```
(error) CLUSTERDOWN Hash slot not served
```

```
redis-cli -a {password} --cluster fix localhost:6379
```