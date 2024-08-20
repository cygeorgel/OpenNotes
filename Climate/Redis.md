-p 6379

```
docker exec -it redis bash
```



## Clusterdown

```
(error) CLUSTERDOWN Hash slot not served
```


1/ check if password in redis.conf match docker-compose.yml config

2/ run:

```
redis-cli -a {password} --cluster fix localhost:6379
```


